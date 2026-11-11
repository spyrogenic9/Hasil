PS C:\GTPS\Gurotopia> Write-Host "`n===== ADMIN FILES ====="

===== ADMIN FILES =====
PS C:\GTPS\Gurotopia> Get-ChildItem .\include\admin -Recurse -File |
>>     Select-Object -ExpandProperty FullName
C:\GTPS\Gurotopia\include\admin\admin.cpp
C:\GTPS\Gurotopia\include\admin\admin.hpp
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== ADMIN IMPLEMENTATION ====="

===== ADMIN IMPLEMENTATION =====
PS C:\GTPS\Gurotopia> Get-Content .\include\admin\admin.hpp
#pragma once

#include "tools/string.hpp"

namespace admin
{
    void initialize();
    bool is_banned(const std::string& growid);
    bool is_muted(const std::string& growid);
    void open_panel(ENetEvent& event);
    void handle_dialog(ENetEvent& event, const ::hPipe& hPipe);
    void command(ENetEvent& event, std::string_view text);
}
PS C:\GTPS\Gurotopia> Get-Content .\include\admin\admin.cpp
#include "pch.hpp"

#include "admin.hpp"

#include "action/join_request.hpp"
#include "action/quit_to_exit.hpp"
#include "onVariant/ConsoleMessage.hpp"
#include "onVariant/SetBux.hpp"
#include "onVariant/SetClothing.hpp"
#include "onVariant/Spawn.hpp"

#include <algorithm>
#include <charconv>
#include <cctype>
#include <limits>

namespace
{
    struct online_player
    {
        ENetPeer* connection{};
        ::peer* data{};

        explicit operator bool() const noexcept
        {
            return connection != nullptr && data != nullptr;
        }
    };

    std::string trim(std::string value)
    {
        const auto first = std::ranges::find_if_not(value, [](unsigned char c) { return std::isspace(c) != 0; });
        value.erase(value.begin(), first);
        const auto last = std::ranges::find_if_not(value.rbegin(), value.rend(), [](unsigned char c) { return std::isspace(c) != 0; }).base();
        value.erase(last, value.end());
        return value;
    }

    std::string clean_text(std::string value, std::size_t max_length)
    {
        for (char& c : value)
            if (c == '|' || c == '\n' || c == '\r' || c == '\0') c = ' ';
        value = trim(std::move(value));
        if (value.size() > max_length) value.resize(max_length);
        return value;
    }

    std::string lower(std::string value)
    {
        for (char& c : value) c = static_cast<char>(std::tolower(static_cast<unsigned char>(c)));
        return value;
    }

    bool valid_growid(const std::string& value)
    {
        if (value.empty() || value.size() > 18) return false;
        return std::all_of(value.begin(), value.end(), [](unsigned char c)
        {
            return std::isalnum(c) != 0 || c == '_';
        });
    }

    bool parse_integer(const std::string& value, long long& output)
    {
        if (value.empty()) return false;
        const char* begin = value.data();
        const char* end = begin + value.size();
        const auto result = std::from_chars(begin, end, output);
        return result.ec == std::errc{} && result.ptr == end;
    }

    online_player find_online(const std::string& growid)
    {
        if (host == nullptr || growid.empty()) return {};
        const std::string wanted = lower(growid);
        for (ENetPeer* connection = host->peers, *end = connection + host->peerCount; connection != end; ++connection)
        {
            if (connection->state != ENET_PEER_STATE_CONNECTED || connection->data == nullptr) continue;
            auto* data = static_cast<::peer*>(connection->data);
            if (lower(data->growid) == wanted) return { connection, data };
        }
        return {};
    }

    bool account_role(const std::string& growid, u_char& value)
    {
        ::hStmt stmt{ "SELECT role FROM peer WHERE LOWER(growid) = LOWER(?) LIMIT 1" };
        MYSQL_BIND param = make_bind_in(growid);
        unsigned raw_role{};
        MYSQL_BIND result = make_bind_out(raw_role);
        stmt.bind_param(&param);
        mysql_stmt_bind_result(stmt.pStmt, &result);
        stmt.execute();
        if (mysql_stmt_store_result(stmt.pStmt) != 0 || mysql_stmt_num_rows(stmt.pStmt) == 0) return false;
        if (mysql_stmt_fetch(stmt.pStmt) != 0) return false;
        value = raw_role <= PLAYER ? static_cast<u_char>(raw_role) : PLAYER;
        return true;
    }

    bool record_exists(const std::string& table, const std::string& growid)
    {
        const std::string query = "SELECT 1 FROM " + table + " WHERE LOWER(growid) = LOWER(?) LIMIT 1";
        ::hStmt stmt{ query };
        MYSQL_BIND param = make_bind_in(growid);
        stmt.bind_param(&param);
        stmt.execute();
        return mysql_stmt_store_result(stmt.pStmt) == 0 && mysql_stmt_num_rows(stmt.pStmt) > 0;
    }

    void upsert_record(const std::string& table, const std::string& growid, const std::string& actor, const std::string& reason)
    {
        const std::string query = "INSERT INTO " + table + " (growid, changed_by, reason) VALUES (?, ?, ?) "
            "ON DUPLICATE KEY UPDATE changed_by = VALUES(changed_by), reason = VALUES(reason), created_at = CURRENT_TIMESTAMP";
        ::hStmt stmt{ query };
        MYSQL_BIND params[3] = { make_bind_in(growid), make_bind_in(actor), make_bind_in(reason) };
        stmt.bind_param(params);
        stmt.execute();
    }

    void remove_record(const std::string& table, const std::string& growid)
    {
        const std::string query = "DELETE FROM " + table + " WHERE LOWER(growid) = LOWER(?)";
        ::hStmt stmt{ query };
        MYSQL_BIND param = make_bind_in(growid);
        stmt.bind_param(&param);
        stmt.execute();
    }

    void log_action(const std::string& actor, const std::string& action, const std::string& target, const std::string& details)
    {
        ::hStmt stmt{ "INSERT INTO admin_logs (actor, action, target, details) VALUES (?, ?, ?, ?)" };
        MYSQL_BIND params[4] = {
            make_bind_in(actor), make_bind_in(action), make_bind_in(target), make_bind_in(details)
        };
        stmt.bind_param(params);
        stmt.execute();
    }

    void tell(ENetPeer* connection, const std::string& message)
    {
        if (connection != nullptr) on::ConsoleMessage(connection, message);
    }

    bool staff_only(ENetEvent& event, u_char minimum_role)
    {
        if (event.peer == nullptr || event.peer->data == nullptr) return false;
        const auto* actor = static_cast<const ::peer*>(event.peer->data);
        if (!peer_is_staff_role(actor->role) || actor->role > minimum_role)
        {
            tell(event.peer, "`4Access denied. You do not have permission to use this action.``");
            return false;
        }
        return true;
    }

    bool can_manage_target(const ::peer& actor, u_char target_role, const std::string& target_name)
    {
        if (lower(actor.growid) == lower(target_name)) return false;
        if (actor.role == OWNER) return true;
        return actor.role < target_role;
    }

    bool load_target_role(ENetPeer* actor_connection, const ::peer& actor, const std::string& target_name, u_char& target_role)
    {
        if (!account_role(target_name, target_role))
        {
            tell(actor_connection, "`4Account not found.``");
            return false;
        }
        if (!can_manage_target(actor, target_role, target_name))
        {
            tell(actor_connection, "`4You cannot manage an account with an equal or higher role.``");
            return false;
        }
        return true;
    }

    void disconnect_target(online_player target, const std::string& reason)
    {
        if (!target) return;
        tell(target.connection, reason);
        enet_peer_disconnect_later(target.connection, 0);
    }

    void update_staff_avatar(online_player target)
    {
        if (!target || target.data->netid == 0 || target.data->recent_worlds.back().empty()) return;
        const std::string world_name = target.data->recent_worlds.back();
        std::string name_color = "`w";
        if (const auto world_it = std::ranges::find(worlds, world_name, &::world::name); world_it != worlds.end())
        {
            if (target.data->user_id == world_it->owner) name_color = "`2";
            else if (std::ranges::find(world_it->access, target.data->user_id) != world_it->access.end()) name_color = "`^";
        }
        target.data->display_growid = make_peer_display_growid(target.data->role, target.data->growid, name_color);
        peers(world_name, PeerSearch::WORLD, [&](ENetPeer* connection)
        {
            auto* other = static_cast<::peer*>(connection->data);
            if (other->user_id == target.data->user_id) return;
            on::Spawn(*connection, target.data->netid, target.data->user_id, target.data->pos,
                target.data->display_growid, target.data->country,
                peer_is_staff_role(target.data->role), peer_is_super_staff_role(target.data->role), false);
            on::Spawn(*target.connection, other->netid, other->user_id, other->pos,
                other->display_growid, other->country,
                peer_is_staff_role(other->role), peer_is_super_staff_role(other->role), false);
        });
        on::Spawn(*target.connection, target.data->netid, target.data->user_id, target.data->pos,
            target.data->display_growid, target.data->country,
            peer_is_staff_role(target.data->role), peer_is_super_staff_role(target.data->role), true);
        on::SetClothing(target.connection);
    }

    void open_panel_for(ENetPeer* connection, const ::peer& actor)
    {
        std::string dialog;
        dialog += "set_default_color|`o\n";
        dialog += "add_label|big|Gurotopia Staff Panel|left|\n";
        dialog += std::format("add_smalltext|Signed in as: {} | Role: {}|left|\n", actor.growid,
            actor.role == OWNER ? "OWNER" : actor.role == DEVELOPER ? "DEVELOPER" : "MODERATOR");
        dialog += "add_spacer|small|\n";
        dialog += "add_text_input|admin_target|Target GrowID||18|\n";
        dialog += "add_text_input|admin_reason|Reason|Staff action|100|\n";
        dialog += "add_label|medium|MODERATION|left|\n";
        dialog += "add_button|admin_kick|Kick|noflags|0|0|\n";
        dialog += "add_button|admin_ban|Ban|noflags|0|0|\n";
        dialog += "add_button|admin_unban|Unban|noflags|0|0|\n";
        dialog += "add_button|admin_mute|Mute|noflags|0|0|\n";
        dialog += "add_button|admin_unmute|Unmute|noflags|0|0|\n";
        dialog += "add_button|admin_goto|Go to player|noflags|0|0|\n";
        dialog += "add_button|admin_summon|Summon player|noflags|0|0|\n";
        dialog += "add_spacer|small|\n";
        dialog += "add_label|medium|SERVER|left|\n";
        dialog += "add_text_input|admin_announce|Announcement||160|\n";
        dialog += "add_button|admin_announce_btn|Broadcast announcement|noflags|0|0|\n";

        if (actor.role <= DEVELOPER)
        {
            dialog += "add_spacer|small|\n";
            dialog += "add_label|medium|DEVELOPER TOOLS|left|\n";
            dialog += "add_text_input|admin_amount|Amount||18|\n";
            dialog += "add_button|admin_gems_set|Set target gems|noflags|0|0|\n";
            dialog += "add_button|admin_gems_add|Add target gems|noflags|0|0|\n";
            dialog += "add_button|admin_gems_take|Remove target gems|noflags|0|0|\n";
            dialog += "add_text_input|admin_item_id|Item ID||8|\n";
            dialog += "add_button|admin_give_item|Give item to target|noflags|0|0|\n";
            dialog += "add_text_input|admin_weather|Weather ID (0-80)||3|\n";
            dialog += "add_button|admin_weather_btn|Set weather in current world|noflags|0|0|\n";
            dialog += "add_button|admin_world_public|Toggle current world public/private|noflags|0|0|\n";
            dialog += "add_text_input|admin_role|New role: 2=MODERATOR, 3=PLAYER (OWNER can use 0-3)||1|\n";
            dialog += "add_button|admin_set_role|Set target role|noflags|0|0|\n";
        }

        dialog += "add_spacer|small|\n";
        dialog += "add_smalltext|Every action is validated by the server and recorded in the admin log.|left|\n";
        dialog += "end_dialog|gurotopia_admin|Close|\n";
        send_varlist(connection, { "OnDialogRequest", dialog });
    }

}

namespace admin
{
    void initialize()
    {
        const char* queries[] = {
            "CREATE TABLE IF NOT EXISTS admin_bans (growid VARCHAR(18) PRIMARY KEY, changed_by VARCHAR(18) NOT NULL, reason VARCHAR(255) NOT NULL DEFAULT '', created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP)",
            "CREATE TABLE IF NOT EXISTS admin_mutes (growid VARCHAR(18) PRIMARY KEY, changed_by VARCHAR(18) NOT NULL, reason VARCHAR(255) NOT NULL DEFAULT '', created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP)",
            "CREATE TABLE IF NOT EXISTS admin_logs (id BIGINT AUTO_INCREMENT PRIMARY KEY, actor VARCHAR(18) NOT NULL, action VARCHAR(32) NOT NULL, target VARCHAR(18) NOT NULL DEFAULT '', details VARCHAR(255) NOT NULL DEFAULT '', created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP)"
        };
        for (const char* query : queries)
            if (mysql_query(db.mysql, query) != 0)
                print(std::format("[ADMIN] Database initialization failed: {}", mysql_error(db.mysql)).c_str());
    }

    bool is_banned(const std::string& growid)
    {
        return record_exists("admin_bans", growid);
    }

    bool is_muted(const std::string& growid)
    {
        return record_exists("admin_mutes", growid);
    }

    void open_panel(ENetEvent& event)
    {
        if (event.peer == nullptr || event.peer->data == nullptr) return;
        const auto* actor = static_cast<const ::peer*>(event.peer->data);
        if (!peer_is_staff_role(actor->role))
        {
            tell(event.peer, "`4The staff panel is available to staff accounts only.``");
            return;
        }
        open_panel_for(event.peer, *actor);
    }

    void command(ENetEvent& event, std::string_view)
    {
        open_panel(event);
    }

    void handle_dialog(ENetEvent& event, const ::hPipe& hPipe)
    {
        if (event.peer == nullptr || event.peer->data == nullptr) return;
        auto* actor = static_cast<::peer*>(event.peer->data);
        if (!peer_is_staff_role(actor->role))
        {
            tell(event.peer, "`4Access denied.``");
            return;
        }

        const std::string button = hPipe["buttonClicked"];
        if (button.empty()) return;

        const std::string target_name = clean_text(hPipe["admin_target"], 18);
        const std::string reason = clean_text(hPipe["admin_reason"], 100);
        const std::string details = reason.empty() ? "Staff action" : reason;
        const auto report = [&](const std::string& action, const std::string& target, const std::string& detail)
        {
            log_action(actor->growid, action, target, detail);
        };

        if (button == "admin_announce_btn")
        {
            const std::string message = clean_text(hPipe["admin_announce"], 160);
            if (message.empty()) { tell(event.peer, "`4Enter an announcement first.``"); return; }
            peers("", PeerSearch::EVERYONE, [&](ENetPeer* connection)
            {
                on::ConsoleMessage(connection, std::format("`4[SERVER ANNOUNCEMENT]`` {}", message));
            });
            report("announce", "", message);
            tell(event.peer, "`2Announcement sent to all online players.``");
            open_panel_for(event.peer, *actor);
            return;
        }

        if (button == "admin_weather_btn")
        {
            if (!staff_only(event, DEVELOPER)) return;
            long long weather_id{};
            if (!parse_integer(trim(hPipe["admin_weather"]), weather_id) || weather_id < 0 || weather_id > 80)
            {
                tell(event.peer, "`4Weather ID must be between 0 and 80.``"); return;
            }
            const std::string current_world = actor->recent_worlds.back();
            if (current_world.empty()) { tell(event.peer, "`4Enter a world first.``"); return; }
            peers(current_world, PeerSearch::WORLD, [&](ENetPeer* connection)
            {
                send_varlist(connection, { "OnSetCurrentWeather", static_cast<int>(weather_id) });
            });
            report("world_weather", current_world, std::to_string(weather_id));
            tell(event.peer, "`2Weather updated for players currently in this world.``");
            open_panel_for(event.peer, *actor);
            return;
        }
        if (button == "admin_world_public")
        {
            if (!staff_only(event, DEVELOPER)) return;
            const std::string current_world = actor->recent_worlds.back();
            auto world_it = std::ranges::find(worlds, current_world, &::world::name);
            if (world_it == worlds.end()) { tell(event.peer, "`4Enter a world first.``"); return; }

            auto lock_it = std::ranges::find_if(world_it->blocks, [](const ::block& block)
            {
                return block.fg != 0 && !is_tile_lock(block.fg) && id_to_item(block.fg).type == type::LOCK;
            });
            if (lock_it == world_it->blocks.end())
            {
                tell(event.peer, "`4This world has no global World Lock to modify.``"); return;
            }

            world_it->is_public = !world_it->is_public;
            lock_it->state[2] &= static_cast<u_char>(~(S_PUBLIC | S_LOCKED));
            lock_it->state[2] |= world_it->is_public ? S_PUBLIC : S_LOCKED;
            const auto lock_index = static_cast<std::size_t>(std::distance(world_it->blocks.begin(), lock_it));
            const ::pos lock_pos{ static_cast<int>(lock_index % 100), static_cast<int>(lock_index / 100) };
            send_tile_update(event, { .id = lock_it->fg, .punch = lock_pos }, *lock_it, *world_it);
            const std::string state = world_it->is_public ? "PUBLIC" : "PRIVATE";
            report("world_visibility", current_world, state);
            tell(event.peer, std::format("`2World {} is now {}.``", current_world, state));
            open_panel_for(event.peer, *actor);
            return;
        }

        if (button == "admin_kick" || button == "admin_ban" || button == "admin_unban" ||
            button == "admin_mute" || button == "admin_unmute" || button == "admin_goto" ||
            button == "admin_summon" || button == "admin_gems_set" || button == "admin_gems_add" ||
            button == "admin_gems_take" || button == "admin_give_item" || button == "admin_set_role")
        {
            if (!valid_growid(target_name)) { tell(event.peer, "`4Enter a valid target GrowID (1-18 letters or numbers).``"); return; }
        }

        if (button == "admin_kick" || button == "admin_ban" || button == "admin_unban" ||
            button == "admin_mute" || button == "admin_unmute" || button == "admin_summon")
        {
            u_char target_role{};
            if (!load_target_role(event.peer, *actor, target_name, target_role)) return;
            online_player target = find_online(target_name);

            if (button == "admin_kick")
            {
                if (!target) { tell(event.peer, "`4That player is not online.``"); return; }
                disconnect_target(target, "`4You were kicked by a staff member.``");
                report("kick", target_name, details);
                tell(event.peer, std::format("`2Kicked {}.``", target_name));
            }
            else if (button == "admin_ban")
            {
                upsert_record("admin_bans", target_name, actor->growid, details);
                if (target) disconnect_target(target, "`4Your account has been banned from this server.``");
                report("ban", target_name, details);
                tell(event.peer, std::format("`2Banned {}.``", target_name));
            }
            else if (button == "admin_unban")
            {
                remove_record("admin_bans", target_name);
                report("unban", target_name, details);
                tell(event.peer, std::format("`2Unbanned {}.``", target_name));
            }
            else if (button == "admin_mute")
            {
                upsert_record("admin_mutes", target_name, actor->growid, details);
                if (target) target.data->muted = true;
                report("mute", target_name, details);
                tell(event.peer, std::format("`2Muted {}.``", target_name));
            }
            else if (button == "admin_unmute")
            {
                remove_record("admin_mutes", target_name);
                if (target) target.data->muted = false;
                report("unmute", target_name, details);
                tell(event.peer, std::format("`2Unmuted {}.``", target_name));
            }
            else if (button == "admin_summon")
            {
                if (!target) { tell(event.peer, "`4That player is not online.``"); return; }
                const std::string destination = actor->recent_worlds.back();
                if (destination.empty()) { tell(event.peer, "`4Enter a world before summoning a player.``"); return; }
                ENetEvent target_event{};
                target_event.peer = target.connection;
                action::quit_to_exit(target_event, "", true);
                action::join_request(target_event, "", destination);
                report("summon", target_name, destination);
                tell(event.peer, std::format("`2Summoned {} to {}.``", target_name, destination));
            }
            open_panel_for(event.peer, *actor);
            return;
        }

        if (button == "admin_goto")
        {
            if (!staff_only(event, MODERATOR)) return;
            online_player target = find_online(target_name);
            if (!target || target.data->recent_worlds.back().empty())
            {
                tell(event.peer, "`4Target player is not online in a world.``"); return;
            }
            const std::string destination = target.data->recent_worlds.back();
            action::quit_to_exit(event, "", true);
            action::join_request(event, "", destination);
            report("goto", target_name, destination);
            tell(event.peer, std::format("`2Teleported to {}.``", target_name));
            return;
        }

        if (button == "admin_gems_set" || button == "admin_gems_add" || button == "admin_gems_take" || button == "admin_give_item")
        {
            if (!staff_only(event, DEVELOPER)) return;
            u_char target_role{};
            if (!load_target_role(event.peer, *actor, target_name, target_role)) return;
            const std::string raw_amount = trim(hPipe["admin_amount"]);
            long long amount{};
            if (!parse_integer(raw_amount, amount) || amount < 0 || amount > 1000000000000LL)
            {
                tell(event.peer, "`4Amount must be a number from 0 to 1,000,000,000,000.``"); return;
            }
            online_player online = find_online(target_name);
            ::peer offline{};
            ::peer* target = online ? online.data : &offline;
            ENetEvent target_event{};
            if (online) target_event.peer = online.connection;
            else
            {
                offline.growid = target_name;
                offline.mysql_select_all(false);
                if (offline.growid.empty()) { tell(event.peer, "`4Account not found.``"); return; }
            }

            if (button == "admin_give_item")
            {
                long long item_id{};
                if (!parse_integer(trim(hPipe["admin_item_id"]), item_id) || item_id < 1 || item_id > 32767 || amount < 1 || amount > 200)
                {
                    tell(event.peer, "`4Item ID must be 1-65535 and amount must be 1-200.``"); return;
                }
                const u_short excess = target->emplace(::slot{ static_cast<short>(item_id), static_cast<short>(amount) });
                target->mysql_update_all();
                if (online) send_inventory_state(target_event);
                report("give_item", target_name, std::format("item={} amount={} excess={}", item_id, amount, excess));
                tell(event.peer, std::format("`2Gave item {} x{} to {}. Excess not added: {}.``", item_id, amount - excess, target_name, excess));
            }
            else
            {
                if (button == "admin_gems_set") target->gems = amount;
                else if (button == "admin_gems_add")
                {
                    if (target->gems > std::numeric_limits<long long>::max() - amount)
                    { tell(event.peer, "`4Gem balance would overflow.``"); return; }
                    target->gems += amount;
                }
                else target->gems = std::max(0LL, target->gems - amount);
                target->mysql_update_all();
                if (online) on::SetBux(target_event);
                report(button == "admin_gems_set" ? "set_gems" : button == "admin_gems_add" ? "add_gems" : "take_gems",
                    target_name, std::to_string(amount));
                tell(event.peer, std::format("`2Updated {}'s gem balance to {}.``", target_name, target->gems));
            }
            open_panel_for(event.peer, *actor);
            return;
        }

        if (button == "admin_set_role")
        {
            if (!staff_only(event, DEVELOPER)) return;
            u_char target_role{};
            if (!load_target_role(event.peer, *actor, target_name, target_role)) return;
            long long requested_role{};
            if (!parse_integer(trim(hPipe["admin_role"]), requested_role) || requested_role < OWNER || requested_role > PLAYER)
            {
                tell(event.peer, "`4Role must be 0=OWNER, 1=DEVELOPER, 2=MODERATOR, or 3=PLAYER.``"); return;
            }
            if (actor->role != OWNER && requested_role < MODERATOR)
            {
                tell(event.peer, "`4DEVELOPER can only assign MODERATOR or PLAYER roles.``"); return;
            }
            ::hStmt stmt{ "UPDATE peer SET role = ? WHERE LOWER(growid) = LOWER(?)" };
            const unsigned new_role = static_cast<unsigned>(requested_role);
            MYSQL_BIND params[2] = { make_bind_in(new_role), make_bind_in(target_name) };
            stmt.bind_param(params);
            stmt.execute();
            online_player target = find_online(target_name);
            if (target)
            {
                target.data->role = static_cast<u_char>(new_role);
                target.data->mysql_update_all();
                update_staff_avatar(target);
            }
            report("set_role", target_name, std::to_string(new_role));
            tell(event.peer, std::format("`2Role for {} changed to {}.``", target_name,
                new_role == OWNER ? "OWNER" : new_role == DEVELOPER ? "DEVELOPER" : new_role == MODERATOR ? "MODERATOR" : "PLAYER"));
            open_panel_for(event.peer, *actor);
            return;
        }

        tell(event.peer, "`4Unknown admin action. Reopen /admin and try again.``");
    }
}

PS C:\GTPS\Gurotopia> Write-Host "`n===== WRENCH / HAND REFERENCES ====="

===== WRENCH / HAND REFERENCES =====
PS C:\GTPS\Gurotopia> Get-ChildItem .\include -Recurse -File -Include *.cpp,*.hpp |
>>     Select-String -Pattern 'wrench|hand|peer_is_staff_role|peer_is_super_staff_role' |
>>     ForEach-Object {
>>         "$($_.Path):$($_.LineNumber): $($_.Line.Trim())"
>>     }
C:\GTPS\Gurotopia\include\action\dialog_return\megaphone.cpp:11: sb(event, "sb " + message); // @note sb() skips the first 3 chars ("sb ") @todo handle this when /sb requires gems @todo handle trim
C:\GTPS\Gurotopia\include\action\dialog_return\trash_item.cpp:38: if (item.id != item_id || item.type == type::FIST || item.type == type::WRENCH)
C:\GTPS\Gurotopia\include\action\dialog_return\__dialog_return.cpp:26: {"gurotopia_admin", std::bind(&admin::handle_dialog, std::placeholders::_1, std::placeholders::_2)},
C:\GTPS\Gurotopia\include\action\info.cpp:14: if (property & 02) temp.emplace_back("`1This item has special properties you can adjust with the Wrench.``");
C:\GTPS\Gurotopia\include\action\info.cpp:18: if (property & 0x20/*@todo handle Valentine*/) temp.emplace_back("`1This item can kill zombies during a Pandemic!``");
C:\GTPS\Gurotopia\include\action\join_request.cpp:89: peer_is_staff_role(pOthers->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp:90: peer_is_super_staff_role(pOthers->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp:99: peer_is_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp:100: peer_is_super_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp:118: peer_is_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp:119: peer_is_super_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\trash.cpp:13: if (item.type == type::FIST || item.type == type::WRENCH)
C:\GTPS\Gurotopia\include\action\wrench.cpp:5: #include "wrench.hpp"
C:\GTPS\Gurotopia\include\action\wrench.cpp:7: void action::wrench(ENetEvent& event, const std::string& header)
C:\GTPS\Gurotopia\include\action\wrench.cpp:21: /* wrench yourself */
C:\GTPS\Gurotopia\include\action\wrench.cpp:28: .add_popup_name("WrenchMenu")
C:\GTPS\Gurotopia\include\action\wrench.cpp:36: .add_custom_button("open_personlize_profile", "image:interface/large/gui_wrench_personalize_profile.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:37: .add_custom_button("set_online_status", "image:interface/large/gui_wrench_online_status_1green.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:38: .add_custom_button("billboard_edit", "image:interface/large/gui_wrench_edit_billboard.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:39: .add_custom_button("wardrobe_customization", "image:interface/large/gui_wrench_wardrobe.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:40: .add_custom_button("seed_diary_customization", "image:interface/large/gui_wrench_seed_diary.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:41: .add_custom_button("notebook_edit", "image:interface/large/gui_wrench_notebook.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:42: .add_custom_button("goals", "image:interface/large/gui_wrench_goals_quests.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:43: .add_custom_button("bonus", "image:interface/large/gui_wrench_daily_bonus_active.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:44: .add_custom_button("my_worlds", "image:interface/large/gui_wrench_my_worlds.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:45: .add_custom_button("alist", "image:interface/large/gui_wrench_achievements.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:47: .add_custom_button("emojis", "image:interface/large/gui_wrench_growmojis.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:48: .add_custom_button("marvelous_missions", "image:interface/large/gui_wrench_marvelous_missions.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:49: .add_custom_button("title_edit", "image:interface/large/gui_wrench_title.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:50: .add_custom_button("trade_scan", "image:interface/large/gui_wrench_trades.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:52: .add_custom_button("pets", "image:interface/large/gui_wrench_battle_pets.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:53: .add_custom_button("wrench_customization", "image:interface/large/gui_wrench_customization.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:54: .add_custom_button("open_worldlock_storage", "image:interface/large/gui_wrench_auction.rttex;image_size:400,260;width:0.19;")
C:\GTPS\Gurotopia\include\action\wrench.cpp:62: /* @todo handle peer's effects */
C:\GTPS\Gurotopia\include\action\wrench.cpp:77: /* wrench someone else */
C:\GTPS\Gurotopia\include\action\wrench.cpp:84: .add_popup_name("WrenchMenu")
C:\GTPS\Gurotopia\include\action\wrench.hpp:5: extern void wrench(ENetEvent& event, const std::string& header);
C:\GTPS\Gurotopia\include\action\__action.cpp:21: #include "wrench.hpp"
C:\GTPS\Gurotopia\include\action\__action.cpp:58: {"action|wrench", std::bind(&action::wrench, std::placeholders::_1, std::placeholders::_2)},
C:\GTPS\Gurotopia\include\admin\admin.cpp:148: if (!peer_is_staff_role(actor->role) || actor->role > minimum_role)
C:\GTPS\Gurotopia\include\admin\admin.cpp:202: peer_is_staff_role(target.data->role), peer_is_super_staff_role(target.data->role), false);
C:\GTPS\Gurotopia\include\admin\admin.cpp:205: peer_is_staff_role(other->role), peer_is_super_staff_role(other->role), false);
C:\GTPS\Gurotopia\include\admin\admin.cpp:209: peer_is_staff_role(target.data->role), peer_is_super_staff_role(target.data->role), true);
C:\GTPS\Gurotopia\include\admin\admin.cpp:289: if (!peer_is_staff_role(actor->role))
C:\GTPS\Gurotopia\include\admin\admin.cpp:302: void handle_dialog(ENetEvent& event, const ::hPipe& hPipe)
C:\GTPS\Gurotopia\include\admin\admin.cpp:306: if (!peer_is_staff_role(actor->role))
C:\GTPS\Gurotopia\include\admin\admin.hpp:11: void handle_dialog(ENetEvent& event, const ::hPipe& hPipe);
C:\GTPS\Gurotopia\include\database\items.cpp:12: const ::item &id_to_item(u_short id) noexcept // @note std::out_of_range is handled
C:\GTPS\Gurotopia\include\database\items.cpp:23: void shift_pos(const std::vector<u_char> &data, u_int &pos, T &value) noexcept // @note std::out_of_range is handled
C:\GTPS\Gurotopia\include\database\items.cpp:37: void data_modify(std::vector<u_char> &data, const u_int &pos, const T &value) noexcept // @note std::out_of_range is handled
C:\GTPS\Gurotopia\include\database\items.hpp:5: FEET, FACE, HAND,
C:\GTPS\Gurotopia\include\database\items.hpp:12: WRENCH = 01,
C:\GTPS\Gurotopia\include\database\items.hpp:195: extern const ::item &id_to_item(u_short id) noexcept; // @note std::out_of_range is handled
C:\GTPS\Gurotopia\include\database\peer.cpp:203: this->slots[1ull] = ::slot{32, 1};   // @note wrench
C:\GTPS\Gurotopia\include\database\peer.hpp:69: constexpr bool peer_is_staff_role(u_char value) noexcept
C:\GTPS\Gurotopia\include\database\peer.hpp:76: constexpr bool peer_is_super_staff_role(u_char value) noexcept
C:\GTPS\Gurotopia\include\database\peer.hpp:155: * @brief add XP safely, this function also handles level up.
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp:35: if (pPeer->clothing[clothing::HAND] == 3066/* fire hose */)
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp:55: if (pPeer->clothing[clothing::HAND] == 5480) // @note Rayman's Fist
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp:93: if (pPeer->clothing[clothing::HAND] == 2952/*Digger's Spade*/)
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp:340: if (item.raw_name.find("Paint Bucket - ") != std::string::npos && pPeer->clothing[clothing::HAND] != 3494) throw std::runtime_error("you need a Paintbrush to apply paint!");
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp:646: return; // @note leave early else wrench will act as a block unlike fist which breaks. this is cause of send_gamePacket()
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp:677: block.state[2] = S_SPLICED; // @todo handle for multiple flags
C:\GTPS\Gurotopia\include\https\https.cpp:159: print("SSL handshake failed.");
C:\GTPS\Gurotopia\include\https\https.cpp:181: if (::shutdown(fd, 2) == SOCKET_ERROR) cross_log("failed to shutdown socket"); // @todo unsure if WSA can handle this.
C:\GTPS\Gurotopia\include\onVariant\RequestGazette.cpp:28: .add_textbox("The Phoenix has officially risen! For a limited time, a select group of classic `4Phoenix Items`` will make their grand comeback! Whether you missed them the first time or are looking to complete your fiery collection, now's your chance to grab them while they're still around! Check the store for more info on how to get your hands on these rare treasures!")
C:\GTPS\Gurotopia\include\onVariant\SetClothing.cpp:12: CL_Vec3f{pPeer->clothing[clothing::FEET], pPeer->clothing[clothing::FACE], pPeer->clothing[clothing::HAND]},
C:\GTPS\Gurotopia\include\onVariant\SetClothing.cpp:28: send_gamePacket(*peer, gamePacket); // @todo handle for 'p'
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== PEER INITIALIZATION ====="

===== PEER INITIALIZATION =====
PS C:\GTPS\Gurotopia> Get-Content .\include\database\peer.cpp
#include "pch.hpp"
#include "items.hpp"
#include "world.hpp"
#include "onVariant/SetClothing.hpp"
#include "onVariant/CountryState.hpp"
#include "onVariant/ConsoleMessage.hpp"
#include "commands/punch.hpp"
#include "tools/string.hpp"

#include "peer.hpp"

bool peer::exists(const std::string &growid)
{
    ::hStmt hStmt{ "SELECT 1 FROM peer WHERE growid = ? LIMIT 1" };

    MYSQL_BIND param = make_bind_in(growid); // WHERE
    hStmt.bind_param(&param);
    hStmt.execute();

    return (!mysql_stmt_store_result(hStmt.pStmt) && mysql_stmt_num_rows(hStmt.pStmt) > 0);
}

::blob slot::to_blob() const
{
    ::blob blob;
    blob.i16(this->id);
    blob.i16(this->count);

    return blob;
}

template<typename T>
void peer::mysql_insert(const std::string &column, const T &value)
{
    ::hStmt hStmt{ std::format("INSERT INTO peer ({}) VALUES (?)", column).c_str() };

    MYSQL_BIND param = make_bind_in(value); // VALUES
    hStmt.bind_param(&param);
    hStmt.execute();
}
template void peer::mysql_insert<signed>(const std::string&, const signed&);
template void peer::mysql_insert<unsigned>(const std::string&, const unsigned&);
template void peer::mysql_insert<float>(const std::string&, const float&);
template void peer::mysql_insert<std::string>(const std::string&, const std::string&);

template<typename T>
void peer::mysql_update(const std::string &column, const T &value)
{
    ::hStmt hStmt{ std::format("UPDATE peer SET {} = ? WHERE growid = ?", column).c_str() };

    MYSQL_BIND params[2] = {
        make_bind_in(value),       // SET
        make_bind_in(this->growid) // WHERE
    };
    hStmt.bind_param(params);
    hStmt.execute();
}
template void peer::mysql_update<signed>(const std::string&, const signed&);
template void peer::mysql_update<unsigned>(const std::string&, const unsigned&);
template void peer::mysql_update<long long>(const std::string&, const long long&);
template void peer::mysql_update<float>(const std::string&, const float&);
template void peer::mysql_update<std::string>(const std::string&, const std::string&);

template<typename T>
T peer::mysql_select(const std::string &column, const std::string &arg, bool by_user_id)
{
    T value{};
    ::hStmt hStmt{ std::format("SELECT {}({}) FROM peer WHERE {} = ? LIMIT 1", arg, column, by_user_id ? "uid" : "growid").c_str() };

    MYSQL_BIND param = by_user_id ? make_bind_in(this->user_id) : make_bind_in(this->growid); // WHERE
    hStmt.bind_param(&param);

    u_long length = 0;
    MYSQL_BIND result = make_bind_out(value);
    result.length = &length;
    mysql_stmt_bind_result(hStmt.pStmt, &result);

    hStmt.execute();
    hStmt.fetch();
    if constexpr (std::is_same_v<T, std::string>)
        value.resize(length);

    return value;
}
/* since we will only select during mysql_select_all */ // @note add templates here if use select outside of this file.
template std::string peer::mysql_select<std::string>(const std::string&, const std::string&, bool); // @note tile_change.cpp (World Lock owner name)

void peer::mysql_select_all(bool by_user_id)
{
    this->user_id    = this->mysql_select<signed>("uid", "", by_user_id);
    this->growid     = this->mysql_select<std::string>("growid", "", by_user_id);
    this->password   = this->mysql_select<std::string>("password", "", by_user_id);
        const unsigned role_value =
                this->mysql_select<unsigned>("role", "", by_user_id);

    this->role = role_value <= PLAYER ? static_cast<u_char>(role_value) : PLAYER;
    this->created_at = this->mysql_select<std::time_t>("created_at", "UNIX_TIMESTAMP", by_user_id);
    this->gems       = this->mysql_select<long long>("gems", "", by_user_id);
    this->wl_storage = this->mysql_select<signed>("wl_storage", "", by_user_id);
    this->level[0]   = this->mysql_select<signed>("level", "", by_user_id);
    this->level[1]   = this->mysql_select<signed>("xp", "", by_user_id);

    auto inventory = this->mysql_select<::blob>("inventory", "", by_user_id);

    if (inventory.size() >= sizeof(int) + sizeof(short))
    {
        int pos{};
        inventory.read_i32(this->slot_size, pos);

        short size{};
        inventory.read_i16(size, pos);

        this->slots.resize(size);

        for (::slot &slot : this->slots)
        {
            if (!inventory.read_i16(slot.id, pos)) break;
            if (!inventory.read_i16(slot.count, pos)) break;
        }
    }
    else
    {
        this->slot_size = 16;
        this->slots.resize(3ull);
        this->slots[0ull] = ::slot{18, 1};
        this->slots[1ull] = ::slot{32, 1};
        this->slots[2ull] = ::slot{9640, 1};

        this->mysql_update_all();
    }
}
::blob peer::serialize_inventory() const
{
    ::blob blob{};
    blob.i32(this->slot_size);
    blob.i16(this->slots.size());
    for (const ::slot &slot : this->slots)
    {
        blob.push_back(slot.to_blob());
    }
    return blob;
}

void peer::mysql_update_all()
{
    if (this->growid.empty()) return;

    ::hStmt hStmt{
    "UPDATE peer SET inventory = ?, gems = ?, level = ?, "
    "xp = ?, wl_storage = ?, role = ? WHERE growid = ?"
};
    const ::blob inventory = this->serialize_inventory();
    const int level_value = this->level[0], xp_value = this->level[1];
        const unsigned role_value = static_cast<unsigned>(this->role);

        MYSQL_BIND params[7] = {
                make_bind_in(inventory),
                make_bind_in(this->gems),
                make_bind_in(level_value),
                make_bind_in(xp_value),
                make_bind_in(this->wl_storage),
                make_bind_in(role_value),
                make_bind_in(this->growid)
        };
    hStmt.bind_param(params);
    hStmt.execute();
}

bool peer::load(const std::string &growid, const std::string password)
{
    this->growid = growid;
    if (!this->exists(growid))
    {
        return false;
    }
    this->mysql_select_all(false);
    if (password.empty() || this->password != password)
    {
        return false;
    }
    return true;
}

bool peer::load_by_uid(int uid)
{
    this->user_id = uid;
    this->mysql_select_all(true);
    return !this->growid.empty();
}

bool peer::create_account(const std::string &growid, const std::string &password)
{
    this->growid = growid;
    if (this->exists(growid))
    {
        return false;
    }
    this->mysql_insert("growid", growid);
    this->mysql_update("password", password);

    this->slots.resize(3ull); // @note default starter items
    this->slots[0ull] = ::slot{18, 1};   // @note fist
    this->slots[1ull] = ::slot{32, 1};   // @note wrench
    this->slots[2ull] = ::slot{9640, 1}; // @note my first world lock

    this->mysql_update_all();
    this->mysql_select_all(false);
    return true;
}

peer::~peer()
{
    this->mysql_update_all();
}

u_short peer::emplace(::slot slot)
{
    auto it = std::ranges::find(this->slots, slot.id, &::slot::id);

    if (it != this->slots.end())
    {
        const u_short excess = std::max(0, (it->count + slot.count) - 200);
        it->count = std::min(it->count + slot.count, 200);
        if (it->count == 0)
        {
            const ::item &item = id_to_item(it->id);
            if (item.cloth_type != clothing::NONE) this->clothing[item.cloth_type] = 0;
        }
        return excess;
    }
    this->slots.emplace_back(std::move(slot)); // @note no such item in inventory, so we create a new entry.
    return 0;
}

u_short peer::have_slot(::slot slot)
{
    auto it = std::ranges::find(this->slots, slot.id, &::slot::id);

    if (it != this->slots.end())
        return it->count;
    return 0;
}

void peer::add_xp(ENetEvent &event, u_short value)
{
    u_short &lvl = this->level.front();
    u_short &xp = this->level.back() += value; // @note factor the new xp amount

    for (; lvl < 125; )
    {
        u_short xp_formula = 50 * (lvl * lvl + 2); // @author https://www.growtopiagame.com/forums/member/553046-kasete
        if (xp < xp_formula) break;

        xp -= xp_formula;
        lvl++;

        if (lvl == 50)
        {
            modify_item_inventory(event, ::slot{1400, 1}); // @note Mini Growtopian
            /* @todo based on account age give peer other items... */
        }
        if (lvl == 125) on::CountryState(event);
        send_varlist(event.peer, { "OnPlayerLeveledUp", (unsigned)lvl });
        send_varlist(event.peer, { "OnParticleEffect", 46u, CL_Vec2f{this->pos.x + 16.0f, this->pos.y + 16.0f}, 0.0f, 0.0f });

        std::string message = std::format("{} is now level {}!", this->display_growid, lvl);
        send_varlist(event.peer, { "OnTalkBubble", this->netid, message, 0u });
        on::ConsoleMessage(event.peer, message);
    }
}

void peer::update_effects()
{
    this->punch_effect = 0;
    for (float cloth : this->clothing)
    {
        u_char punch_id = get_punch_id((u_int)cloth);
        if (punch_id != 0) // @note an actual change rather than no effect.
            this->punch_effect = punch_id;
    }
}

ENetHost *host;

void safe_disconnect_peers(int signal)
{
    peers("", PeerSearch::EVERYONE, [](auto *p) { enet_peer_disconnect(p, 0); });
    enet_host_flush(host);
}

::blob compressMessage(const gameMessage &gameMessage)
{
    ::blob blob{};

    blob.i32(gameMessage.packet_create);
    for (char c : gameMessage.message) blob.u8(c);
    blob.u8(gameMessage.terminator);

    return blob;
}

gamePacket make_gamePacket(const enet_uint8 *data)
{
    const int   *i32 = reinterpret_cast<const int*>(data);
    const u_int *u32 = reinterpret_cast<const u_int*>(data);
    const float *f32 = reinterpret_cast<const float*>(data);

    return gamePacket{
        .type  = i32[1],
        .netid = i32[2],
        .uid   = i32[3],
        .state = i32[4],
        .count = f32[5],
        .id    = i32[6],
        .pos   = ::pos{f32[7], f32[8]},
        .speed = ::pos{f32[9], f32[10]},
        .idk   = f32[11],
        .punch = ::pos{i32[12], i32[13]},
        .size  = u32[14]
    };
}

::blob compress_state(const gamePacket &gamePacket)
{
    ::blob blob{};

    blob.i32(gamePacket.packet_create);
    blob.i32(gamePacket.type);
    blob.i32(gamePacket.netid);
    blob.i32(gamePacket.uid);
    blob.i32(gamePacket.state);
    blob.f32(gamePacket.count);
    blob.i32(gamePacket.id);
    blob.f32(gamePacket.pos.x);
    blob.f32(gamePacket.pos.y);
    blob.f32(gamePacket.speed.x);
    blob.f32(gamePacket.speed.y);
    blob.f32(gamePacket.idk);
    blob.i32(gamePacket.punch.x);
    blob.i32(gamePacket.punch.y);
    blob.i32(gamePacket.size);

    return blob;
}

void send_inventory_state(ENetEvent &event)
{
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    ::blob blob = compress_state(::gamePacket{
        .type = 0x09, // @note PACKET_SEND_INVENTORY_STATE
        .netid = pPeer->netid,
        .state = (int)gamePacketState::EXTENDED
    });
    blob.u8(0x01); // @note enable flag for big backpack

    blob.push_back(pPeer->serialize_inventory());

    ENetPacket *packet = enet_packet_create(blob.data().data(), blob.size(), ENET_PACKET_FLAG_RELIABLE);
        if (enet_peer_send(event.peer, 0, packet)) enet_packet_destroy(packet);
}
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== ENTER GAME ====="

===== ENTER GAME =====
PS C:\GTPS\Gurotopia> Get-Content .\include\action\enter_game.cpp
#include "pch.hpp"

#include "onVariant/RequestWorldSelectMenu.hpp"
#include "onVariant/RequestGazette.hpp"
#include "onVariant/ConsoleMessage.hpp"
#include "onVariant/SetBux.hpp"
#include "automate/holiday.hpp"

#include "enter_game.hpp"

void action::enter_game(ENetEvent& event, const std::string& header)
{
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    pPeer->display_growid = make_peer_display_growid(pPeer->role, pPeer->growid);
    on::ConsoleMessage(event.peer,
        std::format("Welcome back, {}. No friends are online.",
            pPeer->display_growid
        )
    );
    on::ConsoleMessage(event.peer, holiday_greeting().second);
    if (active_holiday == holiday::HALLOWEEN)
    {
        on::ConsoleMessage(event.peer, "Growtopians have collectively released `20`` `9Corrupted Souls`` from the Tomb of Growganoth! Growganoth is pleased and unleashes the corrupted `2Tarantula Legs`` upon Growtopia!");
        send_varlist(event.peer, { "OnEventButtonDataSet", "HalloweenButton", 1, /*@todo*/ });
    }
    on::ConsoleMessage(event.peer, "`3Today is (null)!`` Your first (null) quest will give 1 `2Growtoken`` and all (null) quests will give 25% bonus points!");
    on::ConsoleMessage(event.peer, "`5Personal Settings active:`` `#Punch Joystick enabled``");

    send_inventory_state(event);

    on::SetBux(event);
    send_varlist(event.peer, { "OnSetVouchers", 0 });
    send_varlist(event.peer, { "SetHasGrowID", 1u, pPeer->growid.c_str(), "" });
    {
        std::tm time = localtime();

        send_varlist(event.peer, {
            "OnTodaysDate",
            time.tm_mon + 1,
            time.tm_mday,
            0u, // @todo
            0u // @todo
        });
    } // @note delete time

    send_varlist(event.peer, { "OnRequestHoustonPricing" });

    on::RequestWorldSelectMenu(event);
    on::RequestGazette(event);

    send_data(*event.peer, compress_state(::gamePacket{ .type = 0x16 /*PACKET_PING_REQUEST*/ }));
    if (pPeer->game_version >= 5.47)
    {
        send_varlist(event.peer, {
            "OnSetFeatureEnableFlags",
            "EAcGAQoDEAQRBQ0JCAwCDw4="
        });
    }
}
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== INPUT ====="

===== INPUT =====
PS C:\GTPS\Gurotopia> Get-Content .\include\action\input.cpp
#include "pch.hpp"

#include "commands/__command.hpp"
#include "onVariant/ConsoleMessage.hpp"
#include "tools/time.hpp"
#include "tools/random.hpp"

#include "input.hpp"

#include <algorithm>

void action::input(ENetEvent& event, const std::string& header)
{
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    ::hPipe hPipe{ header };
    std::string text = hPipe["text"];

    if (text.empty() || text.front() == '\r' || std::ranges::all_of(text, ::isspace)) return;

    text.erase(text.begin(), std::find_if_not(text.begin(), text.end(), ::isspace));
    text.erase(std::find_if_not(text.rbegin(), text.rend(), ::isspace).base(), text.end());
    if (text.empty()) return; // @note we recheck if empty since we did trimming.

    const u_int now = ticks();
    pPeer->messages.push_back(now);
    if (pPeer->messages.size() > 5) pPeer->messages.pop_front();
    if (pPeer->messages.size() == 5 && now - pPeer->messages.front() <= 5)
    {
        on::ConsoleMessage(event.peer,
            "`6>>`4Spam detected! ``Please wait a bit before typing anything else.  "
            "Please note, any form of bot/macro/auto-paste will get all your accounts banned, so don't do it!");
    }
    else if (text.starts_with('/'))
    {
        send_gameMessage(event.peer, {.message = std::format("action|log\nmsg|`6{}``", text)});

        std::string_view command = text;
        command = command.substr(0, command.find(' '));

        if (pPeer->muted && command != "/admin")
        {
            on::ConsoleMessage(event.peer, "`4You are muted and cannot use chat commands.``");
            return;
        }
        if (auto it = cmd_pool.find(command); it != cmd_pool.end())
            it->second(event, std::move(text));
        else
            send_gameMessage(event.peer, {.message = "action|log\nmsg|`4Unknown command.`` Enter `$/?`` for a list of valid commands."});
    }
    else
    {
        if (pPeer->muted)
        {
            on::ConsoleMessage(event.peer, "`4You are muted and cannot chat.``");
            return;
        }
        if (pPeer->state & S_DUCT_TAPE)
        {
            for (char &c : text)
                if (c != ' ') c = (RandomRange(1, 3) == 1) ? 'm' : 'f';
        }
        const std::string &player_chat = std::format("CP:0_PL:0_OID:_player_chat={}", text);
        const std::string &message = std::format("CP:0_PL:0_OID:_CT:[W]_ `6<{}>`` `$`${}````", pPeer->display_growid, text);
        peers(pPeer->recent_worlds.back(), PeerSearch::WORLD, [&event, &pPeer, player_chat, message](ENetPeer *p)
        {
            send_varlist(p, { "OnTalkBubble", pPeer->netid, player_chat, 0u });
            on::ConsoleMessage(p, message, pPeer->netid);
        });
    }
}

PS C:\GTPS\Gurotopia> Get-Content .\include\action\worldlock_storage_modify_amount.cpp

#include "pch.hpp"

#include <algorithm>
#include <charconv>
#include <limits>

#include "onVariant/ConsoleMessage.hpp"
#include "onVariant/WorldLockStorageResponse.hpp"
#include "onVariant/EventButtonDataSet.hpp"
#include "tools/conversions.hpp"

#include "worldlock_storage_getpage.hpp"
#include "worldlock_storage_modify_amount.hpp"

void action::worldlock_storage_modify_amount(ENetEvent& event, const std::string& header)
{
    ::peer* pPeer = static_cast<::peer*>(event.peer->data);
    if (pPeer == nullptr) return;

    const ::hPipe hPipe{ header };

    // Strict integer parsing: reject malformed input and overflow.
    auto parse_integer = [](const std::string& text, int& value) -> bool
    {
        if (text.empty()) return false;

        const char* begin = text.data();
        const char* end = begin + text.size();

        const auto result = std::from_chars(begin, end, value);

        return result.ec == std::errc{} && result.ptr == end;
    };

    int amount{};
    int type{};

    if (!parse_integer(hPipe["amount"], amount) || amount <= 0)
        return;

    if (!parse_integer(hPipe["type"], type))
        return;

    if (type < -1 || type > 1)
        return;

    auto refresh_storage = [&]()
    {
        on::EventButtonDataSet(event, true);
        on::EventButtonDataSet(event, false);

        send_varlist(event.peer, {
            "OnActiveAuctionUpdate",
            "{\"Active\":false}"
        });

        on::WorldLockStorageResponse(event.peer);
    };

    // Preserve the existing refresh-only behavior.
    if (type == 0)
    {
        refresh_storage();
        return;
    }

    auto get_inventory_count = [&](short item_id, int& count) -> bool
    {
        const auto it = std::ranges::find(
            pPeer->slots,
            item_id,
            &::slot::id
        );

        count = (it == pPeer->slots.end())
            ? 0
            : static_cast<int>(it->count);

        return count >= 0 && count <= 200;
    };

    int owned_wl{};
    int owned_dl{};
    int owned_bgl{};

    if (!get_inventory_count(242, owned_wl))
        return;

    if (!get_inventory_count(1796, owned_dl))
        return;

        if (!get_inventory_count(7188, owned_bgl))
                return;

    // The client uses 1100090 as the Store All request value.
    // It is a command sentinel, NOT the literal amount of WL.
    constexpr int STORE_ALL_AMOUNT = 1100090;

    const bool store_all =
        (type == 1 && amount == STORE_ALL_AMOUNT);

    // Resolve Store All using the actual server-side inventory.
    if (store_all)
    {
        const long long total_value =
            static_cast<long long>(owned_bgl) * BLUE_GEM_LOCK_VALUE +
            static_cast<long long>(owned_dl) * DIAMOND_LOCK_VALUE +
            static_cast<long long>(owned_wl);

        if (total_value > std::numeric_limits<int>::max())
            return;

        amount = static_cast<int>(total_value);
    }

    // Reject corrupted balances.
    if (pPeer->wl_storage < 0)
        return;

    // Empty Store All: do not modify the balance or inventory.
    // Still refresh the interface so the button does not appear stuck.
    if (amount <= 0)
    {
        if (store_all)
            refresh_storage();

        return;
    }

    // Validate balance after resolving the actual Store All amount.
    if (type == 1)
    {
        if (amount > std::numeric_limits<int>::max() - pPeer->wl_storage)
            return;
    }
    else
    {
        if (amount > pPeer->wl_storage)
            return;
    }

    // Deposit: available inventory counts.
    // Withdrawal: remaining capacity in each inventory stack.
    const int wl_capacity = (type == 1)
        ? owned_wl
        : 200 - owned_wl;

    const int dl_capacity = (type == 1)
        ? owned_dl
        : 200 - owned_dl;

    const int bgl_capacity = (type == 1)
        ? owned_bgl
        : 200 - owned_bgl;

    int bgl{};
    int dl{};
    int wl{};
    int remaining = amount;

    if (store_all)
    {
        // Store All must transfer every owned lock, not reconstruct
        // a requested denomination from the sentinel.
        bgl = owned_bgl;
        dl = owned_dl;
        wl = owned_wl;

        remaining = 0;
    }
    else
    {
        // Normal deposit / withdrawal denomination conversion.
        bgl = std::min<int>(
            remaining / BLUE_GEM_LOCK_VALUE,
            bgl_capacity
        );
        remaining -= bgl * BLUE_GEM_LOCK_VALUE;

        dl = std::min<int>(
            remaining / DIAMOND_LOCK_VALUE,
            dl_capacity
        );
        remaining -= dl * DIAMOND_LOCK_VALUE;

        wl = std::min<int>(
            remaining,
            wl_capacity
        );
        remaining -= wl;
    }

    // Never execute an incomplete transaction.
    if (remaining != 0)
        return;

    // All item counts are now verified to fit within signed short
    // and the inventory's 0..200 stack limit.
    std::string collected;

    if (bgl > 0)
    {
        collected = std::format(
            "{} `2Blue Gem Lock`` and {} `2Diamond Lock`` and {} `2World Lock``",
            bgl, dl, wl
        );
    }
    else if (dl > 0)
    {
        collected = std::format(
            "{} `2Diamond Lock`` and {} `2World Lock``",
            dl, wl
        );
    }
    else if (wl > 0)
    {
        collected = std::format(
            "{} `2World Lock``",
            wl
        );
    }

    const short direction = (type == 1) ? -1 : 1;

    // Apply inventory changes only after every validation has passed.
    if (bgl > 0)
    {
        modify_item_inventory(
            event,
            ::slot(7188, static_cast<short>(direction * bgl))
        );
    }

    if (dl > 0)
    {
        modify_item_inventory(
            event,
            ::slot(1796, static_cast<short>(direction * dl))
        );
    }

    if (wl > 0)
    {
        modify_item_inventory(
            event,
            ::slot(242, static_cast<short>(direction * wl))
        );
    }

    // Change the storage balance only after inventory changes.
    if (type == 1)
        pPeer->wl_storage += amount;
    else
        pPeer->wl_storage -= amount;

    if (type == -1)
    {
        const std::string message = std::format(
            "You collected {}.",
            collected
        );

        send_varlist(event.peer, {
            "OnTalkBubble",
            pPeer->netid,
            message,
            0u,
            1u
        });

        on::ConsoleMessage(event.peer, message);
    }

    refresh_storage();
}
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== INVENTORY IMPLEMENTATION ====="

===== INVENTORY IMPLEMENTATION =====
PS C:\GTPS\Gurotopia> Get-Content .\include\database\peer.cpp |
>>     Select-Object -Skip 65 -First 160
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
    }
            // Repair mandatory starter tools for every account, regardless of role.
    bool inventory_changed = false;

    auto ensure_required_item =
        [this, &inventory_changed](short item_id)
    {
        auto it = std::ranges::find(
            this->slots,
            item_id,
            &::slot::id
        );

        if (it == this->slots.end())
        {
            this->slots.emplace_back(item_id, 1);
            inventory_changed = true;
        }
        else if (it->count <= 0)
        {
            it->count = 1;
            inventory_changed = true;
        }
    };

    // Fist / Hand
    ensure_required_item(18);

    // Wrench
    ensure_required_item(32);

    // Preserve existing inventory; expand capacity only when necessary.
    if (this->slot_size < static_cast<int>(this->slots.size()))
    {
        this->slot_size = static_cast<int>(this->slots.size());
        inventory_changed = true;
    }

    // Persist the repair so it is not repeated on every login.
    if (inventory_changed)
        this->mysql_update_all();
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
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== INVENTORY MODIFY ====="

===== INVENTORY MODIFY =====
PS C:\GTPS\Gurotopia> Get-ChildItem .\include -Recurse -File -Filter "*.cpp" |
>>     Select-String -Pattern 'modify_item_inventory' -Context 3,10

  include\action\buy.cpp:130:                    pPeer->slot_size += 10;
  include\action\buy.cpp:131:                    send_inventory_state(event); // @note update the new slots
  include\action\buy.cpp:132:                }
> include\action\buy.cpp:133:                else modify_item_inventory(event, {item.first, item.second});
  include\action\buy.cpp:134:                received.append(std::format("{}, ", raw_name)); // @todo add green text to
 rare items, or something cool.
  include\action\buy.cpp:135:            }
  include\action\buy.cpp:136:            send_varlist(event.peer, { "OnStorePurchaseResult", (_tab < 5) ?
  include\action\buy.cpp:137:                std::format(
  include\action\buy.cpp:138:                    "You've purchased `0{}`` for `${}`` Gems.\nYou have `${}`` Gems left.\
n\n`5Received: ```0{}``",
  include\action\buy.cpp:139:                    shouhin.name, shouhin.cost, pPeer->gems -= shouhin.cost, received) :
  include\action\buy.cpp:140:                std::format(
  include\action\buy.cpp:141:                    "You've purchased `0{}`` for `${}`` `2Growtokens``.\nYou have `${}`` `
2Growtokens`` left.\n\n`5Received: ```0{}``",
  include\action\buy.cpp:142:                    shouhin.name, growtoken_cost, growtoken->count - growtoken_cost, recei
ved)
  include\action\buy.cpp:143:            });
  include\action\buy.cpp:146:                pPeer->mysql_update("gems", pPeer->gems);
  include\action\buy.cpp:147:                on::SetBux(event);
  include\action\buy.cpp:148:            }
> include\action\buy.cpp:149:            else modify_item_inventory(event, ::slot(growtoken->id, -growtoken_cost));
  include\action\buy.cpp:150:            break;
  include\action\buy.cpp:151:        }
  include\action\buy.cpp:152:    }
  include\action\buy.cpp:153:}
  include\action\worldlock_storage_modify_amount.cpp:226:    // Apply inventory changes only after every validation has
 passed.
  include\action\worldlock_storage_modify_amount.cpp:227:    if (bgl > 0)
  include\action\worldlock_storage_modify_amount.cpp:228:    {
> include\action\worldlock_storage_modify_amount.cpp:229:        modify_item_inventory(
  include\action\worldlock_storage_modify_amount.cpp:230:            event,
  include\action\worldlock_storage_modify_amount.cpp:231:            ::slot(7188, static_cast<short>(direction * bgl))
  include\action\worldlock_storage_modify_amount.cpp:232:        );
  include\action\worldlock_storage_modify_amount.cpp:233:    }
  include\action\worldlock_storage_modify_amount.cpp:234:
  include\action\worldlock_storage_modify_amount.cpp:235:    if (dl > 0)
  include\action\worldlock_storage_modify_amount.cpp:236:    {
> include\action\worldlock_storage_modify_amount.cpp:237:        modify_item_inventory(
  include\action\worldlock_storage_modify_amount.cpp:238:            event,
  include\action\worldlock_storage_modify_amount.cpp:239:            ::slot(1796, static_cast<short>(direction * dl))
  include\action\worldlock_storage_modify_amount.cpp:240:        );
  include\action\worldlock_storage_modify_amount.cpp:241:    }
  include\action\worldlock_storage_modify_amount.cpp:242:
  include\action\worldlock_storage_modify_amount.cpp:243:    if (wl > 0)
  include\action\worldlock_storage_modify_amount.cpp:244:    {
> include\action\worldlock_storage_modify_amount.cpp:245:        modify_item_inventory(
  include\action\worldlock_storage_modify_amount.cpp:246:            event,
  include\action\worldlock_storage_modify_amount.cpp:247:            ::slot(242, static_cast<short>(direction * wl))
  include\action\worldlock_storage_modify_amount.cpp:248:        );
  include\action\worldlock_storage_modify_amount.cpp:249:    }
  include\action\worldlock_storage_modify_amount.cpp:250:
  include\action\worldlock_storage_modify_amount.cpp:251:    // Change the storage balance only after inventory changes
.
  include\action\worldlock_storage_modify_amount.cpp:252:    if (type == 1)
  include\action\worldlock_storage_modify_amount.cpp:253:        pPeer->wl_storage += amount;
  include\action\worldlock_storage_modify_amount.cpp:254:    else
  include\action\worldlock_storage_modify_amount.cpp:255:        pPeer->wl_storage -= amount;
  include\action\dialog_return\drop_item.cpp:52:    }
  include\action\dialog_return\drop_item.cpp:53:
  include\action\dialog_return\drop_item.cpp:54:    const short count = std::min(requested_count, slot_it->count);
> include\action\dialog_return\drop_item.cpp:55:    modify_item_inventory(event, ::slot(item_id, -count));
  include\action\dialog_return\drop_item.cpp:56:
  include\action\dialog_return\drop_item.cpp:57:    const float x_neighbor = pPeer->facing_left ? pPeer->pos.x - 32 : p
Peer->pos.x + 32;
  include\action\dialog_return\drop_item.cpp:58:    add_drop(event, { item_id, count }, { x_neighbor, pPeer->pos.y }, *
world);
  include\action\dialog_return\drop_item.cpp:59:}
  include\action\dialog_return\find_item.cpp:30:        return;
  include\action\dialog_return\find_item.cpp:31:    }
  include\action\dialog_return\find_item.cpp:32:
> include\action\dialog_return\find_item.cpp:33:    modify_item_inventory(event, ::slot(parsed_id, 200));
  include\action\dialog_return\find_item.cpp:34:}
  include\action\dialog_return\trash_item.cpp:49:    }
  include\action\dialog_return\trash_item.cpp:50:
  include\action\dialog_return\trash_item.cpp:51:    const short count = std::min(requested_count, slot_it->count);
> include\action\dialog_return\trash_item.cpp:52:    modify_item_inventory(event, ::slot(item_id, -count));
  include\action\dialog_return\trash_item.cpp:53:    on::ConsoleMessage(event.peer, std::format("{} `w{}`` recycled, `w
0`` gems earned.", count, item.raw_name));
  include\action\dialog_return\trash_item.cpp:54:}
  include\database\peer.cpp:294:
  include\database\peer.cpp:295:        if (lvl == 50)
  include\database\peer.cpp:296:        {
> include\database\peer.cpp:297:            modify_item_inventory(event, ::slot{1400, 1}); // @note Mini Growtopian
  include\database\peer.cpp:298:            /* @todo based on account age give peer other items... */
  include\database\peer.cpp:299:        }
  include\database\peer.cpp:300:        if (lvl == 125) on::CountryState(event);
  include\database\peer.cpp:301:        send_varlist(event.peer, { "OnPlayerLeveledUp", (unsigned)lvl });
  include\database\peer.cpp:302:        send_varlist(event.peer, { "OnParticleEffect", 46u, CL_Vec2f{this->pos.x + 16.0
f, this->pos.y + 16.0f}, 0.0f, 0.0f });
  include\database\peer.cpp:303:
  include\database\peer.cpp:304:        std::string message = std::format("{} is now level {}!", this->display_growid,
lvl);
  include\database\peer.cpp:305:        send_varlist(event.peer, { "OnTalkBubble", this->netid, message, 0u });
  include\database\peer.cpp:306:        on::ConsoleMessage(event.peer, message);
  include\database\peer.cpp:307:    }
  include\database\world.cpp:410:       send_gamePacket(*event.peer, gamePacket);
  include\database\world.cpp:411:}
  include\database\world.cpp:412:
> include\database\world.cpp:413:u_short modify_item_inventory(ENetEvent &event, ::slot slot)
  include\database\world.cpp:414:{
  include\database\world.cpp:415:    ::peer *pPeer = static_cast<::peer*>(event.peer->data);
  include\database\world.cpp:416:
  include\database\world.cpp:417:    ::gamePacket gamePacket{.id = slot.id};
  include\database\world.cpp:418:    if (slot.count < 0) gamePacket.type = (slot.count*-1 << 16) | 0x000d; // @noote 0x
00{}000d
  include\database\world.cpp:419:    else                gamePacket.type = (slot.count    << 24) | 0x000d; // @noote 0x
{}00000d
  include\database\world.cpp:420:    send_data(*event.peer, compress_state(gamePacket)); // @note only the player whose
 backpack changes
  include\database\world.cpp:421:
  include\database\world.cpp:422:    return pPeer->emplace(::slot(slot.id, slot.count));
  include\database\world.cpp:423:}
  include\database\world.cpp:569:    if (++pPeer->fires_removed % 100 == 0)
  include\database\world.cpp:570:    {
  include\database\world.cpp:571:        on::ConsoleMessage(event.peer, "`oI'm so good at fighting fires, I rescused th
is `2Highly Combustible Box``!");
> include\database\world.cpp:572:        modify_item_inventory(event, {3090/*Combustible Box*/, 1});
  include\database\world.cpp:573:    }
  include\database\world.cpp:574:    pPeer->add_xp(event, 1);
  include\database\world.cpp:575:}
  include\database\world.cpp:576:
  include\database\world.cpp:577:void fireworks(ENetEvent &event, const ::pos &pos)
  include\database\world.cpp:578:{
  include\database\world.cpp:579:    int type  [3]{ RandomRange(0x25, 0x28), RandomRange(0x25, 0x28), RandomRange(0x25,
 0x28) };
  include\database\world.cpp:580:    int offset[3]{ RandomRange(260, 2200), RandomRange(260, 2200), RandomRange(260, 22
00) };
  include\database\world.cpp:581:
  include\database\world.cpp:582:    send_particle_effect(event, pos, {0xb3, type[0]}, 0xc8*0, offset[0]);
  include\gamePacket\item_activate.cpp:34:
  include\gamePacket\item_activate.cpp:35:        if (item->id == 242 && item->count >= 100)
  include\gamePacket\item_activate.cpp:36:        {
> include\gamePacket\item_activate.cpp:37:            const u_short nokori = modify_item_inventory(event, {1796, 1});
  include\gamePacket\item_activate.cpp:38:            if (nokori == 0)
  include\gamePacket\item_activate.cpp:39:            {
> include\gamePacket\item_activate.cpp:40:                modify_item_inventory(event, {item->id, -100});
  include\gamePacket\item_activate.cpp:41:                const std::string compressed = "You compressed 100 `2World Lo
ck`` into a `2Diamond Lock``!";
  include\gamePacket\item_activate.cpp:42:                send_varlist(event.peer, { "OnTalkBubble", pPeer->netid, comp
ressed, 0u, 1u });
  include\gamePacket\item_activate.cpp:43:                on::ConsoleMessage(event.peer, compressed);
  include\gamePacket\item_activate.cpp:44:            }
  include\gamePacket\item_activate.cpp:45:        }
  include\gamePacket\item_activate.cpp:46:        else if (item->id == 1796 && item->count >= 1)
  include\gamePacket\item_activate.cpp:47:        {
> include\gamePacket\item_activate.cpp:48:            const u_short nokori = modify_item_inventory(event, {242, 100});
  include\gamePacket\item_activate.cpp:49:            short hyaku = 100 - nokori;
  include\gamePacket\item_activate.cpp:50:            if (hyaku == 100)
  include\gamePacket\item_activate.cpp:51:            {
> include\gamePacket\item_activate.cpp:52:                modify_item_inventory(event, {item->id, -1});
  include\gamePacket\item_activate.cpp:53:                const std::string shattered = "You shattered a `2Diamond Lock
`` into 100 `2World Lock``!";
  include\gamePacket\item_activate.cpp:54:                send_varlist(event.peer, { "OnTalkBubble", pPeer->netid, shat
tered, 0u, 1u });
  include\gamePacket\item_activate.cpp:55:                on::ConsoleMessage(event.peer, shattered);
  include\gamePacket\item_activate.cpp:56:            }
> include\gamePacket\item_activate.cpp:57:            else modify_item_inventory(event, ::slot(242, -hyaku)); // @note
return wls if can't hold 100
  include\gamePacket\item_activate.cpp:58:        }
  include\gamePacket\item_activate.cpp:59:        else if (item->id == 1486 && item->count >= 100)
  include\gamePacket\item_activate.cpp:60:        {
> include\gamePacket\item_activate.cpp:61:            const u_short nokori = modify_item_inventory(event, {6802, 1});
  include\gamePacket\item_activate.cpp:62:            if (nokori == 0)
> include\gamePacket\item_activate.cpp:63:                modify_item_inventory(event, {item->id, -100});
  include\gamePacket\item_activate.cpp:64:        }
  include\gamePacket\item_activate.cpp:65:        else if (item->id == 6802 && item->count >= 1)
  include\gamePacket\item_activate.cpp:66:        {
> include\gamePacket\item_activate.cpp:67:            const u_short nokori = modify_item_inventory(event, {1486, 100});
  include\gamePacket\item_activate.cpp:68:            short hyaku = 100 - nokori;
  include\gamePacket\item_activate.cpp:69:            if (hyaku == 100)
> include\gamePacket\item_activate.cpp:70:                modify_item_inventory(event, {item->id, -1});
  include\gamePacket\item_activate.cpp:71:            else
> include\gamePacket\item_activate.cpp:72:                modify_item_inventory(event, ::slot(1486, -hyaku)); // @note
return growtoken if can't hold 100
  include\gamePacket\item_activate.cpp:73:        }
  include\gamePacket\item_activate.cpp:74:    }
  include\gamePacket\item_activate.cpp:75:}
  include\gamePacket\tile_change.cpp:267:                        send_gameMessage(peer, {.message = std::format("action
|log\n{}", message.c_str())});
  include\gamePacket\tile_change.cpp:268:                    });
  include\gamePacket\tile_change.cpp:269:                }
> include\gamePacket\tile_change.cpp:270:                if (++pPeer->gbc_pity % 100 == 0) modify_item_inventory(event,
 ::slot{9350, 1});
  include\gamePacket\tile_change.cpp:271:            }
  include\gamePacket\tile_change.cpp:272:            else if (item.type == type::LOCK && !is_tile_lock(item.id))
  include\gamePacket\tile_change.cpp:273:            {
  include\gamePacket\tile_change.cpp:274:                pPeer->display_growid = make_peer_display_growid(pPeer->role,
pPeer->growid);
  include\gamePacket\tile_change.cpp:275:                on::NameChanged(event);
  include\gamePacket\tile_change.cpp:276:
  include\gamePacket\tile_change.cpp:277:                world->owner = 0; // @todo have a seperate thing for 'range_lo
ck'
  include\gamePacket\tile_change.cpp:278:            }
  include\gamePacket\tile_change.cpp:279:
  include\gamePacket\tile_change.cpp:280:            if (item.cat == CAT_RETURN)
  include\gamePacket\tile_change.cpp:507:            }
  include\gamePacket\tile_change.cpp:508:            send_tile_update(event, std::move(gamePacket), block, *world);
  include\gamePacket\tile_change.cpp:509:
> include\gamePacket\tile_change.cpp:510:            modify_item_inventory(event, ::slot(item.id, -1));
  include\gamePacket\tile_change.cpp:511:            pPeer->add_xp(event, 1);
  include\gamePacket\tile_change.cpp:512:            return;
  include\gamePacket\tile_change.cpp:513:        }
  include\gamePacket\tile_change.cpp:514:        else if (gamePacket.id == 32)
  include\gamePacket\tile_change.cpp:515:        {
  include\gamePacket\tile_change.cpp:516:            switch (item.type)
  include\gamePacket\tile_change.cpp:517:            {
  include\gamePacket\tile_change.cpp:518:                case type::LOCK:
  include\gamePacket\tile_change.cpp:519:                {
  include\gamePacket\tile_change.cpp:520:                    if (is_tile_lock(item.id)) break; // @todo seperate area f
or 'range_lock'
  include\gamePacket\tile_change.cpp:687:                }
  include\gamePacket\tile_change.cpp:688:                if (update_tile)
  include\gamePacket\tile_change.cpp:689:                {
> include\gamePacket\tile_change.cpp:690:                    modify_item_inventory(event, ::slot(gamePacket.id, -1));
  include\gamePacket\tile_change.cpp:691:                    send_tile_update(event, std::move(gamePacket), block, *wor
ld);
  include\gamePacket\tile_change.cpp:692:                    return;
  include\gamePacket\tile_change.cpp:693:                }
  include\gamePacket\tile_change.cpp:694:            }
  include\gamePacket\tile_change.cpp:695:            if ((item.type == type::BACKGROUND && block.bg != 0) ||
  include\gamePacket\tile_change.cpp:696:                (item.type != type::BACKGROUND && block.fg != 0)) return; // @
note an extra check, i will later make this cleaner.
  include\gamePacket\tile_change.cpp:697:            if (item.collision == collision::FULL)
  include\gamePacket\tile_change.cpp:698:            {
  include\gamePacket\tile_change.cpp:699:                if (gamePacket.punch == gamePacket.pos.by_32(true)) return; //
 @todo when moving avoid collision.
  include\gamePacket\tile_change.cpp:700:            }

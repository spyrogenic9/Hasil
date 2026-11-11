===== STORAGE ACTION REFERENCES =====
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Get-ChildItem .\include -Recurse -File -Include *.cpp,*.hpp |
>>     Select-String -Pattern 'WorldLockStorage|worldlock_storage|wl_storage|store.?all|deposit.?all|withdraw.?all' -Context 4,7

  include\action\dialog_return\popup.cpp:4:#include <unordered_map>
  include\action\dialog_return\popup.cpp:5:
  include\action\dialog_return\popup.cpp:6:static const std::unordered_map<std::string, std::string> rml_pages{
  include\action\dialog_return\popup.cpp:7:    {"seed_diary_customization", "show_seed_diary_ui"},
> include\action\dialog_return\popup.cpp:8:    {"open_worldlock_storage", "show_world_lock_storage"}
  include\action\dialog_return\popup.cpp:9:};
  include\action\dialog_return\popup.cpp:10:
  include\action\dialog_return\popup.cpp:11:void popup(ENetEvent& event, const ::hPipe &hPipe)
  include\action\dialog_return\popup.cpp:12:{
  include\action\dialog_return\popup.cpp:13:    ::peer *pPeer = static_cast<::peer*>(event.peer->data);
  include\action\dialog_return\popup.cpp:14:
  include\action\dialog_return\popup.cpp:15:    if (hPipe["buttonClicked"] == "my_worlds")
  include\action\worldlock_storage_getpage.cpp:1:#include "pch.hpp"
  include\action\worldlock_storage_getpage.cpp:2:
> include\action\worldlock_storage_getpage.cpp:3:#include "onVariant/WorldLockStorageResponse.hpp"
  include\action\worldlock_storage_getpage.cpp:4:
> include\action\worldlock_storage_getpage.cpp:5:#include "worldlock_storage_getpage.hpp"
  include\action\worldlock_storage_getpage.cpp:6:
> include\action\worldlock_storage_getpage.cpp:7:void action::worldlock_storage_getpage(ENetEvent& event, const std::st
ring& header)
  include\action\worldlock_storage_getpage.cpp:8:{
  include\action\worldlock_storage_getpage.cpp:9:    ::peer *pPeer = static_cast<::peer*>(event.peer->data);
  include\action\worldlock_storage_getpage.cpp:10:
> include\action\worldlock_storage_getpage.cpp:11:    on::WorldLockStorageResponse(event.peer);
  include\action\worldlock_storage_getpage.cpp:12:}
  include\action\worldlock_storage_getpage.hpp:1:#pragma once
  include\action\worldlock_storage_getpage.hpp:2:
  include\action\worldlock_storage_getpage.hpp:3:namespace action
  include\action\worldlock_storage_getpage.hpp:4:{
> include\action\worldlock_storage_getpage.hpp:5:    extern void worldlock_storage_getpage(ENetEvent& event, const std:
:string& header);
  include\action\worldlock_storage_getpage.hpp:6:}
  include\action\worldlock_storage_modify_amount.cpp:5:#include <charconv>
  include\action\worldlock_storage_modify_amount.cpp:6:#include <limits>
  include\action\worldlock_storage_modify_amount.cpp:7:
  include\action\worldlock_storage_modify_amount.cpp:8:#include "onVariant/ConsoleMessage.hpp"
> include\action\worldlock_storage_modify_amount.cpp:9:#include "onVariant/WorldLockStorageResponse.hpp"
  include\action\worldlock_storage_modify_amount.cpp:10:#include "onVariant/EventButtonDataSet.hpp"
  include\action\worldlock_storage_modify_amount.cpp:11:#include "tools/conversions.hpp"
  include\action\worldlock_storage_modify_amount.cpp:12:
> include\action\worldlock_storage_modify_amount.cpp:13:#include "worldlock_storage_getpage.hpp"
> include\action\worldlock_storage_modify_amount.cpp:14:#include "worldlock_storage_modify_amount.hpp"
  include\action\worldlock_storage_modify_amount.cpp:15:
> include\action\worldlock_storage_modify_amount.cpp:16:void action::worldlock_storage_modify_amount(ENetEvent& event,
const std::string& header)
  include\action\worldlock_storage_modify_amount.cpp:17:{
  include\action\worldlock_storage_modify_amount.cpp:18:    ::peer* pPeer = static_cast<::peer*>(event.peer->data);
  include\action\worldlock_storage_modify_amount.cpp:19:    if (pPeer == nullptr) return;
  include\action\worldlock_storage_modify_amount.cpp:20:
  include\action\worldlock_storage_modify_amount.cpp:21:    const ::hPipe hPipe{ header };
  include\action\worldlock_storage_modify_amount.cpp:22:
  include\action\worldlock_storage_modify_amount.cpp:23:    // Strict integer parsing: reject malformed input and overf
low.
  include\action\worldlock_storage_modify_amount.cpp:54:            "OnActiveAuctionUpdate",
  include\action\worldlock_storage_modify_amount.cpp:55:            "{\"Active\":false}"
  include\action\worldlock_storage_modify_amount.cpp:56:        });
  include\action\worldlock_storage_modify_amount.cpp:57:
> include\action\worldlock_storage_modify_amount.cpp:58:        on::WorldLockStorageResponse(event.peer);
  include\action\worldlock_storage_modify_amount.cpp:59:    };
  include\action\worldlock_storage_modify_amount.cpp:60:
  include\action\worldlock_storage_modify_amount.cpp:61:    // Preserve the existing refresh-only behavior.
  include\action\worldlock_storage_modify_amount.cpp:62:    if (type == 0)
  include\action\worldlock_storage_modify_amount.cpp:63:    {
  include\action\worldlock_storage_modify_amount.cpp:64:        refresh_storage();
  include\action\worldlock_storage_modify_amount.cpp:65:        return;
  include\action\worldlock_storage_modify_amount.cpp:66:    }
  include\action\worldlock_storage_modify_amount.cpp:67:
  include\action\worldlock_storage_modify_amount.cpp:68:    // A negative balance indicates corrupted/previously exploi
ted data.
  include\action\worldlock_storage_modify_amount.cpp:69:    // Do not perform additional transactions against it.
> include\action\worldlock_storage_modify_amount.cpp:70:    if (pPeer->wl_storage < 0)
  include\action\worldlock_storage_modify_amount.cpp:71:        return;
  include\action\worldlock_storage_modify_amount.cpp:72:
  include\action\worldlock_storage_modify_amount.cpp:73:    // Prevent signed integer overflow and overdrawing.
  include\action\worldlock_storage_modify_amount.cpp:74:    if (type == 1)
  include\action\worldlock_storage_modify_amount.cpp:75:    {
> include\action\worldlock_storage_modify_amount.cpp:76:        if (amount > std::numeric_limits<int>::max() - pPeer->w
l_storage)
  include\action\worldlock_storage_modify_amount.cpp:77:            return;
  include\action\worldlock_storage_modify_amount.cpp:78:    }
  include\action\worldlock_storage_modify_amount.cpp:79:    else
  include\action\worldlock_storage_modify_amount.cpp:80:    {
> include\action\worldlock_storage_modify_amount.cpp:81:        if (amount > pPeer->wl_storage)
  include\action\worldlock_storage_modify_amount.cpp:82:            return;
  include\action\worldlock_storage_modify_amount.cpp:83:    }
  include\action\worldlock_storage_modify_amount.cpp:84:
  include\action\worldlock_storage_modify_amount.cpp:85:    // Read the actual signed inventory count.
  include\action\worldlock_storage_modify_amount.cpp:86:    // Do not use have_slot(), because it returns unsigned data
.
  include\action\worldlock_storage_modify_amount.cpp:87:    auto get_inventory_count = [&](short item_id, int& count) -
> bool
  include\action\worldlock_storage_modify_amount.cpp:88:    {
  include\action\worldlock_storage_modify_amount.cpp:205:    }
  include\action\worldlock_storage_modify_amount.cpp:206:
  include\action\worldlock_storage_modify_amount.cpp:207:    // Change the storage balance only after inventory changes
.
  include\action\worldlock_storage_modify_amount.cpp:208:    if (type == 1)
> include\action\worldlock_storage_modify_amount.cpp:209:        pPeer->wl_storage += amount;
  include\action\worldlock_storage_modify_amount.cpp:210:    else
> include\action\worldlock_storage_modify_amount.cpp:211:        pPeer->wl_storage -= amount;
  include\action\worldlock_storage_modify_amount.cpp:212:
  include\action\worldlock_storage_modify_amount.cpp:213:    if (type == -1)
  include\action\worldlock_storage_modify_amount.cpp:214:    {
  include\action\worldlock_storage_modify_amount.cpp:215:        const std::string message = std::format(
  include\action\worldlock_storage_modify_amount.cpp:216:            "You collected {}.",
  include\action\worldlock_storage_modify_amount.cpp:217:            collected
  include\action\worldlock_storage_modify_amount.cpp:218:        );
  include\action\worldlock_storage_modify_amount.hpp:1:#pragma once
  include\action\worldlock_storage_modify_amount.hpp:2:
  include\action\worldlock_storage_modify_amount.hpp:3:namespace action
  include\action\worldlock_storage_modify_amount.hpp:4:{
> include\action\worldlock_storage_modify_amount.hpp:5:    extern void worldlock_storage_modify_amount(ENetEvent& event
, const std::string& header);
  include\action\worldlock_storage_modify_amount.hpp:6:}
  include\action\wrench.cpp:50:                            .add_custom_button("trade_scan", "image:interface/large/gui_
wrench_trades.rttex;image_size:400,260;width:0.19;")
  include\action\wrench.cpp:51:                            .embed_data("netID", netid) // @todo research why rgt adds t
his twice···
  include\action\wrench.cpp:52:                            .add_custom_button("pets", "image:interface/large/gui_wrench
_battle_pets.rttex;image_size:400,260;width:0.19;")
  include\action\wrench.cpp:53:                            .add_custom_button("wrench_customization", "image:interface/
large/gui_wrench_customization.rttex;image_size:400,260;width:0.19;")
> include\action\wrench.cpp:54:                            .add_custom_button("open_worldlock_storage", "image:interfac
e/large/gui_wrench_auction.rttex;image_size:400,260;width:0.19;")
  include\action\wrench.cpp:55:                            .add_custom_break()
  include\action\wrench.cpp:56:                            .add_spacer("small")
  include\action\wrench.cpp:57:                            .set_custom_spacing(0, 0) // @todo research why rgt adds thi
s too. is 0, 0 unaffecting? or is this resetting the previous 5, 10 spacing
  include\action\wrench.cpp:58:                            .add_spacer("small")
  include\action\wrench.cpp:59:                            .add_textbox("Surgeon Level: 0")
  include\action\wrench.cpp:60:                            .add_spacer("small")
  include\action\wrench.cpp:61:                            .add_textbox("`wActive effects:``")
  include\action\__action.cpp:27:#include "store.hpp"
  include\action\__action.cpp:28:#include "storenavigate.hpp"
  include\action\__action.cpp:29:#include "buy.hpp"
  include\action\__action.cpp:30:
> include\action\__action.cpp:31:#include "worldlock_storage_getpage.hpp"
> include\action\__action.cpp:32:#include "worldlock_storage_modify_amount.hpp"
  include\action\__action.cpp:33:
  include\action\__action.cpp:34:#include "quit.hpp"
  include\action\__action.cpp:35:
  include\action\__action.cpp:36:#include "__action.hpp"
  include\action\__action.cpp:37:
  include\action\__action.cpp:38:std::unordered_map<std::string, std::function<void(ENetEvent&, const std::string&)>> a
ction_pool
  include\action\__action.cpp:39:{
  include\action\__action.cpp:64:    {"action|store", std::bind(&action::store, std::placeholders::_1, std::placeholder
s::_2)},
  include\action\__action.cpp:65:    {"action|storenavigate", std::bind(&action::storenavigate, std::placeholders::_1,
std::placeholders::_2)},
  include\action\__action.cpp:66:    {"action|buy", std::bind(&action::buy, std::placeholders::_1, std::placeholders::_
2, "")},
  include\action\__action.cpp:67:
> include\action\__action.cpp:68:    {"action|worldlock_storage_getpage", std::bind(&action::worldlock_storage_getpage,
 std::placeholders::_1, std::placeholders::_2)},
> include\action\__action.cpp:69:    {"action|worldlock_storage_modify_amount", std::bind(&action::worldlock_storage_mo
dify_amount, std::placeholders::_1, std::placeholders::_2)},
  include\action\__action.cpp:70:
  include\action\__action.cpp:71:    {"action|quit", std::bind(&action::quit, std::placeholders::_1, std::placeholders:
:_2)}
  include\action\__action.cpp:72:};
  include\database\database.cpp:19:             "role TINYINT UNSIGNED NOT NULL DEFAULT 3,"
  include\database\database.cpp:20:        "created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,"
  include\database\database.cpp:21:        "inventory BLOB,"
  include\database\database.cpp:22:        "gems BIGINT DEFAULT 0,"
> include\database\database.cpp:23:        "wl_storage INT DEFAULT 0,"
  include\database\database.cpp:24:        "level INT DEFAULT 1,"
  include\database\database.cpp:25:        "xp INT DEFAULT 0"
  include\database\database.cpp:26:    ")");
  include\database\database.cpp:27:    error = mysql_query(mysql,
  include\database\database.cpp:28:        "CREATE TABLE IF NOT EXISTS world ("
  include\database\database.cpp:29:        "name VARCHAR(24) NOT NULL PRIMARY KEY,"
  include\database\database.cpp:30:        "owner INT DEFAULT 0,"
  include\database\database.cpp:58:{
  include\database\database.cpp:59:    if (!column_found("peer", "gems"))  alter_table("peer", "gems BIGINT DEFAULT 0")
;
  include\database\database.cpp:60:    if (!column_found("peer", "level")) alter_table("peer", "level INT DEFAULT 1");
  include\database\database.cpp:61:    if (!column_found("peer", "xp"))    alter_table("peer", "xp INT DEFAULT 0");
> include\database\database.cpp:62:    if (!column_found("peer", "wl_storage")) alter_table("peer", "wl_storage INT DEF
AULT 0");
  include\database\database.cpp:63:     if (!column_found("peer", "role")) alter_table("peer", "role TINYINT UNSIGNED NOT N
ULL DEFAULT 3");
  include\database\database.cpp:64:}
  include\database\database.cpp:65:
  include\database\database.cpp:66:void mysql_gateway::mysql_connect()
  include\database\database.cpp:67:{
  include\database\database.cpp:68:    if (!mysql_real_connect(mysql, this->host.c_str(), this->user.c_str(), this->pas
swd.c_str(), NULL, 3306u, NULL, 0ul))
  include\database\database.cpp:69:    {
  include\database\peer.cpp:95:
  include\database\peer.cpp:96:    this->role = role_value <= PLAYER ? static_cast<u_char>(role_value) : PLAYER;
  include\database\peer.cpp:97:    this->created_at = this->mysql_select<std::time_t>("created_at", "UNIX_TIMESTAMP", b
y_user_id);
  include\database\peer.cpp:98:    this->gems       = this->mysql_select<long long>("gems", "", by_user_id);
> include\database\peer.cpp:99:    this->wl_storage = this->mysql_select<signed>("wl_storage", "", by_user_id);
  include\database\peer.cpp:100:    this->level[0]   = this->mysql_select<signed>("level", "", by_user_id);
  include\database\peer.cpp:101:    this->level[1]   = this->mysql_select<signed>("xp", "", by_user_id);
  include\database\peer.cpp:102:
  include\database\peer.cpp:103:    auto inventory = this->mysql_select<::blob>("inventory", "", by_user_id);
  include\database\peer.cpp:104:
  include\database\peer.cpp:105:    if (inventory.size() >= sizeof(int) + sizeof(short))
  include\database\peer.cpp:106:    {
  include\database\peer.cpp:184:    if (this->growid.empty()) return;
  include\database\peer.cpp:185:
  include\database\peer.cpp:186:    ::hStmt hStmt{
  include\database\peer.cpp:187:    "UPDATE peer SET inventory = ?, gems = ?, level = ?, "
> include\database\peer.cpp:188:    "xp = ?, wl_storage = ?, role = ? WHERE growid = ?"
  include\database\peer.cpp:189:};
  include\database\peer.cpp:190:    const ::blob inventory = this->serialize_inventory();
  include\database\peer.cpp:191:    const int level_value = this->level[0], xp_value = this->level[1];
  include\database\peer.cpp:192:        const unsigned role_value = static_cast<unsigned>(this->role);
  include\database\peer.cpp:193:
  include\database\peer.cpp:194:        MYSQL_BIND params[7] = {
  include\database\peer.cpp:195:                make_bind_in(inventory),
  include\database\peer.cpp:196:                make_bind_in(this->gems),
  include\database\peer.cpp:197:                make_bind_in(level_value),
  include\database\peer.cpp:198:                make_bind_in(xp_value),
> include\database\peer.cpp:199:                make_bind_in(this->wl_storage),
  include\database\peer.cpp:200:                make_bind_in(role_value),
  include\database\peer.cpp:201:                make_bind_in(this->growid)
  include\database\peer.cpp:202:        };
  include\database\peer.cpp:203:    hStmt.bind_param(params);
  include\database\peer.cpp:204:    hStmt.execute();
  include\database\peer.cpp:205:}
  include\database\peer.cpp:206:
  include\database\peer.hpp:148:
  include\database\peer.hpp:149:    std::vector<short> fav{};
  include\database\peer.hpp:150:
  include\database\peer.hpp:151:    long long gems{0};
> include\database\peer.hpp:152:    int wl_storage{0};
  include\database\peer.hpp:153:    std::array<u_short, 2ull> level{ 1, 0 }; // {level, xp} XP formula credits: https:/
/www.growtopiagame.com/forums/member/553046-kasete
  include\database\peer.hpp:154:    /*
  include\database\peer.hpp:155:    * @brief add XP safely, this function also handles level up.
  include\database\peer.hpp:156:    */
  include\database\peer.hpp:157:    void add_xp(ENetEvent &event, u_short value);
  include\database\peer.hpp:158:
  include\database\peer.hpp:159:    /*
  include\onVariant\WorldLockStorageResponse.cpp:1:#include "pch.hpp"
  include\onVariant\WorldLockStorageResponse.cpp:2:
> include\onVariant\WorldLockStorageResponse.cpp:3:#include "WorldLockStorageResponse.hpp"
  include\onVariant\WorldLockStorageResponse.cpp:4:
> include\onVariant\WorldLockStorageResponse.cpp:5:void on::WorldLockStorageResponse(ENetPeer *peer)
  include\onVariant\WorldLockStorageResponse.cpp:6:{
  include\onVariant\WorldLockStorageResponse.cpp:7:    ::peer *pPeer = static_cast<::peer*>(peer->data);
  include\onVariant\WorldLockStorageResponse.cpp:8:
> include\onVariant\WorldLockStorageResponse.cpp:9:    const u_int count = pPeer->wl_storage > 0
> include\onVariant\WorldLockStorageResponse.cpp:10:            ? static_cast<u_int>(pPeer->wl_storage)
  include\onVariant\WorldLockStorageResponse.cpp:11:            : 0u;
  include\onVariant\WorldLockStorageResponse.cpp:12:    std::string data{"\x95\x90", 2}; // @note msgpack [[], balance,
 0, 0, 0]
  include\onVariant\WorldLockStorageResponse.cpp:13:    struct encoding { u_int maximum; u_char prefix; int bytes; };
  include\onVariant\WorldLockStorageResponse.cpp:14:    constexpr encoding formats[]{
  include\onVariant\WorldLockStorageResponse.cpp:15:        {0x7f, 0, 1}, {0xff, 0xcc, 1}, {0xffff, 0xcd, 2}, {0xffffff
ffu, 0xce, 4}
  include\onVariant\WorldLockStorageResponse.cpp:16:    };
  include\onVariant\WorldLockStorageResponse.cpp:17:    const encoding *const format = std::ranges::find_if(formats, [c
ount](const encoding &entry) { return count <= entry.maximum; });
  include\onVariant\WorldLockStorageResponse.cpp:18:    if (format->prefix != 0) data.push_back(static_cast<char>(forma
t->prefix));
  include\onVariant\WorldLockStorageResponse.cpp:19:    for (int i = format->bytes - 1; i >= 0; --i) data.push_back(sta
tic_cast<char>(count >> (i * 8)));
  include\onVariant\WorldLockStorageResponse.cpp:20:    data.append(3, '\0');
  include\onVariant\WorldLockStorageResponse.cpp:21:
> include\onVariant\WorldLockStorageResponse.cpp:22:    send_varlist(peer, { "OnWorldLockStorageResponse", data });
  include\onVariant\WorldLockStorageResponse.cpp:23:}
  include\onVariant\WorldLockStorageResponse.hpp:1:#pragma once
  include\onVariant\WorldLockStorageResponse.hpp:2:
  include\onVariant\WorldLockStorageResponse.hpp:3:namespace on
  include\onVariant\WorldLockStorageResponse.hpp:4:{
> include\onVariant\WorldLockStorageResponse.hpp:5:    extern void WorldLockStorageResponse(ENetPeer *peer);
  include\onVariant\WorldLockStorageResponse.hpp:6:}


PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== STORAGE MODIFY ====="

===== STORAGE MODIFY =====
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

    // A negative balance indicates corrupted/previously exploited data.
    // Do not perform additional transactions against it.
    if (pPeer->wl_storage < 0)
        return;

    // Prevent signed integer overflow and overdrawing.
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

    // Read the actual signed inventory count.
    // Do not use have_slot(), because it returns unsigned data.
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

    // Calculate exact denominations using wider signed integers.
    int remaining = amount;

    int bgl = std::min<int>(
        remaining / BLUE_GEM_LOCK_VALUE,
        bgl_capacity
    );
    remaining -= bgl * BLUE_GEM_LOCK_VALUE;

    int dl = std::min<int>(
        remaining / DIAMOND_LOCK_VALUE,
        dl_capacity
    );
    remaining -= dl * DIAMOND_LOCK_VALUE;

    int wl = std::min<int>(
        remaining,
        wl_capacity
    );
    remaining -= wl;

    // Never execute a partial transaction.
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
PS C:\GTPS\Gurotopia> Write-Host "`n===== DIALOG RETURN DISPATCH ====="

===== DIALOG RETURN DISPATCH =====
PS C:\GTPS\Gurotopia> Get-Content .\include\action\dialog_return\__dialog_return.cpp
#include "pch.hpp"

#include "admin/admin.hpp"

#include "popup.hpp"

#include "drop_item.hpp"
#include "trash_item.hpp"
#include "find_item.hpp"
#include "trade_item.hpp"

#include "gateway_edit.hpp"

#include "billboard_edit.hpp"
#include "lock_edit.hpp"

#include "create_blast.hpp"
#include "socialportal.hpp"
#include "megaphone.hpp"

#include "__dialog_return.hpp"

std::unordered_map<std::string, std::function<void(ENetEvent &, const ::hPipe &)>> dialog_return_pool
{
    {"popup", std::bind(&popup, std::placeholders::_1, std::placeholders::_2)},
    {"gurotopia_admin", std::bind(&admin::handle_dialog, std::placeholders::_1, std::placeholders::_2)},

    {"drop_item", std::bind(&drop_item, std::placeholders::_1, std::placeholders::_2)},
    {"trash_item", std::bind(&trash_item, std::placeholders::_1, std::placeholders::_2)},
    {"find_item", std::bind(&find_item, std::placeholders::_1, std::placeholders::_2)},
    {"trade_item", std::bind(&trade_item, std::placeholders::_1, std::placeholders::_2)},

    {"gateway_edit", std::bind(&gateway_edit, std::placeholders::_1, std::placeholders::_2)},
    {"door_edit", std::bind(&gateway_edit, std::placeholders::_1, std::placeholders::_2)},
    {"sign_edit", std::bind(&gateway_edit, std::placeholders::_1, std::placeholders::_2)},

    {"billboard_edit", std::bind(&billboard_edit, std::placeholders::_1, std::placeholders::_2)},
    {"lock_edit", std::bind(&lock_edit, std::placeholders::_1, std::placeholders::_2)},

    {"create_blast", std::bind(&create_blast, std::placeholders::_1, std::placeholders::_2)},
    {"socialportal", std::bind(&socialportal, std::placeholders::_1, std::placeholders::_2)},
    {"megaphone", std::bind(&megaphone, std::placeholders::_1, std::placeholders::_2)}
};
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== ACTION DISPATCH ====="

===== ACTION DISPATCH =====
PS C:\GTPS\Gurotopia> Get-Content .\include\action\__action.cpp
#include "pch.hpp"

#include "protocol.hpp"
#include "tankIDName.hpp"
#include "refresh_item_data.hpp"
#include "enter_game.hpp"

#include "dialog_return.hpp"
#include "friends.hpp"

#include "join_request.hpp"
#include "validate_world.hpp"
#include "quit_to_exit.hpp"
#include "respawn.hpp"
#include "respawn_spike.hpp"
#include "setSkin.hpp"
#include "input.hpp"
#include "drop.hpp"
#include "info.hpp"
#include "trash.hpp"
#include "wrench.hpp"
#include "trade_started.hpp"
#include "mod_trade.hpp"
#include "rem_trade.hpp"
#include "itemfavourite.hpp"
#include "inventoryfavuitrigger.hpp"
#include "store.hpp"
#include "storenavigate.hpp"
#include "buy.hpp"

#include "worldlock_storage_getpage.hpp"
#include "worldlock_storage_modify_amount.hpp"

#include "quit.hpp"

#include "__action.hpp"

std::unordered_map<std::string, std::function<void(ENetEvent&, const std::string&)>> action_pool
{
    {"protocol", std::bind(&action::protocol, std::placeholders::_1, std::placeholders::_2)},
    {"tankIDName", std::bind(&action::tankIDName, std::placeholders::_1, std::placeholders::_2)},
    {"action|refresh_item_data", std::bind(&action::refresh_item_data, std::placeholders::_1, std::placeholders::_2)},
    {"action|enter_game", std::bind(&action::enter_game, std::placeholders::_1, std::placeholders::_2)},

    {"action|dialog_return", std::bind(&action::dialog_return, std::placeholders::_1, std::placeholders::_2)},
    {"action|friends", std::bind(&action::friends, std::placeholders::_1, std::placeholders::_2)},

    {"action|join_request", std::bind(&action::join_request, std::placeholders::_1, std::placeholders::_2, "")},
    {"action|validate_world", std::bind(&action::validate_world, std::placeholders::_1, std::placeholders::_2)},
    {"action|quit_to_exit", std::bind(&action::quit_to_exit, std::placeholders::_1, std::placeholders::_2, false)},
    {"action|respawn", std::bind(&action::respawn, std::placeholders::_1, std::placeholders::_2)},
    {"action|respawn_spike", std::bind(&action::respawn_spike, std::placeholders::_1, std::placeholders::_2)},
    {"action|setSkin", std::bind(&action::setSkin, std::placeholders::_1, std::placeholders::_2)},
    {"action|input", std::bind(&action::input, std::placeholders::_1, std::placeholders::_2)},
    {"action|drop", std::bind(&action::drop, std::placeholders::_1, std::placeholders::_2)},
    {"action|info", std::bind(&action::info, std::placeholders::_1, std::placeholders::_2)},
    {"action|trash", std::bind(&action::trash, std::placeholders::_1, std::placeholders::_2)},
    {"action|wrench", std::bind(&action::wrench, std::placeholders::_1, std::placeholders::_2)},
    {"action|trade_started", std::bind(&action::trade_started, std::placeholders::_1, std::placeholders::_2)},
    {"action|mod_trade", std::bind(&action::mod_trade, std::placeholders::_1, std::placeholders::_2)},
    {"action|rem_trade", std::bind(&action::rem_trade, std::placeholders::_1, std::placeholders::_2)},
    {"action|itemfavourite", std::bind(&action::itemfavourite, std::placeholders::_1, std::placeholders::_2)},
    {"action|inventoryfavuitrigger", std::bind(&action::inventoryfavuitrigger, std::placeholders::_1, std::placeholders::_2)},
    {"action|store", std::bind(&action::store, std::placeholders::_1, std::placeholders::_2)},
    {"action|storenavigate", std::bind(&action::storenavigate, std::placeholders::_1, std::placeholders::_2)},
    {"action|buy", std::bind(&action::buy, std::placeholders::_1, std::placeholders::_2, "")},

    {"action|worldlock_storage_getpage", std::bind(&action::worldlock_storage_getpage, std::placeholders::_1, std::placeholders::_2)},
    {"action|worldlock_storage_modify_amount", std::bind(&action::worldlock_storage_modify_amount, std::placeholders::_1, std::placeholders::_2)},

    {"action|quit", std::bind(&action::quit, std::placeholders::_1, std::placeholders::_2)}
};
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== STORAGE RESPONSE ====="

===== STORAGE RESPONSE =====
PS C:\GTPS\Gurotopia> Get-Content .\include\onVariant\WorldLockStorageResponse.cpp
#include "pch.hpp"

#include "WorldLockStorageResponse.hpp"

void on::WorldLockStorageResponse(ENetPeer *peer)
{
    ::peer *pPeer = static_cast<::peer*>(peer->data);

    const u_int count = pPeer->wl_storage > 0
                ? static_cast<u_int>(pPeer->wl_storage)
                : 0u;
    std::string data{"\x95\x90", 2}; // @note msgpack [[], balance, 0, 0, 0]
    struct encoding { u_int maximum; u_char prefix; int bytes; };
    constexpr encoding formats[]{
        {0x7f, 0, 1}, {0xff, 0xcc, 1}, {0xffff, 0xcd, 2}, {0xffffffffu, 0xce, 4}
    };
    const encoding *const format = std::ranges::find_if(formats, [count](const encoding &entry) { return count <= entry.maximum; });
    if (format->prefix != 0) data.push_back(static_cast<char>(format->prefix));
    for (int i = format->bytes - 1; i >= 0; --i) data.push_back(static_cast<char>(count >> (i * 8)));
    data.append(3, '\0');

    send_varlist(peer, { "OnWorldLockStorageResponse", data });
}

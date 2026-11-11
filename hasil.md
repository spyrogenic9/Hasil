PS C:\GTPS\Gurotopia> $files = @(
>>     ".\include\action\worldlock_storage_modify_amount.cpp",
>>     ".\include\database\peer.hpp",
>>     ".\include\database\database.hpp"
>> )
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> foreach ($file in $files) {
>>     Write-Host "`n========== $file ==========" -ForegroundColor Cyan
>>     Get-Content $file
>> }

========== .\include\action\worldlock_storage_modify_amount.cpp ==========
#include "pch.hpp"

#include "onVariant/ConsoleMessage.hpp"
#include "onVariant/WorldLockStorageResponse.hpp"
#include "onVariant/EventButtonDataSet.hpp"
#include "tools/conversions.hpp"

#include "worldlock_storage_getpage.hpp"
#include "worldlock_storage_modify_amount.hpp"

void action::worldlock_storage_modify_amount(ENetEvent& event, const std::string& header)
{
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    const ::hPipe hPipe{header};

    u_int amount = atoi(hPipe["amount"].c_str());
    if (amount <= 0) return;
    int type = atoi(hPipe["type"].c_str());
    if (type < -1 || type > 1) return;

    pPeer->wl_storage += type*amount;

    u_short wl = amount,
            dl = amount / DIAMOND_LOCK_VALUE,
            bgl = amount / BLUE_GEM_LOCK_VALUE;
    std::string str;

    if (type == 1)
    {
        wl = pPeer->have_slot({ 242, 0 }),
        dl = pPeer->have_slot({ 1796, 0 }),
        bgl = pPeer->have_slot({ 7188, 0 });
        convert_lock(amount, wl, dl, bgl, str);
    }
    else convert_lock(amount, wl, dl, bgl, str);

    if (bgl > 0) modify_item_inventory(event, ::slot(7188, -(type)*bgl));
    if (dl  > 0) modify_item_inventory(event, ::slot(1796, -(type)*dl));
    if (wl  > 0) modify_item_inventory(event, ::slot(242,  -(type)*wl));

    if (type == -1)
    {
        std::string message = std::format("You collected {}.", str);

        send_varlist(event.peer, { "OnTalkBubble", pPeer->netid, message, 0u, 1u });
        on::ConsoleMessage(event.peer, message);
    }
    on::EventButtonDataSet(event, true);
    on::EventButtonDataSet(event, false);
    send_varlist(event.peer, { "OnActiveAuctionUpdate", "{\"Active\":false}" });
    on::WorldLockStorageResponse(event.peer);
}

========== .\include\database\peer.hpp ==========
#pragma once

#include <cmath> // @note std::floor
#include <deque> // @note std::deque

enum bgra : u_int
{
    BLUE  = 0xff000000,
    GREEN = 0x00ff0000,
    RED   = 0x0000ff00,
    ALPHA = 0x000000ff
};

#include "database.hpp"

/* id, count */
struct slot {
    slot(short _id = 0, short _count = 0) : id(_id), count(_count) {}
    short id{};
    short count{}; // @note total amount of that item

    ::blob to_blob() const;
};

/* x, y */
struct pos {
    pos() = default;
    pos(float _x, float _y) : x(_x), y(_y) {}
    pos(int _x, int _y)     : x(_x), y(_y) {}
    pos(u_int _x, u_int _y) : x(_x), y(_y) {} // @todo can this even be unsigned?

    float x, y;

    /* @param pixel
    *   true to divide by 32 pixels for true tile.
    *   false to multiply by 32 for percise position.
    */
    pos by_32(bool pixel = false) const {
        return (pixel) ?
            pos{std::floor/*<auto>*/(x/32.0f), std::floor/*<auto>*/(y/32.0f)} :
            pos{x*32.0f, y*32.0f};
    }

    int x_int() const { return std::floor<int>(x); }
    int y_int() const { return std::floor<int>(y); }

    u_int x_u_int() const { return std::floor<u_int>(x); }
    u_int y_u_int() const { return std::floor<u_int>(y); }

    auto operator<=>(const pos&) const = default;
};

struct Billboard {
    short id{0}; // @note the item they're selling
    bool show{};
    bool isBuying{};
    int price{1};
    bool perItem{}; // @note true if world locks per item, false if items per world lock
};

enum role : u_char
{
    OWNER     = 0,
    DEVELOPER = 1,
    MODERATOR = 2,
    PLAYER    = 3
};

constexpr bool peer_is_staff_role(u_char value) noexcept
{
    return value == OWNER ||
           value == DEVELOPER ||
           value == MODERATOR;
}

constexpr bool peer_is_super_staff_role(u_char value) noexcept
{
    return value == OWNER || value == DEVELOPER;
}

enum pstate : int
{
    S_GHOST       = 0x00000001,
    S_DOUBLE_JUMP = 0x00000002,
    S_DUCT_TAPE   = 0x00002000
};

class peer {
public:
    ~peer();

    bool load(const std::string &growid, const std::string password);
    bool load_by_uid(int uid);
    bool create_account(const std::string &growid, const std::string &password);

    bool exists(const std::string &growid);

    template<typename T>
    void mysql_insert(const std::string &column, const T &value);

    template<typename T>
    void mysql_update(const std::string &column, const T &value);

    template<typename T>
    T    mysql_select(const std::string &column, const std::string &arg = "", bool by_user_id = false); // @note by_user_id: WHERE uid instead of WHERE growid
    void mysql_select_all(bool by_user_id = false);
    void mysql_update_all();

    int user_id{}; // @note unqiue user id.
    std::string growid{""}, password{""};
    std::time_t created_at{}; // @note when inserted in SQL (account age)
    u_char role{PLAYER};
    std::array<float, 10ull> clothing{}; // @note peer's clothing {id, clothing::}
    u_char punch_effect{}; // @note last equipped clothing that has a effect. supporting 0-255 effects.

    int netid{}; // @note peer's netid is world identity. this will be useful for many packet sending
    u_char icon{}; // @note typing or busy icon
    std::string display_growid{}; // @note use this for displaying growid, never use ::growid
    std::string country{};
    float game_version{0.0f};

    u_int skin_color{ 2527912447 };
    u_int hair_color = bgra::GREEN | bgra::GREEN | bgra::RED | bgra::ALPHA; // @note value declines for specfic hair colors

    int state{}; // @note using pstate::
    bool muted{}; // @note server-side chat restriction loaded from admin_mutes

    ::Billboard billboard{};

    ::pos pos{}; // @note position 1D {x, y}
    ::pos rest_pos{}; // @note respawn position {x, y}
    bool facing_left{}; // @note peer is directed towards the left direction
    short pain_hp{ 10 };

    int slot_size{16}; // @note amount of slots this peer has | were talking total slots not itemed slots, to get itemed slots do slot.size()
    std::vector<slot> slots{}; // @note an array of each slot. storing {id, count}
    /*
    * @brief set slot::count to nagative value if you want to remove an amount.
    * @return the remaining amount if exeeds 200. e.g. emplace(slot{0, 201}) returns 1.
    */
    u_short emplace(::slot slot);
    /*
    * @brief check if item exists in inventory (::slots)
    * @return slot count (0 if not exist)
    */
    u_short have_slot(::slot slot);
    ::blob serialize_inventory() const;

    std::vector<short> fav{};

    long long gems{0};
    int wl_storage{0};
    std::array<u_short, 2ull> level{ 1, 0 }; // {level, xp} XP formula credits: https://www.growtopiagame.com/forums/member/553046-kasete
    /*
    * @brief add XP safely, this function also handles level up.
    */
    void add_xp(ENetEvent &event, u_short value);

    /*
    * @brief recalculate transient effects based on clothing.
    */
    void update_effects();

    std::array<std::string, 6ull> recent_worlds{}; // @note recent worlds, a list of 6 worlds, once it reaches 7 it'll be replaced by the oldest
    std::array<std::string, 200ull> my_worlds{}; // @note first 200 relevant worlds locked by peer.

    std::deque<u_int> messages; // @note last 5 que messages sent time, this is used to check for spamming

    u_short fires_removed{};
    u_short gbc_pity{}; // @note GBC pity; for each 100 will receive super GBC

    /* @todo move outside */
    std::vector<::slot> trade_offers{};
    bool trade_accepted = false;
};

/*
 * Build a role-aware character name. Keep the native Growtopia staff state
 * flags (mstate/smstate) as well; this text badge makes the three Gurotopia
 * staff ranks distinguishable even though the client exposes only two flags.
 * name_color preserves world-owner/access coloring supplied by the caller.
 */
inline std::string make_peer_display_growid(
    u_char value,
    const std::string& growid,
    const std::string& name_color = "`w")
{
    const char* badge = "";
    switch (value)
    {
        case OWNER:     badge = "`b[OWNER]`` "; break;
        case DEVELOPER: badge = "`6[DEVELOPER]`` "; break;
        case MODERATOR: badge = "`3[MOD]`` "; break;
        default: break;
    }
    return std::format("{}{}{}{}", badge, name_color, growid, "``");
}

extern ENetHost* host;

/* @brief search specific peer(s), used in peers() */
enum class PeerSearch : u_char
{
    WORLD = 0,
    EVERYONE = 1
};
template <typename Func>
void peers(const std::string &world, PeerSearch search, Func &&fun)
{
    for (ENetPeer *peer = host->peers, *end = peer + host->peerCount; peer != end; ++peer)
    {
        if (peer->state != ENET_PEER_STATE_CONNECTED) continue;

        if (search == PeerSearch::WORLD)
        {
            ::peer *pPeer = static_cast<::peer*>(peer->data);
            if (pPeer->netid == 0 || (pPeer->recent_worlds.back() != world)) continue;
        }
        std::forward<Func>(fun)(peer);
    }
}

extern void safe_disconnect_peers(int signal);

class gameMessage {
    public:
        int packet_create{ 03 }; // @note NET_MESSAGE_GAME_MESSAGE

        std::string message{};
        u_char terminator{ '\0' };
};

extern ::blob compressMessage(const gameMessage &gameMessage);

enum class gamePacketState : int
{
    UPDATE               = 0x00000004,
    EXTENDED             = 0x00000008,
    MOVE_LEFT            = 0x00000010,
    MOVE_RIGHT           = 0x00000020,
    HIT_BY_LAVA          = 0x00000040,
    JUMP                 = 0x00000080,
    ITEM_ACTIVATE_OBJECT = 0x00004000
};
class gamePacket {
public:
    int packet_create{ 04 }; // @note NET_MESSAGE_GAME_PACKET

    int type{};
    union
    {
        int netid{},
            particle_effect;
    };
    int uid{}; // @todo understand this better @note so far I think this holds uid value
    int state{}; // @note enum gamePacketState
    union
    {
        float count{},
              waterspeed;
    };
    union
    {
        int id{},
            delay;
    };
    ::pos pos{}; // @note position 1D {x, y}
    ::pos speed{}; // @note player movement (velocity(x), gravity(y)), higher gravity = smaller jumps
    float idk{};
    ::pos punch{}; // @note punching/placing position 2D {x, y}
    u_int size{};
};

extern gamePacket make_gamePacket(const enet_uint8 *data);

/* put it back into it's original form */
extern ::blob compress_state(const gamePacket &gamePacket);

extern void send_inventory_state(ENetEvent &event);

========== .\include\database\database.hpp ==========
#pragma once

#include <mysql/mysql.h>

#include "tools/terminal.hpp"

class mysql_gateway
{
public:
    mysql_gateway() { mysql = mysql_init(NULL); }
    ~mysql_gateway() { mysql_close(mysql); }

    void create_table_if_not_exist();
    bool column_found(const std::string &table, const std::string &column);
    int alter_table(const std::string &table, const std::string &column);
    void integrity();

    void mysql_connect();
    void load_login();

    MYSQL *mysql{nullptr};
private:
    std::string host{"127.0.0.1"};
    std::string user{"root"};
    std::string passwd{""};
};
extern ::mysql_gateway db;

class hStmt
{
public:
    hStmt(const std::string &query);
   ~hStmt();

    hStmt           (const hStmt &) = delete;
    hStmt &operator=(const hStmt &) = delete;

    void bind_param(MYSQL_BIND *param);
    void execute();
    void fetch();

    /* https://dev.mysql.com/doc/mysql-errors/8.4/en/client-error-reference.html */
    void log_stmt_error();

    MYSQL_STMT *pStmt;
};

#include <cstring> // linux

struct blob
{
    /* @note template vibes */
    void f32(float val) {
        int size = mData.size();
        mData.resize(size + sizeof(float));
        memcpy(mData.data() + size, &val, sizeof(float));
    }
    void i32(int val)   {
        int size = mData.size();
        mData.resize(size + sizeof(int));
        memcpy(mData.data() + size, &val, sizeof(int));
    }
    void u32(u_int val)   {
        int size = mData.size();
        mData.resize(size + sizeof(u_int));
        memcpy(mData.data() + size, &val, sizeof(u_int));
    }
    void i16(short val) {
        int size = mData.size();
        mData.resize(size + sizeof(short));
        memcpy(mData.data() + size, &val, sizeof(short));
    }
    void u8(u_char val) {
        mData.push_back(val);
    }

    bool read_f32(float &val, int &pos)
    {
        if (pos + (int)sizeof(float) > (int)mData.size()) return false;
        memcpy(&val, mData.data()+pos, sizeof(float));
        pos += sizeof(float);
        return true;
    }
    bool read_i32(int &val, int &pos)
    {
        if (pos + (int)sizeof(int) > (int)mData.size()) return false;
        memcpy(&val, mData.data()+pos, sizeof(int));
        pos += sizeof(int);
        return true;
    }
    bool read_u32(u_int &val, int &pos)
    {
        if (pos + (int)sizeof(u_int) > (int)mData.size()) return false;
        memcpy(&val, mData.data()+pos, sizeof(u_int));
        pos += sizeof(u_int);
        return true;
    }
    bool read_i16(short &val, int &pos)
    {
        if (pos + (int)sizeof(short) > (int)mData.size()) return false;
        memcpy(&val, mData.data()+pos, sizeof(short));
        pos += sizeof(short);
        return true;
    }
    bool read_u16(u_short &val, int &pos)
    {
        if (pos + (int)sizeof(u_short) > (int)mData.size()) return false;
        memcpy(&val, mData.data()+pos, sizeof(u_short));
        pos += sizeof(u_short);
        return true;
    }
    bool read_i8(char &val, int &pos)
    {
        if (pos + (int)sizeof(char) > (int)mData.size()) return false;
        memcpy(&val, mData.data()+pos, sizeof(char));
        pos += sizeof(char);
        return true;
    }
    bool read_u8(u_char &val, int &pos)
    {
        if (pos + (int)sizeof(u_char) > (int)mData.size()) return false;
        memcpy(&val, mData.data()+pos, sizeof(u_char));
        pos += sizeof(u_char);
        return true;
    }


    void push_back(const blob &blob)
    {
        const auto &data = blob.data();

        mData.insert(mData.end(), data.cbegin(), data.cend());
    }
    [[nodiscard]] const std::vector<u_char> &data() const noexcept {
        return mData;
    }
    [[nodiscard]] std::vector<u_char> &data() noexcept {
        return mData;
    }
    [[nodiscard]] constexpr std::size_t size() const noexcept {
        return mData.size();
    }
    constexpr void resize(std::size_t __new_size)
    {
        mData.resize(__new_size);
    }

private:
    std::vector<u_char> mData;
};

extern MYSQL_BIND make_bind_in(const signed &buffer);
extern MYSQL_BIND make_bind_in(const unsigned &buffer);
extern MYSQL_BIND make_bind_in(const long &buffer);
extern MYSQL_BIND make_bind_in(const long long &buffer);
extern MYSQL_BIND make_bind_in(const float &buffer);
extern MYSQL_BIND make_bind_in(const std::string &buffer);
extern MYSQL_BIND make_bind_in(const std::vector<u_char> &buffer);
extern MYSQL_BIND make_bind_in(const ::blob &buffer);

extern MYSQL_BIND make_bind_out(signed &buffer);
extern MYSQL_BIND make_bind_out(unsigned &buffer);
extern MYSQL_BIND make_bind_out(long &buffer);
extern MYSQL_BIND make_bind_out(long long &buffer);
extern MYSQL_BIND make_bind_out(float &buffer);
extern MYSQL_BIND make_bind_out(std::string &buffer);
extern MYSQL_BIND make_bind_out(std::vector<u_char> &buffer);
extern MYSQL_BIND make_bind_out(::blob &buffer);
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Get-ChildItem .\include -Recurse -File |
>>     Where-Object {
>>         $_.Name -match 'conversion|WorldLockStorageResponse'
>>     } |
>>     ForEach-Object {
>>         Write-Host "`n========== $($_.FullName) ==========" -ForegroundColor Cyan
>>         Get-Content $_.FullName
>>     }

========== C:\GTPS\Gurotopia\include\onVariant\WorldLockStorageResponse.cpp ==========
#include "pch.hpp"

#include "WorldLockStorageResponse.hpp"

void on::WorldLockStorageResponse(ENetPeer *peer)
{
    ::peer *pPeer = static_cast<::peer*>(peer->data);

    const u_int count = pPeer->wl_storage;
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

========== C:\GTPS\Gurotopia\include\onVariant\WorldLockStorageResponse.hpp ==========
#pragma once

namespace on
{
    extern void WorldLockStorageResponse(ENetPeer *peer);
}

========== C:\GTPS\Gurotopia\include\tools\conversions.cpp ==========
#include "pch.hpp"

#include "conversions.hpp"

void convert_lock(int amount, u_short& wl, u_short& dl, u_short& bgl, std::string &str)
{
    bgl = std::min<int>(amount / BLUE_GEM_LOCK_VALUE, bgl);
    amount -= bgl * BLUE_GEM_LOCK_VALUE;

    dl = std::min<int>(amount / DIAMOND_LOCK_VALUE, dl);
    amount -= dl * DIAMOND_LOCK_VALUE;

    wl = std::min<int>(amount, wl);
    amount -= wl;

    if (bgl > 0)
        str = std::format("{} `2Blue Gem Lock`` and {} `2Diamond Lock`` and {} `2World Lock``", bgl, dl, wl);
    else if (dl > 0)
        str = std::format("{} `2Diamond Lock`` and {} `2World Lock``", dl, wl);
    else if (wl > 0)
        str = std::format("{} `2World Lock``", wl);
}

========== C:\GTPS\Gurotopia\include\tools\conversions.hpp ==========
#pragma once

enum : u_short/*fit in ::slot::count*/
{
    DIAMOND_LOCK_VALUE = 100,
    BLUE_GEM_LOCK_VALUE = 1000
};

void convert_lock(int amount, u_short& wl, u_short& dl, u_short& bgl, std::string &str);

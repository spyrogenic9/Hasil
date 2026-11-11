PS C:\GTPS\Gurotopia> function Show-Range {
>>     param([string]$Path, [int]$Start, [int]$Count)
>>
>>     Write-Host "`n===== $Path =====" -ForegroundColor Cyan
>>
>>     if (!(Test-Path $Path)) {
>>         Write-Host "FILE NOT FOUND"
>>         return
>>     }
>>
>>     $lines = Get-Content $Path
>>     $end = [Math]::Min($Start + $Count - 1, $lines.Count)
>>
>>     for ($i = $Start; $i -le $end; $i++) {
>>         Write-Host ("{0,4}: {1}" -f $i, $lines[$i - 1])
>>     }
>> }
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> # A. ACCOUNT SAVE, LOAD, AND INVENTORY
PS C:\GTPS\Gurotopia> Show-Range "include/database/peer.cpp" 1 245

===== include/database/peer.cpp =====
   1: #include "pch.hpp"
   2: #include "items.hpp"
   3: #include "world.hpp"
   4: #include "onVariant/SetClothing.hpp"
   5: #include "onVariant/CountryState.hpp"
   6: #include "onVariant/ConsoleMessage.hpp"
   7: #include "commands/punch.hpp"
   8: #include "tools/string.hpp"
   9:
  10: #include "peer.hpp"
  11:
  12: bool peer::exists(const std::string &growid)
  13: {
  14:     ::hStmt hStmt{ "SELECT 1 FROM peer WHERE growid = ? LIMIT 1" };
  15:
  16:     MYSQL_BIND param = make_bind_in(growid); // WHERE
  17:     hStmt.bind_param(&param);
  18:     hStmt.execute();
  19:
  20:     return (!mysql_stmt_store_result(hStmt.pStmt) && mysql_stmt_num_rows(hStmt.pStmt) > 0);
  21: }
  22:
  23: ::blob slot::to_blob() const
  24: {
  25:     ::blob blob;
  26:     blob.i16(this->id);
  27:     blob.i16(this->count);
  28:
  29:     return blob;
  30: }
  31:
  32: template<typename T>
  33: void peer::mysql_insert(const std::string &column, const T &value)
  34: {
  35:     ::hStmt hStmt{ std::format("INSERT INTO peer ({}) VALUES (?)", column).c_str() };
  36:
  37:     MYSQL_BIND param = make_bind_in(value); // VALUES
  38:     hStmt.bind_param(&param);
  39:     hStmt.execute();
  40: }
  41: template void peer::mysql_insert<signed>(const std::string&, const signed&);
  42: template void peer::mysql_insert<unsigned>(const std::string&, const unsigned&);
  43: template void peer::mysql_insert<float>(const std::string&, const float&);
  44: template void peer::mysql_insert<std::string>(const std::string&, const std::string&);
  45:
  46: template<typename T>
  47: void peer::mysql_update(const std::string &column, const T &value)
  48: {
  49:     ::hStmt hStmt{ std::format("UPDATE peer SET {} = ? WHERE growid = ?", column).c_str() };
  50:
  51:     MYSQL_BIND params[2] = {
  52:         make_bind_in(value),       // SET
  53:         make_bind_in(this->growid) // WHERE
  54:     };
  55:     hStmt.bind_param(params);
  56:     hStmt.execute();
  57: }
  58: template void peer::mysql_update<signed>(const std::string&, const signed&);
  59: template void peer::mysql_update<unsigned>(const std::string&, const unsigned&);
  60: template void peer::mysql_update<long long>(const std::string&, const long long&);
  61: template void peer::mysql_update<float>(const std::string&, const float&);
  62: template void peer::mysql_update<std::string>(const std::string&, const std::string&);
  63:
  64: template<typename T>
  65: T peer::mysql_select(const std::string &column, const std::string &arg, bool by_user_id)
  66: {
  67:     T value{};
  68:     ::hStmt hStmt{ std::format("SELECT {}({}) FROM peer WHERE {} = ? LIMIT 1", arg, column, by_user_id ? "uid" : "growid").c_str() };
  69:
  70:     MYSQL_BIND param = by_user_id ? make_bind_in(this->user_id) : make_bind_in(this->growid); // WHERE
  71:     hStmt.bind_param(&param);
  72:
  73:     u_long length = 0;
  74:     MYSQL_BIND result = make_bind_out(value);
  75:     result.length = &length;
  76:     mysql_stmt_bind_result(hStmt.pStmt, &result);
  77:
  78:     hStmt.execute();
  79:     hStmt.fetch();
  80:     if constexpr (std::is_same_v<T, std::string>)
  81:         value.resize(length);
  82:
  83:     return value;
  84: }
  85: /* since we will only select during mysql_select_all */ // @note add templates here if use select outside of this file.
  86: template std::string peer::mysql_select<std::string>(const std::string&, const std::string&, bool); // @note tile_change.cpp (World Lock owner name)
  87:
  88: void peer::mysql_select_all(bool by_user_id)
  89: {
  90:     this->user_id    = this->mysql_select<signed>("uid", "", by_user_id);
  91:     this->growid     = this->mysql_select<std::string>("growid", "", by_user_id);
  92:     this->password   = this->mysql_select<std::string>("password", "", by_user_id);
  93:   const unsigned role_value =
  94:           this->mysql_select<unsigned>("role", "", by_user_id);
  95:
  96:     this->role = role_value <= PLAYER ? static_cast<u_char>(role_value) : PLAYER;
  97:     this->created_at = this->mysql_select<std::time_t>("created_at", "UNIX_TIMESTAMP", by_user_id);
  98:     this->gems       = this->mysql_select<long long>("gems", "", by_user_id);
  99:     this->wl_storage = this->mysql_select<signed>("wl_storage", "", by_user_id);
 100:     this->level[0]   = this->mysql_select<signed>("level", "", by_user_id);
 101:     this->level[1]   = this->mysql_select<signed>("xp", "", by_user_id);
 102:
 103:     auto inventory = this->mysql_select<::blob>("inventory", "", by_user_id);
 104:
 105:     if (inventory.size() >= sizeof(int) + sizeof(short))
 106:     {
 107:         int pos{};
 108:         inventory.read_i32(this->slot_size, pos);
 109:
 110:         short size{};
 111:         inventory.read_i16(size, pos);
 112:
 113:         this->slots.resize(size);
 114:
 115:         for (::slot &slot : this->slots)
 116:         {
 117:             if (!inventory.read_i16(slot.id, pos)) break;
 118:             if (!inventory.read_i16(slot.count, pos)) break;
 119:         }
 120:     }
 121:     else
 122:     {
 123:         this->slot_size = 16;
 124:         this->slots.resize(3ull);
 125:         this->slots[0ull] = ::slot{18, 1};
 126:         this->slots[1ull] = ::slot{32, 1};
 127:         this->slots[2ull] = ::slot{9640, 1};
 128:
 129:         this->mysql_update_all();
 130:     }
 131: }
 132: ::blob peer::serialize_inventory() const
 133: {
 134:     ::blob blob{};
 135:     blob.i32(this->slot_size);
 136:     blob.i16(this->slots.size());
 137:     for (const ::slot &slot : this->slots)
 138:     {
 139:         blob.push_back(slot.to_blob());
 140:     }
 141:     return blob;
 142: }
 143:
 144: void peer::mysql_update_all()
 145: {
 146:     if (this->growid.empty()) return;
 147:
 148:     ::hStmt hStmt{
 149:     "UPDATE peer SET inventory = ?, gems = ?, level = ?, "
 150:     "xp = ?, wl_storage = ?, role = ? WHERE growid = ?"
 151: };
 152:     const ::blob inventory = this->serialize_inventory();
 153:     const int level_value = this->level[0], xp_value = this->level[1];
 154:   const unsigned role_value = static_cast<unsigned>(this->role);
 155:
 156:   MYSQL_BIND params[7] = {
 157:           make_bind_in(inventory),
 158:           make_bind_in(this->gems),
 159:           make_bind_in(level_value),
 160:           make_bind_in(xp_value),
 161:           make_bind_in(this->wl_storage),
 162:           make_bind_in(role_value),
 163:           make_bind_in(this->growid)
 164:   };
 165:     hStmt.bind_param(params);
 166:     hStmt.execute();
 167: }
 168:
 169: bool peer::load(const std::string &growid, const std::string password)
 170: {
 171:     this->growid = growid;
 172:     if (!this->exists(growid))
 173:     {
 174:         return false;
 175:     }
 176:     this->mysql_select_all(false);
 177:     if (password.empty() || this->password != password)
 178:     {
 179:         return false;
 180:     }
 181:     return true;
 182: }
 183:
 184: bool peer::load_by_uid(int uid)
 185: {
 186:     this->user_id = uid;
 187:     this->mysql_select_all(true);
 188:     return !this->growid.empty();
 189: }
 190:
 191: bool peer::create_account(const std::string &growid, const std::string &password)
 192: {
 193:     this->growid = growid;
 194:     if (this->exists(growid))
 195:     {
 196:         return false;
 197:     }
 198:     this->mysql_insert("growid", growid);
 199:     this->mysql_update("password", password);
 200:
 201:     this->slots.resize(3ull); // @note default starter items
 202:     this->slots[0ull] = ::slot{18, 1};   // @note fist
 203:     this->slots[1ull] = ::slot{32, 1};   // @note wrench
 204:     this->slots[2ull] = ::slot{9640, 1}; // @note my first world lock
 205:
 206:     this->mysql_update_all();
 207:     this->mysql_select_all(false);
 208:     return true;
 209: }
 210:
 211: peer::~peer()
 212: {
 213:     this->mysql_update_all();
 214: }
 215:
 216: u_short peer::emplace(::slot slot)
 217: {
 218:     auto it = std::ranges::find(this->slots, slot.id, &::slot::id);
 219:
 220:     if (it != this->slots.end())
 221:     {
 222:         const u_short excess = std::max(0, (it->count + slot.count) - 200);
 223:         it->count = std::min(it->count + slot.count, 200);
 224:         if (it->count == 0)
 225:         {
 226:             const ::item &item = id_to_item(it->id);
 227:             if (item.cloth_type != clothing::NONE) this->clothing[item.cloth_type] = 0;
 228:         }
 229:         return excess;
 230:     }
 231:     this->slots.emplace_back(std::move(slot)); // @note no such item in inventory, so we create a new entry.
 232:     return 0;
 233: }
 234:
 235: u_short peer::have_slot(::slot slot)
 236: {
 237:     auto it = std::ranges::find(this->slots, slot.id, &::slot::id);
 238:
 239:     if (it != this->slots.end())
 240:         return it->count;
 241:     return 0;
 242: }
 243:
 244: void peer::add_xp(ENetEvent &event, u_short value)
 245: {
PS C:\GTPS\Gurotopia> Show-Range "include/database/peer.hpp" 80 175

===== include/database/peer.hpp =====
  80:
  81: enum pstate : int
  82: {
  83:     S_GHOST       = 0x00000001,
  84:     S_DOUBLE_JUMP = 0x00000002,
  85:     S_DUCT_TAPE   = 0x00002000
  86: };
  87:
  88: class peer {
  89: public:
  90:     ~peer();
  91:
  92:     bool load(const std::string &growid, const std::string password);
  93:     bool load_by_uid(int uid);
  94:     bool create_account(const std::string &growid, const std::string &password);
  95:
  96:     bool exists(const std::string &growid);
  97:
  98:     template<typename T>
  99:     void mysql_insert(const std::string &column, const T &value);
 100:
 101:     template<typename T>
 102:     void mysql_update(const std::string &column, const T &value);
 103:
 104:     template<typename T>
 105:     T    mysql_select(const std::string &column, const std::string &arg = "", bool by_user_id = false); // @note by_user_id: WHERE uid instead of WHERE growid
 106:     void mysql_select_all(bool by_user_id = false);
 107:     void mysql_update_all();
 108:
 109:     int user_id{}; // @note unqiue user id.
 110:     std::string growid{""}, password{""};
 111:     std::time_t created_at{}; // @note when inserted in SQL (account age)
 112:     u_char role{PLAYER};
 113:     std::array<float, 10ull> clothing{}; // @note peer's clothing {id, clothing::}
 114:     u_char punch_effect{}; // @note last equipped clothing that has a effect. supporting 0-255 effects.
 115:
 116:     int netid{}; // @note peer's netid is world identity. this will be useful for many packet sending
 117:     u_char icon{}; // @note typing or busy icon
 118:     std::string display_growid{}; // @note use this for displaying growid, never use ::growid
 119:     std::string country{};
 120:     float game_version{0.0f};
 121:
 122:     u_int skin_color{ 2527912447 };
 123:     u_int hair_color = bgra::GREEN | bgra::GREEN | bgra::RED | bgra::ALPHA; // @note value declines for specfic hair colors
 124:
 125:     int state{}; // @note using pstate::
 126:     bool muted{}; // @note server-side chat restriction loaded from admin_mutes
 127:
 128:     ::Billboard billboard{};
 129:
 130:     ::pos pos{}; // @note position 1D {x, y}
 131:     ::pos rest_pos{}; // @note respawn position {x, y}
 132:     bool facing_left{}; // @note peer is directed towards the left direction
 133:     short pain_hp{ 10 };
 134:
 135:     int slot_size{16}; // @note amount of slots this peer has | were talking total slots not itemed slots, to get itemed slots do slot.size()
 136:     std::vector<slot> slots{}; // @note an array of each slot. storing {id, count}
 137:     /*
 138:     * @brief set slot::count to nagative value if you want to remove an amount.
 139:     * @return the remaining amount if exeeds 200. e.g. emplace(slot{0, 201}) returns 1.
 140:     */
 141:     u_short emplace(::slot slot);
 142:     /*
 143:     * @brief check if item exists in inventory (::slots)
 144:     * @return slot count (0 if not exist)
 145:     */
 146:     u_short have_slot(::slot slot);
 147:     ::blob serialize_inventory() const;
 148:
 149:     std::vector<short> fav{};
 150:
 151:     long long gems{0};
 152:     int wl_storage{0};
 153:     std::array<u_short, 2ull> level{ 1, 0 }; // {level, xp} XP formula credits: https://www.growtopiagame.com/forums/member/553046-kasete
 154:     /*
 155:     * @brief add XP safely, this function also handles level up.
 156:     */
 157:     void add_xp(ENetEvent &event, u_short value);
 158:
 159:     /*
 160:     * @brief recalculate transient effects based on clothing.
 161:     */
 162:     void update_effects();
 163:
 164:     std::array<std::string, 6ull> recent_worlds{}; // @note recent worlds, a list of 6 worlds, once it reaches 7 it'll be replaced by the oldest
 165:     std::array<std::string, 200ull> my_worlds{}; // @note first 200 relevant worlds locked by peer.
 166:
 167:     std::deque<u_int> messages; // @note last 5 que messages sent time, this is used to check for spamming
 168:
 169:     u_short fires_removed{};
 170:     u_short gbc_pity{}; // @note GBC pity; for each 100 will receive super GBC
 171:
 172:     /* @todo move outside */
 173:     std::vector<::slot> trade_offers{};
 174:     bool trade_accepted = false;
 175: };
 176:
 177: /*
 178:  * Build a role-aware character name. Keep the native Growtopia staff state
 179:  * flags (mstate/smstate) as well; this text badge makes the three Gurotopia
 180:  * staff ranks distinguishable even though the client exposes only two flags.
 181:  * name_color preserves world-owner/access coloring supplied by the caller.
 182:  */
 183: inline std::string make_peer_display_growid(
 184:     u_char value,
 185:     const std::string& growid,
 186:     const std::string& name_color = "`w")
 187: {
 188:     const char* badge = "";
 189:     switch (value)
 190:     {
 191:         case OWNER:     badge = "`b[OWNER]`` "; break;
 192:         case DEVELOPER: badge = "`6[DEVELOPER]`` "; break;
 193:         case MODERATOR: badge = "`3[MOD]`` "; break;
 194:         default: break;
 195:     }
 196:     return std::format("{}{}{}{}", badge, name_color, growid, "``");
 197: }
 198:
 199: extern ENetHost* host;
 200:
 201: /* @brief search specific peer(s), used in peers() */
 202: enum class PeerSearch : u_char
 203: {
 204:     WORLD = 0,
 205:     EVERYONE = 1
 206: };
 207: template <typename Func>
 208: void peers(const std::string &world, PeerSearch search, Func &&fun)
 209: {
 210:     for (ENetPeer *peer = host->peers, *end = peer + host->peerCount; peer != end; ++peer)
 211:     {
 212:         if (peer->state != ENET_PEER_STATE_CONNECTED) continue;
 213:
 214:         if (search == PeerSearch::WORLD)
 215:         {
 216:             ::peer *pPeer = static_cast<::peer*>(peer->data);
 217:             if (pPeer->netid == 0 || (pPeer->recent_worlds.back() != world)) continue;
 218:         }
 219:         std::forward<Func>(fun)(peer);
 220:     }
 221: }
 222:
 223: extern void safe_disconnect_peers(int signal);
 224:
 225: class gameMessage {
 226:     public:
 227:         int packet_create{ 03 }; // @note NET_MESSAGE_GAME_MESSAGE
 228:
 229:         std::string message{};
 230:         u_char terminator{ '\0' };
 231: };
 232:
 233: extern ::blob compressMessage(const gameMessage &gameMessage);
 234:
 235: enum class gamePacketState : int
 236: {
 237:     UPDATE               = 0x00000004,
 238:     EXTENDED             = 0x00000008,
 239:     MOVE_LEFT            = 0x00000010,
 240:     MOVE_RIGHT           = 0x00000020,
 241:     HIT_BY_LAVA          = 0x00000040,
 242:     JUMP                 = 0x00000080,
 243:     ITEM_ACTIVATE_OBJECT = 0x00004000
 244: };
 245: class gamePacket {
 246: public:
 247:     int packet_create{ 04 }; // @note NET_MESSAGE_GAME_PACKET
 248:
 249:     int type{};
 250:     union
 251:     {
 252:         int netid{},
 253:             particle_effect;
 254:     };
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> # B. DATABASE TRANSACTION SUPPORT
PS C:\GTPS\Gurotopia> Show-Range "include/database/database.hpp" 1 240

===== include/database/database.hpp =====
   1: #pragma once
   2:
   3: #include <mysql/mysql.h>
   4:
   5: #include "tools/terminal.hpp"
   6:
   7: class mysql_gateway
   8: {
   9: public:
  10:     mysql_gateway() { mysql = mysql_init(NULL); }
  11:     ~mysql_gateway() { mysql_close(mysql); }
  12:
  13:     void create_table_if_not_exist();
  14:     bool column_found(const std::string &table, const std::string &column);
  15:     int alter_table(const std::string &table, const std::string &column);
  16:     void integrity();
  17:
  18:     void mysql_connect();
  19:     void load_login();
  20:
  21:     MYSQL *mysql{nullptr};
  22: private:
  23:     std::string host{"127.0.0.1"};
  24:     std::string user{"root"};
  25:     std::string passwd{""};
  26: };
  27: extern ::mysql_gateway db;
  28:
  29: class hStmt
  30: {
  31: public:
  32:     hStmt(const std::string &query);
  33:    ~hStmt();
  34:
  35:     hStmt           (const hStmt &) = delete;
  36:     hStmt &operator=(const hStmt &) = delete;
  37:
  38:     void bind_param(MYSQL_BIND *param);
  39:     void execute();
  40:     void fetch();
  41:
  42:     /* https://dev.mysql.com/doc/mysql-errors/8.4/en/client-error-reference.html */
  43:     void log_stmt_error();
  44:
  45:     MYSQL_STMT *pStmt;
  46: };
  47:
  48: #include <cstring> // linux
  49:
  50: struct blob
  51: {
  52:     /* @note template vibes */
  53:     void f32(float val) {
  54:         int size = mData.size();
  55:         mData.resize(size + sizeof(float));
  56:         memcpy(mData.data() + size, &val, sizeof(float));
  57:     }
  58:     void i32(int val)   {
  59:         int size = mData.size();
  60:         mData.resize(size + sizeof(int));
  61:         memcpy(mData.data() + size, &val, sizeof(int));
  62:     }
  63:     void u32(u_int val)   {
  64:         int size = mData.size();
  65:         mData.resize(size + sizeof(u_int));
  66:         memcpy(mData.data() + size, &val, sizeof(u_int));
  67:     }
  68:     void i16(short val) {
  69:         int size = mData.size();
  70:         mData.resize(size + sizeof(short));
  71:         memcpy(mData.data() + size, &val, sizeof(short));
  72:     }
  73:     void u8(u_char val) {
  74:         mData.push_back(val);
  75:     }
  76:
  77:     bool read_f32(float &val, int &pos)
  78:     {
  79:         if (pos + (int)sizeof(float) > (int)mData.size()) return false;
  80:         memcpy(&val, mData.data()+pos, sizeof(float));
  81:         pos += sizeof(float);
  82:         return true;
  83:     }
  84:     bool read_i32(int &val, int &pos)
  85:     {
  86:         if (pos + (int)sizeof(int) > (int)mData.size()) return false;
  87:         memcpy(&val, mData.data()+pos, sizeof(int));
  88:         pos += sizeof(int);
  89:         return true;
  90:     }
  91:     bool read_u32(u_int &val, int &pos)
  92:     {
  93:         if (pos + (int)sizeof(u_int) > (int)mData.size()) return false;
  94:         memcpy(&val, mData.data()+pos, sizeof(u_int));
  95:         pos += sizeof(u_int);
  96:         return true;
  97:     }
  98:     bool read_i16(short &val, int &pos)
  99:     {
 100:         if (pos + (int)sizeof(short) > (int)mData.size()) return false;
 101:         memcpy(&val, mData.data()+pos, sizeof(short));
 102:         pos += sizeof(short);
 103:         return true;
 104:     }
 105:     bool read_u16(u_short &val, int &pos)
 106:     {
 107:         if (pos + (int)sizeof(u_short) > (int)mData.size()) return false;
 108:         memcpy(&val, mData.data()+pos, sizeof(u_short));
 109:         pos += sizeof(u_short);
 110:         return true;
 111:     }
 112:     bool read_i8(char &val, int &pos)
 113:     {
 114:         if (pos + (int)sizeof(char) > (int)mData.size()) return false;
 115:         memcpy(&val, mData.data()+pos, sizeof(char));
 116:         pos += sizeof(char);
 117:         return true;
 118:     }
 119:     bool read_u8(u_char &val, int &pos)
 120:     {
 121:         if (pos + (int)sizeof(u_char) > (int)mData.size()) return false;
 122:         memcpy(&val, mData.data()+pos, sizeof(u_char));
 123:         pos += sizeof(u_char);
 124:         return true;
 125:     }
 126:
 127:
 128:     void push_back(const blob &blob)
 129:     {
 130:         const auto &data = blob.data();
 131:
 132:         mData.insert(mData.end(), data.cbegin(), data.cend());
 133:     }
 134:     [[nodiscard]] const std::vector<u_char> &data() const noexcept {
 135:         return mData;
 136:     }
 137:     [[nodiscard]] std::vector<u_char> &data() noexcept {
 138:         return mData;
 139:     }
 140:     [[nodiscard]] constexpr std::size_t size() const noexcept {
 141:         return mData.size();
 142:     }
 143:     constexpr void resize(std::size_t __new_size)
 144:     {
 145:         mData.resize(__new_size);
 146:     }
 147:
 148: private:
 149:     std::vector<u_char> mData;
 150: };
 151:
 152: extern MYSQL_BIND make_bind_in(const signed &buffer);
 153: extern MYSQL_BIND make_bind_in(const unsigned &buffer);
 154: extern MYSQL_BIND make_bind_in(const long &buffer);
 155: extern MYSQL_BIND make_bind_in(const long long &buffer);
 156: extern MYSQL_BIND make_bind_in(const float &buffer);
 157: extern MYSQL_BIND make_bind_in(const std::string &buffer);
 158: extern MYSQL_BIND make_bind_in(const std::vector<u_char> &buffer);
 159: extern MYSQL_BIND make_bind_in(const ::blob &buffer);
 160:
 161: extern MYSQL_BIND make_bind_out(signed &buffer);
 162: extern MYSQL_BIND make_bind_out(unsigned &buffer);
 163: extern MYSQL_BIND make_bind_out(long &buffer);
 164: extern MYSQL_BIND make_bind_out(long long &buffer);
 165: extern MYSQL_BIND make_bind_out(float &buffer);
 166: extern MYSQL_BIND make_bind_out(std::string &buffer);
 167: extern MYSQL_BIND make_bind_out(std::vector<u_char> &buffer);
 168: extern MYSQL_BIND make_bind_out(::blob &buffer);
PS C:\GTPS\Gurotopia> Show-Range "include/database/database.cpp" 1 220

===== include/database/database.cpp =====
   1: #include "pch.hpp"
   2:
   3: #include "tools/terminal.hpp"
   4:
   5: #include <fstream>
   6:
   7: #include "database.hpp"
   8:
   9: ::mysql_gateway db;
  10:
  11: void mysql_gateway::create_table_if_not_exist()
  12: {
  13:     int error;
  14:     error = mysql_query(mysql,
  15:         "CREATE TABLE IF NOT EXISTS peer ("
  16:         "uid INT AUTO_INCREMENT PRIMARY KEY,"
  17:         "growid VARCHAR(18) UNIQUE,"
  18:         "password VARCHAR(18),"
  19:           "role TINYINT UNSIGNED NOT NULL DEFAULT 3,"
  20:         "created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,"
  21:         "inventory BLOB,"
  22:         "gems BIGINT DEFAULT 0,"
  23:         "wl_storage INT DEFAULT 0,"
  24:         "level INT DEFAULT 1,"
  25:         "xp INT DEFAULT 0"
  26:     ")");
  27:     error = mysql_query(mysql,
  28:         "CREATE TABLE IF NOT EXISTS world ("
  29:         "name VARCHAR(24) NOT NULL PRIMARY KEY,"
  30:         "owner INT DEFAULT 0,"
  31:         "blocks BLOB,"
  32:         "objects BLOB"
  33:     ")");
  34:
  35:     if (error) print(mysql_error(mysql));
  36: }
  37:
  38: bool mysql_gateway::column_found(const std::string &table, const std::string &column)
  39: {
  40:     mysql_query(mysql, std::format(
  41:         "SHOW COLUMNS FROM {} WHERE Field = '{}'",
  42:         table, column).c_str()
  43:     );
  44:     MYSQL_RES *res = mysql_store_result(mysql);
  45:
  46:     my_ulonglong rows = mysql_num_rows(res);
  47:     mysql_free_result(res);
  48:     return (rows > 0);
  49: }
  50:
  51: int mysql_gateway::alter_table(const std::string &table, const std::string &column)
  52: {
  53:     return mysql_query(mysql, std::format("ALTER TABLE {} ADD COLUMN {}", table, column).c_str());
  54: }
  55:
  56: /* @note i use this for new columns. this could be removed once i 100% copy rgt. */
  57: void mysql_gateway::integrity()
  58: {
  59:     if (!column_found("peer", "gems"))  alter_table("peer", "gems BIGINT DEFAULT 0");
  60:     if (!column_found("peer", "level")) alter_table("peer", "level INT DEFAULT 1");
  61:     if (!column_found("peer", "xp"))    alter_table("peer", "xp INT DEFAULT 0");
  62:     if (!column_found("peer", "wl_storage")) alter_table("peer", "wl_storage INT DEFAULT 0");
  63:   if (!column_found("peer", "role")) alter_table("peer", "role TINYINT UNSIGNED NOT NULL DEFAULT 3");
  64: }
  65:
  66: void mysql_gateway::mysql_connect()
  67: {
  68:     if (!mysql_real_connect(mysql, this->host.c_str(), this->user.c_str(), this->passwd.c_str(), NULL, 3306u, NULL, 0ul))
  69:     {
  70:         print(mysql_error(mysql));
  71:     }
  72:     else print(std::format("connected to MariaDB server on {}:{}", mysql->host, mysql->port).c_str());
  73:
  74:     mysql_query(mysql, "CREATE DATABASE IF NOT EXISTS gurotopia");
  75:     mysql_select_db(mysql, "gurotopia");
  76:
  77:     create_table_if_not_exist();
  78:     integrity();
  79: }
  80:
  81: void mysql_gateway::load_login()
  82: {
  83:     std::ifstream istrm("mysql_login.txt");
  84:     if (!istrm.is_open())
  85:     {
  86:         std::ofstream ostrm("mysql_login.txt");
  87:         ostrm <<
  88:             std::format(
  89:                 "host|{}\n"
  90:                 "user|{}\n"
  91:                 "password|{}",
  92:                 this->host, this->user, this->passwd
  93:             );
  94:     } // @note close ostrm
  95:     else
  96:     {
  97:         for (std::string line; std::getline(istrm, line); )
  98:         {
  99:             ::hPipe hPipe{ line };
 100:
 101:             if (!hPipe["host"].empty()) this->host = hPipe["host"];
 102:             else if (!hPipe["user"].empty()) this->user = hPipe["user"];
 103:             else if (!hPipe["password"].empty()) this->passwd = hPipe["password"];
 104:         }
 105:     } // @note delete pipes
 106: }
 107:
 108:
 109: hStmt::hStmt(const std::string &query)
 110: {
 111:     this->pStmt = mysql_stmt_init(db.mysql);
 112:     if (!pStmt)
 113:     {
 114:         log_stmt_error();
 115:     }
 116:     if (mysql_stmt_prepare(pStmt, query.c_str(), (u_long)query.size()))
 117:     {
 118:         log_stmt_error();
 119:     }
 120: }
 121: hStmt::~hStmt()
 122: {
 123:     if (mysql_stmt_close(pStmt))
 124:     {
 125:         log_stmt_error();
 126:     }
 127: }
 128:
 129: void hStmt::bind_param(MYSQL_BIND *param)
 130: {
 131:     if (mysql_stmt_bind_param(pStmt, param)) log_stmt_error();
 132: }
 133: void hStmt::execute()
 134: {
 135:     if (mysql_stmt_execute(pStmt)) log_stmt_error();
 136: }
 137: void hStmt::fetch()
 138: {
 139:     int value = mysql_stmt_fetch(pStmt);
 140:     if (value == 1 || value == MYSQL_DATA_TRUNCATED) log_stmt_error();
 141:     else if (value == 0 || value == MYSQL_NO_DATA) /*@todo do something later...*/; // @note success
 142: }
 143: void hStmt::log_stmt_error()
 144: {
 145:     print(mysql_stmt_error(pStmt));
 146: }
 147: /* ~ hStmt ~ */
 148:
 149:
 150:
 151: MYSQL_BIND make_bind_in(const signed &buffer)
 152: {
 153:     return { .buffer = (void*)&buffer, .buffer_type = MYSQL_TYPE_LONG };
 154: }
 155: MYSQL_BIND make_bind_in(const unsigned &buffer)
 156: {
 157:     return { .buffer = (void*)&buffer, .buffer_type = MYSQL_TYPE_LONG, .is_unsigned = true };
 158: }
 159: MYSQL_BIND make_bind_in(const long &buffer)
 160: {
 161:     return { .buffer = (void*)&buffer, .buffer_type = MYSQL_TYPE_LONG };
 162: }
 163: MYSQL_BIND make_bind_in(const long long &buffer)
 164: {
 165:     return { .buffer = (void*)&buffer, .buffer_type = MYSQL_TYPE_LONGLONG };
 166: }
 167: MYSQL_BIND make_bind_in(const float &buffer)
 168: {
 169:     return { .buffer = (void*)&buffer, .buffer_type = MYSQL_TYPE_FLOAT };
 170: }
 171: MYSQL_BIND make_bind_in(const std::string &buffer)
 172: {
 173:     return { .buffer = (void*)buffer.c_str(), .buffer_length = (u_long)buffer.size(), .buffer_type = MYSQL_TYPE_STRING };
 174: }
 175: MYSQL_BIND make_bind_in(const std::vector<u_char> &buffer)
 176: {
 177:     return { .buffer = (void*)buffer.data(), .buffer_length = (u_long)buffer.size(), .buffer_type = MYSQL_TYPE_BLOB };
 178: }
 179: MYSQL_BIND make_bind_in(const ::blob &buffer)
 180: {
 181:     return { .buffer = (void*)buffer.data().data(), .buffer_length = (u_long)buffer.size(), .buffer_type = MYSQL_TYPE_BLOB };
 182: }
 183:
 184: MYSQL_BIND make_bind_out(signed &buffer)
 185: {
 186:     return { .buffer = &buffer, .buffer_type = MYSQL_TYPE_LONG };
 187: }
 188: MYSQL_BIND make_bind_out(unsigned &buffer)
 189: {
 190:     return { .buffer = &buffer, .buffer_type = MYSQL_TYPE_LONG, .is_unsigned = true };
 191: }
 192: MYSQL_BIND make_bind_out(long &buffer)
 193: {
 194:     return { .buffer = &buffer, .buffer_type = MYSQL_TYPE_LONG };
 195: }
 196: MYSQL_BIND make_bind_out(long long &buffer)
 197: {
 198:     return { .buffer = &buffer, .buffer_type = MYSQL_TYPE_LONGLONG };
 199: }
 200: MYSQL_BIND make_bind_out(float &buffer)
 201: {
 202:     return { .buffer = &buffer, .buffer_type = MYSQL_TYPE_FLOAT };
 203: }
 204: MYSQL_BIND make_bind_out(std::string &buffer)
 205: {
 206:     buffer.resize(1024, '\0');
 207:
 208:     return { .buffer = buffer.data(), .buffer_length = (u_long)buffer.size(), .buffer_type = MYSQL_TYPE_STRING };
 209: }
 210: MYSQL_BIND make_bind_out(std::vector<u_char> &buffer)
 211: {
 212:     buffer.resize(cord(0, 60)* sizeof(::block));
 213:
 214:     return { .buffer = buffer.data(), .buffer_length = (u_long)buffer.size(), .buffer_type = MYSQL_TYPE_BLOB };
 215: }
 216: MYSQL_BIND make_bind_out(::blob &buffer)
 217: {
 218:     buffer.resize(cord(0, 60)* sizeof(::block));
 219:
 220:     return { .buffer = buffer.data().data(), .buffer_length = (u_long)buffer.size(), .buffer_type = MYSQL_TYPE_BLOB };
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> # C. DISCONNECT AND PLAYER LIFECYCLE
PS C:\GTPS\Gurotopia> Write-Host "`n===== EVENT TYPE FILES ====="

===== EVENT TYPE FILES =====
PS C:\GTPS\Gurotopia> Get-ChildItem .\include\eventType -File |
>>     Select-Object Name,Length

Name           Length
----           ------
connect.cpp       840
connect.hpp        54
disconnect.cpp    142
disconnect.hpp     56
receive.cpp      1980
receive.hpp        53
_eventType.cpp    293
_eventType.hpp     78


PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Show-Range "include/eventType/disconnect.cpp" 1 180

===== include/eventType/disconnect.cpp =====
   1: #include "pch.hpp"
   2:
   3: #include "action/quit.hpp"
   4:
   5: #include "disconnect.hpp"
   6:
   7: void disconnect(ENetEvent& event)
   8: {
   9:     action::quit(event, "");
  10: }
PS C:\GTPS\Gurotopia> Show-Range "main.cpp" 1 180

===== main.cpp =====
   1: /*
   2:     @copyright gurotopia (c) 2024-05-25
   3:     @version parent SHA: 313310dc606c852ed72b64e7e325a15eee3be42b 2026-11-3
   4: */
   5: #include "include/pch.hpp"
   6: #include "include/eventType/_eventType.hpp"
   7:
   8: #include "include/database/shouhin.hpp" // @include parse_store()
   9: #include "include/https/https.hpp" // @include https::listener()
  10: #include "include/https/server_data.hpp" // @include gServer_data
  11: #include "include/database/database.hpp"
  12: #include "include/admin/admin.hpp"
  13: #include "include/automate/holiday.hpp"
  14: #include "include/tools/terminal.hpp"
  15:
  16: #include <csignal>
  17: #include <thread>
  18:
  19: namespace
  20: {
  21:     volatile std::sig_atomic_t gSignal = 0;
  22: }
  23: static void signal_handler(int signal) { gSignal = signal; }
  24:
  25: int main()
  26: {
  27:     std::signal(SIGINT, signal_handler);
  28: #ifdef SIGHUP // @note unix
  29:     std::signal(SIGHUP, signal_handler); // @note PuTTY, SSH problems
  30: #endif
  31:
  32:     mysql_library_init(0, NULL, NULL);
  33:     enet_initialize();
  34:     {
  35:         gServer_data.init(); // @note ./server_data.php
  36:         std::thread(&https::listener).detach();
  37:
  38:         ENetAddress address{
  39:             .type = ENET_ADDRESS_TYPE_IPV4,
  40:             .port = gServer_data.port
  41:         };
  42:         host = enet_host_create (ENET_ADDRESS_TYPE_IPV4, &address, 50ull/* max peer count */, 2ull, 0u, 0u);
  43:     } // @note delete address
  44:     host->usingNewPacketForServer = true;
  45:     host->checksum = enet_crc32;
  46:     enet_host_compress_with_range_coder(host);
  47:
  48:     db.load_login(); // @note ./mysql_login.txt
  49:     db.mysql_connect();
  50:     admin::initialize();
  51:
  52:     decode_items_dat();
  53:     parse_store();
  54:     check_for_holiday();
  55:
  56:     ENetEvent event{};
  57:     while (!gSignal)
  58:         while (enet_host_service(host, &event, 1000/*ms*/) > 0)
  59:             eventType_pool[event.type](event);
  60:
  61:     safe_disconnect_peers(gSignal);
  62:     enet_host_destroy(host);
  63:     if (host != nullptr) host = nullptr;
  64:     enet_deinitialize();
  65:     mysql_library_end();
  66:
  67:     print("killed gurotopia! [EXIT_SUCCESS]");
  68:     return EXIT_SUCCESS;
  69: }
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> # D. DROP AND PICKUP
PS C:\GTPS\Gurotopia> Show-Range "include/action/drop.cpp" 1 180

===== include/action/drop.cpp =====
   1: #include "pch.hpp"
   2:
   3: #include "tools/create_dialog.hpp"
   4:
   5: #include "drop.hpp"
   6:
   7: void action::drop(ENetEvent& event, const std::string& header)
   8: {
   9:     const std::string &itemID = readch(header, '|')[4];
  10:
  11:     const ::item &item = id_to_item(atoi(itemID.c_str()));
  12:
  13:     if (item.cat & CAT_UNTRADEABLE)
  14:     {
  15:         send_varlist(event.peer, { "OnTextOverlay", "You can't drop that." });
  16:         return;
  17:     }
  18:     ::peer *pPeer = static_cast<::peer*>(event.peer->data);
  19:
  20:     for (const ::slot &slot : pPeer->slots)
  21:         if (slot.id == item.id)
  22:         {
  23:             send_varlist(event.peer, {
  24:                 "OnDialogRequest",
  25:                 create_dialog()
  26:                     .set_default_color("`o")
  27:                     .add_label_with_icon("big", std::format("`wDrop {}``", item.raw_name), item.id)
  28:                     .add_textbox("How many to drop?")
  29:                     .add_text_input("count", "", slot.count, 5)
  30:                     .embed_data("itemID", item.id)
  31:                     .end_dialog("drop_item")
  32:             });
  33:             return;
  34:         }
  35: }
PS C:\GTPS\Gurotopia> Show-Range "include/gamePacket/item_activate_object.cpp" 1 200

===== include/gamePacket/item_activate_object.cpp =====
   1: #include "pch.hpp"
   2:
   3: #include "onVariant/SetBux.hpp"
   4: #include "onVariant/ConsoleMessage.hpp"
   5:
   6: #include "item_activate_object.hpp"
   7:
   8: void item_activate_object(ENetEvent& event, ::gamePacket gamePacket)
   9: {
  10:     ::peer *pPeer = static_cast<::peer*>(event.peer->data);
  11:
  12:     auto world = std::ranges::find(worlds, pPeer->recent_worlds.back(), &::world::name);
  13:     if (world == worlds.end()) return;
  14:
  15:     auto object = std::ranges::find(world->objects, gamePacket.id, &::object::uid);
  16:     if (object == world->objects.end()) return; // @note already picked up (the game can ask twice)
  17:
  18:     u_short left = 0;
  19:     if (object->id != 112/*gem*/)
  20:     {
  21:         const ::item &item = id_to_item(object->id);
  22:
  23:         const u_short remember_count = object->count;
  24:         left = pPeer->emplace(::slot(object->id, remember_count)); // @return remains after reaching 200
  25:         const u_short collected = remember_count - left;
  26:         if (collected ==/*unsigned*/ 0) return; // @note backpack full: leave it where it is
  27:
  28:         on::ConsoleMessage(event.peer, (item.rarity >= 999) ?
  29:             std::format("Collected `w{} {}``.",                collected, item.raw_name) :
  30:             std::format("Collected `w{} {}``. Rarity: `w{}``", collected, item.raw_name, item.rarity)
  31:         );
  32:     }
  33:     else
  34:     {
  35:         pPeer->gems += object->count;
  36:         pPeer->mysql_update("gems", pPeer->gems);
  37:         on::SetBux(event);
  38:     }
  39:     remove_object(event, object->uid);
  40:     const ::object remember_object = *object;
  41:     world->objects.erase(object); // @note erase before add_object(), which can move the list and break the iterator
  42:
  43:     if (left > 0) add_object(event, ::slot(remember_object.id, left), remember_object.pos, *world); // @note the rest stays on the ground
  44: }
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> # E. DROP FUNCTION CALLS
PS C:\GTPS\Gurotopia> Get-ChildItem .\include -Recurse -File -Include *.cpp,*.hpp,*.h |
>>     Select-String -Pattern 'merge_object|add_object|remove_object|add_drop|modify_item_inventory' `
>>     -Context 2,4

  include\action\dialog_return\drop_item.cpp:53:
  include\action\dialog_return\drop_item.cpp:54:    const short count = std::min(requested_count, slot_it->count);
> include\action\dialog_return\drop_item.cpp:55:    modify_item_inventory(event, ::slot(item_id, -count));
  include\action\dialog_return\drop_item.cpp:56:
  include\action\dialog_return\drop_item.cpp:57:    const float x_neighbor = pPeer->facing_left ? pPeer->pos.x - 32 : p
Peer->pos.x + 32;
> include\action\dialog_return\drop_item.cpp:58:    add_drop(event, { item_id, count }, { x_neighbor, pPeer->pos.y }, *
world);
  include\action\dialog_return\drop_item.cpp:59:}
  include\action\dialog_return\find_item.cpp:31:    }
  include\action\dialog_return\find_item.cpp:32:
> include\action\dialog_return\find_item.cpp:33:    modify_item_inventory(event, ::slot(parsed_id, 200));
  include\action\dialog_return\find_item.cpp:34:}
  include\action\dialog_return\trash_item.cpp:50:
  include\action\dialog_return\trash_item.cpp:51:    const short count = std::min(requested_count, slot_it->count);
> include\action\dialog_return\trash_item.cpp:52:    modify_item_inventory(event, ::slot(item_id, -count));
  include\action\dialog_return\trash_item.cpp:53:    on::ConsoleMessage(event.peer, std::format("{} `w{}`` recycled, `w
0`` gems earned.", count, item.raw_name));
  include\action\dialog_return\trash_item.cpp:54:}
  include\action\buy.cpp:131:                    send_inventory_state(event); // @note update the new slots
  include\action\buy.cpp:132:                }
> include\action\buy.cpp:133:                else modify_item_inventory(event, {item.first, item.second});
  include\action\buy.cpp:134:                received.append(std::format("{}, ", raw_name)); // @todo add green text to
 rare items, or something cool.
  include\action\buy.cpp:135:            }
  include\action\buy.cpp:136:            send_varlist(event.peer, { "OnStorePurchaseResult", (_tab < 5) ?
  include\action\buy.cpp:137:                std::format(
  include\action\buy.cpp:147:                on::SetBux(event);
  include\action\buy.cpp:148:            }
> include\action\buy.cpp:149:            else modify_item_inventory(event, ::slot(growtoken->id, -growtoken_cost));
  include\action\buy.cpp:150:            break;
  include\action\buy.cpp:151:        }
  include\action\buy.cpp:152:    }
  include\action\buy.cpp:153:}
  include\action\worldlock_storage_modify_amount.cpp:36:    else convert_lock(amount, wl, dl, bgl, str);
  include\action\worldlock_storage_modify_amount.cpp:37:
> include\action\worldlock_storage_modify_amount.cpp:38:    if (bgl > 0) modify_item_inventory(event, ::slot(7188, -(ty
pe)*bgl));
> include\action\worldlock_storage_modify_amount.cpp:39:    if (dl  > 0) modify_item_inventory(event, ::slot(1796, -(ty
pe)*dl));
> include\action\worldlock_storage_modify_amount.cpp:40:    if (wl  > 0) modify_item_inventory(event, ::slot(242,  -(ty
pe)*wl));
  include\action\worldlock_storage_modify_amount.cpp:41:
  include\action\worldlock_storage_modify_amount.cpp:42:    if (type == -1)
  include\action\worldlock_storage_modify_amount.cpp:43:    {
  include\action\worldlock_storage_modify_amount.cpp:44:        std::string message = std::format("You collected {}.",
str);
  include\database\peer.cpp:257:        if (lvl == 50)
  include\database\peer.cpp:258:        {
> include\database\peer.cpp:259:            modify_item_inventory(event, ::slot{1400, 1}); // @note Mini Growtopian
  include\database\peer.cpp:260:            /* @todo based on account age give peer other items... */
  include\database\peer.cpp:261:        }
  include\database\peer.cpp:262:        if (lvl == 125) on::CountryState(event);
  include\database\peer.cpp:263:        send_varlist(event.peer, { "OnPlayerLeveledUp", (unsigned)lvl });
  include\database\world.cpp:411:}
  include\database\world.cpp:412:
> include\database\world.cpp:413:u_short modify_item_inventory(ENetEvent &event, ::slot slot)
  include\database\world.cpp:414:{
  include\database\world.cpp:415:    ::peer *pPeer = static_cast<::peer*>(event.peer->data);
  include\database\world.cpp:416:
  include\database\world.cpp:417:    ::gamePacket gamePacket{.id = slot.id};
  include\database\world.cpp:430:}
  include\database\world.cpp:431:
> include\database\world.cpp:432:void merge_object(ENetEvent &event, ::slot slot, const ::pos &pos, ::world &world)
  include\database\world.cpp:433:{
  include\database\world.cpp:434:    auto object = std::ranges::find_if(world.objects, [&](const ::object &object) {
  include\database\world.cpp:435:        return object.id == slot.id && (object.pos.by_32(true) == pos.by_32(true));
  include\database\world.cpp:436:    });
> include\database\world.cpp:437:    /* @todo avoid surpassing 200 and call add_object() for the remaining amount */ //
 @note future self reference peer::emplace()...
  include\database\world.cpp:438:    object->count += slot.count;
  include\database\world.cpp:439:
  include\database\world.cpp:440:    item_change_object(event, ::gamePacket{
  include\database\world.cpp:441:        .netid = (int)0xfffffffd,
  include\database\world.cpp:447:}
  include\database\world.cpp:448:
> include\database\world.cpp:449:void remove_object(ENetEvent& event, signed uid)
  include\database\world.cpp:450:{
  include\database\world.cpp:451:    ::peer *pPeer = static_cast<::peer*>(event.peer->data);
  include\database\world.cpp:452:
  include\database\world.cpp:453:    item_change_object(event, ::gamePacket{
  include\database\world.cpp:458:}
  include\database\world.cpp:459:
> include\database\world.cpp:460:int add_object(ENetEvent& event, ::slot slot, const ::pos& pos, ::world &world)
  include\database\world.cpp:461:{
  include\database\world.cpp:462:    /* @todo got a little messy */
  include\database\world.cpp:463:    auto object = std::ranges::find_if(world.objects, [&](const ::object &object) {
  include\database\world.cpp:464:        return object.id == slot.id && (object.pos.by_32(true) == pos.by_32(true));
  include\database\world.cpp:466:    if (object != world.objects.end() && object->count < 200/*@todo*/)
  include\database\world.cpp:467:    {
> include\database\world.cpp:468:        merge_object(event, slot, pos, world);
  include\database\world.cpp:469:        return object->uid;
  include\database\world.cpp:470:    }
  include\database\world.cpp:471:    ::object it = world.objects.emplace_back(::object(slot.id, slot.count, pos, ++worl
d.last_object_uid)); // @note a iterator ahead of time
  include\database\world.cpp:472:
  include\database\world.cpp:481:}
  include\database\world.cpp:482:
> include\database\world.cpp:483:void add_drop(ENetEvent &event, ::slot im, ::pos pos, ::world &world) // @todo
  include\database\world.cpp:484:{
> include\database\world.cpp:485:    add_object(event, im, ::pos{
  include\database\world.cpp:486:        pos.x + RandomRange(0, 16),
  include\database\world.cpp:487:        pos.y + RandomRange(0, 16)
  include\database\world.cpp:488:    }, world);
  include\database\world.cpp:489:}
  include\database\world.cpp:570:    {
  include\database\world.cpp:571:        on::ConsoleMessage(event.peer, "`oI'm so good at fighting fires, I rescused th
is `2Highly Combustible Box``!");
> include\database\world.cpp:572:        modify_item_inventory(event, {3090/*Combustible Box*/, 1});
  include\database\world.cpp:573:    }
  include\database\world.cpp:574:    pPeer->add_xp(event, 1);
  include\database\world.cpp:575:}
  include\database\world.cpp:576:
  include\database\world.hpp:185:* @return the remaining amount if exeeds 200. e.g. emplace(slot{0, 201}) returns 1.
  include\database\world.hpp:186:*/
> include\database\world.hpp:187:extern u_short modify_item_inventory(ENetEvent &event, ::slot slot);
  include\database\world.hpp:188:
  include\database\world.hpp:189:extern void item_change_object(ENetEvent& event, ::gamePacket gamePacket);
  include\database\world.hpp:190:
> include\database\world.hpp:191:extern void merge_object(ENetEvent& event, ::slot slot, const ::pos &pos, ::world &wor
ld);
> include\database\world.hpp:192:extern void remove_object(ENetEvent& event, signed uid);
> include\database\world.hpp:193:extern int  add_object(ENetEvent& event, ::slot slot, const ::pos &pos, ::world &world
);
  include\database\world.hpp:194:
> include\database\world.hpp:195:extern void add_drop(ENetEvent &event, ::slot im, ::pos pos, ::world &world);
  include\database\world.hpp:196:
  include\database\world.hpp:197:extern void send_tile_update(ENetEvent &event, gamePacket s, ::block &b, ::world &worl
d);
  include\database\world.hpp:198:
  include\database\world.hpp:199:/*
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
  include\gamePacket\item_activate_object.cpp:37:        on::SetBux(event);
  include\gamePacket\item_activate_object.cpp:38:    }
> include\gamePacket\item_activate_object.cpp:39:    remove_object(event, object->uid);
  include\gamePacket\item_activate_object.cpp:40:    const ::object remember_object = *object;
> include\gamePacket\item_activate_object.cpp:41:    world->objects.erase(object); // @note erase before add_object(),
which can move the list and break the iterator
  include\gamePacket\item_activate_object.cpp:42:
> include\gamePacket\item_activate_object.cpp:43:    if (left > 0) add_object(event, ::slot(remember_object.id, left),
remember_object.pos, *world); // @note the rest stays on the ground
  include\gamePacket\item_activate_object.cpp:44:}
  include\gamePacket\tile_change.cpp:146:                                for (short i : {100, 50, 10, 5, 1}/* gem type
*/)
  include\gamePacket\tile_change.cpp:147:                                    for (; gems >= i; gems -= i/* downgrade ty
pe */)
> include\gamePacket\tile_change.cpp:148:                                        add_drop(event, {112, i}, gamePacket.p
unch.by_32(), *world);
  include\gamePacket\tile_change.cpp:149:
  include\gamePacket\tile_change.cpp:150:                                break;
  include\gamePacket\tile_change.cpp:151:                            }
  include\gamePacket\tile_change.cpp:152:                            case 872:/*chicken*/ case 866:/*cow*/ case 1632:/*
coffee maker*/ case 3888:/*sheep*/
  include\gamePacket\tile_change.cpp:153:                            {
> include\gamePacket\tile_change.cpp:154:                                add_drop(event, ::slot(item.id+2, RandomRange(
1, 2)), gamePacket.punch.by_32(), *world);
  include\gamePacket\tile_change.cpp:155:                                break;
  include\gamePacket\tile_change.cpp:156:                            }
  include\gamePacket\tile_change.cpp:157:                            case 5116:/*tea set*/
  include\gamePacket\tile_change.cpp:158:                            {
> include\gamePacket\tile_change.cpp:159:                                add_drop(event, ::slot(item.id-2, RandomRange(
1, 2)), gamePacket.punch.by_32(), *world);
  include\gamePacket\tile_change.cpp:160:                                break;
  include\gamePacket\tile_change.cpp:161:                            }
  include\gamePacket\tile_change.cpp:162:                            case 2798:/*well*/
  include\gamePacket\tile_change.cpp:163:                            {
> include\gamePacket\tile_change.cpp:164:                                add_drop(event, ::slot(822/*water bucket*/, Ra
ndomRange(1, 2)), gamePacket.punch.by_32(), *world);
  include\gamePacket\tile_change.cpp:165:                                break;
  include\gamePacket\tile_change.cpp:166:                            }
  include\gamePacket\tile_change.cpp:167:                            case 928:/*science station*/ // @note source: http
s://growtopia.fandom.com/wiki/Science_Station
  include\gamePacket\tile_change.cpp:168:                            {
  include\gamePacket\tile_change.cpp:172:                                    (!RandomRange(0, 6))  ? chemcial = 924/*Y*
/ :
  include\gamePacket\tile_change.cpp:173:                                    (!RandomRange(0, 4))  ? chemcial = 916/*R*
/ : chemcial = 914/*G*/;
> include\gamePacket\tile_change.cpp:174:                                add_drop(event, {chemcial, 1}, gamePacket.punc
h.by_32(), *world);
  include\gamePacket\tile_change.cpp:175:                                break;
  include\gamePacket\tile_change.cpp:176:                            }
  include\gamePacket\tile_change.cpp:177:                        }
  include\gamePacket\tile_change.cpp:178:                        //block.tick = ticks();
  include\gamePacket\tile_change.cpp:190:                    {
  include\gamePacket\tile_change.cpp:191:                        block.hits[0] = 99;
> include\gamePacket\tile_change.cpp:192:                        add_drop(event, ::slot(item.id - 1, RandomRange(1, tre
e->fruit*3)), gamePacket.punch.by_32(), *world); // @note fruit (from tree)
  include\gamePacket\tile_change.cpp:193:                    }
  include\gamePacket\tile_change.cpp:194:                    break;
  include\gamePacket\tile_change.cpp:195:                }
  include\gamePacket\tile_change.cpp:196:                case type::WEATHER_MACHINE:
  include\gamePacket\tile_change.cpp:259:                    // @todo add all the remaining drops - https://growtopia.f
andom.com/wiki/Golden_Booty_Chest
  include\gamePacket\tile_change.cpp:260:
> include\gamePacket\tile_change.cpp:261:                add_drop(event, ::slot(reward, (reward == 3408 || reward == 34
04) ? 10 : 1), gamePacket.punch.by_32(), *world);
  include\gamePacket\tile_change.cpp:262:                if (reward == 1458)
  include\gamePacket\tile_change.cpp:263:                {
  include\gamePacket\tile_change.cpp:264:                    std::string message = std::format("msg|`4The Power of Love
! `2{} found a `#Golden Heart Crystal`2 in a `#{}`2!", pPeer->growid, item.raw_name);
  include\gamePacket\tile_change.cpp:265:                    peers(pPeer->recent_worlds.back(), PeerSearch::EVERYONE, [
message](ENetPeer *peer)
  include\gamePacket\tile_change.cpp:268:                    });
  include\gamePacket\tile_change.cpp:269:                }
> include\gamePacket\tile_change.cpp:270:                if (++pPeer->gbc_pity % 100 == 0) modify_item_inventory(event,
 ::slot{9350, 1});
  include\gamePacket\tile_change.cpp:271:            }
  include\gamePacket\tile_change.cpp:272:            else if (item.type == type::LOCK && !is_tile_lock(item.id))
  include\gamePacket\tile_change.cpp:273:            {
  include\gamePacket\tile_change.cpp:274:                pPeer->display_growid = make_peer_display_growid(pPeer->role,
pPeer->growid);
  include\gamePacket\tile_change.cpp:280:            if (item.cat == CAT_RETURN)
  include\gamePacket\tile_change.cpp:281:            {
> include\gamePacket\tile_change.cpp:282:                int uid = add_object(event, ::slot(item.id, 1), gamePacket.pos
, *world);
  include\gamePacket\tile_change.cpp:283:                item_activate_object(event, ::gamePacket{.id = uid, .punch = g
amePacket.punch});
  include\gamePacket\tile_change.cpp:284:            }
  include\gamePacket\tile_change.cpp:285:            else if (u_char(item.property) & 04) { } // @note "This item never
 drops any seeds."; should it drop a block?
  include\gamePacket\tile_change.cpp:286:            else // @note normal break (drop gem, seed, block & give XP)
  include\gamePacket\tile_change.cpp:304:                        for (short i : {10, 5, 1}/* gem type */)
  include\gamePacket\tile_change.cpp:305:                            for (; gems >= i; gems -= i/* downgrade type */)
> include\gamePacket\tile_change.cpp:306:                                add_drop(event, {112, i}, gamePacket.punch.by_
32(), *world);
  include\gamePacket\tile_change.cpp:307:                    }
> include\gamePacket\tile_change.cpp:308:                    if (!RandomRange(0, (rarity_to_gem > 1) ? 2 : 4)) add_drop
(event, ::slot(item.id + 1, 1), gamePacket.punch.by_32(), *world);
> include\gamePacket\tile_change.cpp:309:                    else if (!RandomRange(0, (rarity_to_gem > 1) ? 4 : 8)) add
_drop(event, ::slot(item.id, 1), gamePacket.punch.by_32(), *world);
  include\gamePacket\tile_change.cpp:310:                } /* ~gem drop */
  include\gamePacket\tile_change.cpp:311:
  include\gamePacket\tile_change.cpp:312:                pPeer->add_xp(event, std::trunc(1.0f + item.rarity / 5.0f));
  include\gamePacket\tile_change.cpp:313:            }
  include\gamePacket\tile_change.cpp:508:            send_tile_update(event, std::move(gamePacket), block, *world);
  include\gamePacket\tile_change.cpp:509:
> include\gamePacket\tile_change.cpp:510:            modify_item_inventory(event, ::slot(item.id, -1));
  include\gamePacket\tile_change.cpp:511:            pPeer->add_xp(event, 1);
  include\gamePacket\tile_change.cpp:512:            return;
  include\gamePacket\tile_change.cpp:513:        }
  include\gamePacket\tile_change.cpp:514:        else if (gamePacket.id == 32)
  include\gamePacket\tile_change.cpp:688:                if (update_tile)
  include\gamePacket\tile_change.cpp:689:                {
> include\gamePacket\tile_change.cpp:690:                    modify_item_inventory(event, ::slot(gamePacket.id, -1));
  include\gamePacket\tile_change.cpp:691:                    send_tile_update(event, std::move(gamePacket), block, *wor
ld);
  include\gamePacket\tile_change.cpp:692:                    return;
  include\gamePacket\tile_change.cpp:693:                }
  include\gamePacket\tile_change.cpp:694:            }


PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> # F. PORTAL AND DOOR PERSISTENCE
PS C:\GTPS\Gurotopia> Show-Range "include/action/dialog_return/gateway_edit.cpp" 1 200

===== include/action/dialog_return/gateway_edit.cpp =====
   1: #include "pch.hpp"
   2:
   3: #include "gateway_edit.hpp"
   4:
   5: void gateway_edit(ENetEvent& event, const ::hPipe &hPipe)
   6: {
   7:     ::peer *pPeer = static_cast<::peer*>(event.peer->data);
   8:
   9:     const short tilex = atoi(hPipe["tilex"].c_str());
  10:     const short tiley = atoi(hPipe["tiley"].c_str());
  11:
  12:     auto world = std::ranges::find(worlds, pPeer->recent_worlds.back(), &::world::name);
  13:     if (world == worlds.end()) return;
  14:
  15:     if (tilex < 0 || tilex >= 100 || tiley < 0 || cord(tilex, tiley) >= world->blocks.size()) return;
  16:     if (world->owner != 0 && world->owner != pPeer->user_id && std::ranges::find(world->access, pPeer->user_id) == world->access.end()) return; // @note same rule as building here
  17:
  18:     block &block = world->blocks[cord(tilex, tiley)];
  19:
  20:     if (hPipe["dialog_name"] == "sign_edit")
  21:     {
  22:         auto sign = std::ranges::find(world->signs, ::pos{tilex, tiley}, &::sign::pos);
  23:         if (sign != world->signs.end())
  24:         {
  25:             sign->label = hPipe["sign_text"];
  26:         }
  27:         else {
  28:             world->signs.emplace_back(::sign(hPipe["sign_text"], ::pos{tilex, tiley}));
  29:         }
  30:     }
  31:     else if (hPipe["dialog_name"] == "door_edit")
  32:     {
  33:         auto door = std::ranges::find(world->doors, ::pos{tilex, tiley}, &::door::pos);
  34:         if (door != world->doors.end())
  35:         {
  36:             door->label = hPipe["door_name"];
  37:             if (!hPipe["dialog_name"].empty())
  38:             {
  39:                 door->dest = hPipe["door_target"];
  40:                 door->id = hPipe["door_id"];
  41:             }
  42:         }
  43:         else {
  44:             world->doors.emplace_back(::door(
  45:                 hPipe["door_name"],
  46:                 hPipe["door_target"],
  47:                 hPipe["door_id"],
  48:                 { tilex, tiley }
  49:             ));
  50:         }
  51:     }
  52:     else if (hPipe["dialog_name"] == "gateway_edit")
  53:     {
  54:         block.state[2] &= ~(S_PUBLIC | S_LOCKED);
  55:         block.state[2] |= atoi(hPipe["checkbox_public"].c_str()) ? S_PUBLIC : S_LOCKED;
  56:     }
  57:
  58:     send_tile_update(event, {
  59:         .id = block.fg,
  60:         .punch = { tilex, tiley }
  61:     }, block, *world);
  62: }
PS C:\GTPS\Gurotopia> Show-Range "include/database/world.cpp" 46 85

===== include/database/world.cpp =====
  46: ::blob object::to_blob() const
  47: {
  48:     blob blob;
  49:     blob.i16(this->id);
  50:     blob.f32(this->pos.x);
  51:     blob.f32(this->pos.y);
  52:     blob.i16(this->count);
  53:     blob.i32(this->uid);
  54:
  55:     return blob;
  56: }
  57:
  58: ::blob door::to_blob() const
  59: {
  60:     blob blob;
  61:     blob.i16(this->label.length());
  62:     for (char c : this->label) blob.u8(c);
  63:     blob.u8('\0');
  64:
  65:     return blob;
  66: }
  67:
  68: ::blob sign::to_blob() const
  69: {
  70:     blob blob;
  71:     blob.i16(this->label.length());
  72:     for (char c : this->label) blob.u8(c);
  73:     blob.u32(this->idk);
  74:
  75:     return blob;
  76: }
  77:
  78: ::blob tree::to_blob(bool seconds) const
  79: {
  80:     blob blob;
  81:     blob.i32((seconds) ? ticks() - this->tick : this->tick);
  82:     blob.u8(this->fruit);
  83:
  84:     return blob;
  85: }
  86:
  87: ::blob world::serialize()
  88: {
  89:     blob blob;
  90:     blob.i16(0x00); // @todo my rgt world says: 19 00
  91:     blob.i32(0x00); // @todo my rgt world says: 40 00 00 00
  92:     blob.i16(this->name.length());
  93:     for (char c : this->name) blob.u8(c);
  94:
  95:     const int y = this->blocks.size() / 100;
  96:     const int x = this->blocks.size() / y;
  97:     blob.i32(x);
  98:     blob.i32(y);
  99:     blob.i16(this->blocks.size());
 100:
 101:     /*@todo*/
 102:     blob.i32(0x00);
 103:     blob.i16(0x00);
 104:     blob.u8(0x00);
 105:
 106:     for (u_short i = 0; const ::block &block : this->blocks)
 107:     {
 108:         blob.push_back(block.to_blob());
 109:
 110:         if (block.fg != 0 || block.fg!=2||block.fg!=4||block.fg!=8||block.fg!=14) // @note so we can save time
 111:         if (char type = get_type(id_to_item(block.fg)); type > '\x00')
 112:         {
 113:             blob.u8(type);
 114:
 115:             const ::pos block_pos{i % x, i / x};
 116:             if (type == '\x01'/*doors, portal*/)
 117:             {
 118:                 if (block.fg == 6/*Main Door*/) this->spawn = block_pos.by_32(false);
 119:
 120:                 auto door = std::ranges::find(this->doors, block_pos, &::door::pos);
 121:                 if (door != this->doors.end())
 122:                 {
 123:                     blob.push_back(door->to_blob());
 124:                 }
 125:             }
 126:             else if (type == '\x02'/*sign*/)
 127:             {
 128:                 auto sign = std::ranges::find(this->signs, block_pos, &::sign::pos);
 129:                 if (sign != this->signs.end())
 130:                 {
PS C:\GTPS\Gurotopia> Show-Range "include/database/world.cpp" 237 310

===== include/database/world.cpp =====
 237: void world::mysql_select_all()
 238: {
 239:     this->name = this->mysql_select<std::string>("name");
 240:     this->owner = this->mysql_select<int>("owner");
 241:     {
 242:         ::blob blob = this->mysql_select<::blob>("blocks");
 243:
 244:         this->blocks.resize(cord(0, 60));
 245:         const int x = this->blocks.size() / 60;
 246:         int pos{};
 247:         for (u_short i = 0; ::block &block : this->blocks)
 248:         {
 249:             blob.read_i16(block.fg, pos);
 250:             blob.read_i16(block.bg, pos);
 251:             blob.read_u8(block.state[0], pos);
 252:             blob.read_u8(block.state[1], pos);
 253:             blob.read_u8(block.state[2], pos);
 254:             blob.read_u8(block.state[3], pos);
 255:
 256:             if (block.fg != 0 || block.fg!=2||block.fg!=4||block.fg!=8||block.fg!=14) // @note so we can save time
 257:             if (char type = get_type(id_to_item(block.fg)); type > '\x00')
 258:             {
 259:                 const ::pos block_pos{i % x, i / x};
 260:                 if (type == '\x01'/*doors, portal*/)
 261:                 {
 262:                     ::door &door = this->doors.emplace_back("","","", block_pos);
 263:
 264:                     short len{};
 265:                     blob.read_i16(len, pos);
 266:                     door.label.resize(len);
 267:                     for (char &c : door.label) blob.read_u8((u_char&)c, pos);
 268:                     pos++;// @note \0
 269:                 }
 270:                 else if (type == '\x02'/*sign*/)
 271:                 {
 272:                     ::sign &sign = this->signs.emplace_back("", block_pos);
 273:
 274:                     short len{};
 275:                     blob.read_i16(len, pos);
 276:                     sign.label.resize(len);
 277:                     for (char &c : sign.label) blob.read_u8((u_char&)c, pos);
 278:                     blob.read_u32(sign.idk, pos);
 279:                 }
 280:                 else if (type == '\x04'/*seed*/)
 281:                 {
 282:                     ::tree &tree = this->trees.emplace_back(0, 0, block_pos);
 283:
 284:                     blob.read_u32(tree.tick, pos);
 285:                     blob.read_u8(tree.fruit, pos);
 286:                 }
 287:             }
 288:             ++i;
 289:         }
 290:     } // @note delete blob, i
 291:     {
 292:         ::blob blob = this->mysql_select<::blob>("objects"); // @note ::blob is cut to the real length, std::vector<u_char> stays at the full buffer size
 293:
 294:         int pos{};
 295:
 296:         blob.read_u32(this->last_object_uid, pos); // @todo real gt has this as 8 bits not just 4.
 297:         objects.resize(blob.size() >= sizeof(u_int) ? (blob.size() - sizeof(u_int)) / 16 : 0); // @note count from the saved data, not the last drop uid
 298:         for (::object &object : this->objects)
 299:         {
 300:             blob.read_u16(object.id, pos);
 301:             blob.read_f32(object.pos.x, pos);
 302:             blob.read_f32(object.pos.y, pos);
 303:             blob.read_u16(object.count, pos);
 304:             blob.read_u32(object.uid, pos);
 305:         }
 306:     } // @note delete blob, pos
 307: }
 308:
 309: world::world(const std::string &name) : name(name)/*DEFAULT*/
 310: {
 311:     if (this->exists(this->name))
 312:     {
 313:         this->mysql_select_all();
 314:     }
 315:     else
 316:     {
 317:         this->mysql_insert("name", this->name); // @note DEFAULT
 318:         generate_world(*this);
 319:     }
 320: }
 321: world::~world()
 322: {
 323:     this->mysql_update("owner", this->owner);
 324:     {
 325:         ::blob blob;
 326:
 327:         const int x = this->blocks.size() / 60;
 328:         for (u_short i = 0; const ::block &block : this->blocks)
 329:         {
 330:             blob.push_back(block.to_blob());
 331:
 332:             if (block.fg != 0) // @note so we can save time
 333:             if (u_char type = get_type(id_to_item(block.fg)); type > 0x00)
 334:             {
 335:                 const ::pos block_pos{i % x, i / x};
 336:                 if (type == '\x01'/*doors, portal*/)
 337:                 {
 338:                     auto door = std::ranges::find(this->doors, block_pos, &::door::pos);
 339:                     if (door != this->doors.end())
 340:                     {
 341:                         blob.push_back(door->to_blob());
 342:                     }
 343:                 }
 344:                 else if (type == '\x02'/*sign*/)
 345:                 {
 346:                     auto sign = std::ranges::find(this->signs, block_pos, &::sign::pos);
 347:                     if (sign != this->signs.end())
 348:                     {
 349:                         blob.push_back(sign->to_blob());
 350:                     }
 351:                 }
 352:                 else if (type == '\x04'/*seed*/)
 353:                 {
 354:                     auto tree = std::ranges::find(this->trees, block_pos, &::tree::pos);
 355:                     if (tree != this->trees.end())
 356:                     {
 357:                         blob.push_back(tree->to_blob());
 358:                     }
 359:                 }
 360:             }
 361:             ++i;
 362:         }
 363:         this->mysql_update("blocks", blob);
 364:     }
 365:     {
 366:         ::blob blob{};
 367:
 368:         blob.i32(this->last_object_uid); // @todo add the other 4 bits like real growtopia
 369:         for (::object &object : this->objects)
 370:         {
 371:             blob.push_back(object.to_blob());
 372:         }
 373:         this->mysql_update("objects", blob.data());
 374:     }
 375: }
 376:
 377: std::vector<world> worlds;
 378:
 379: void send_gameMessage(ENetPeer *peer, ::gameMessage gameMessage)
 380: {
 381:     send_data(*peer, compressMessage(gameMessage));
 382: }
 383:
 384: void send_data(ENetPeer &peer, const ::blob &blob)
 385: {
 386:     ENetPacket *packet = enet_packet_create(blob.data().data(), blob.size(), ENET_PACKET_FLAG_RELIABLE);
 387:     if (packet == nullptr) return;
 388:
 389:     if (enet_peer_send(&peer, 0, packet)) enet_packet_destroy(packet);
 390: }
 391:
 392: void send_gamePacket(ENetPeer &peer, ::gamePacket &gamePacket)
 393: {
 394:     ::peer *pPeer = static_cast<::peer*>(peer.data);
 395:
 396:     peers(pPeer->recent_worlds.back(), PeerSearch::WORLD, [&](ENetPeer *peer)
 397:     {
 398:         send_data(*peer, compress_state(gamePacket));
 399:     });
 400: }
 401:
 402: void tile_apply_damage(ENetEvent &event, ::gamePacket gamePacket, block &block, u_int value)
 403: {
 404:     ::peer *pPeer = static_cast<::peer*>(event.peer->data);
 405:
 406:     (block.fg == 0) ? ++block.hits[1] : ++block.hits[0];
 407:     gamePacket.type = (value << 24) | 0x000008; // @note 0x{}000008
 408:     gamePacket.id = 6; // @note idk exactly
 409:     gamePacket.netid = pPeer->netid;
 410:   send_gamePacket(*event.peer, gamePacket);
 411: }
 412:
 413: u_short modify_item_inventory(ENetEvent &event, ::slot slot)
 414: {
 415:     ::peer *pPeer = static_cast<::peer*>(event.peer->data);
 416:
 417:     ::gamePacket gamePacket{.id = slot.id};
 418:     if (slot.count < 0) gamePacket.type = (slot.count*-1 << 16) | 0x000d; // @noote 0x00{}000d
 419:     else                gamePacket.type = (slot.count    << 24) | 0x000d; // @noote 0x{}00000d
 420:     send_data(*event.peer, compress_state(gamePacket)); // @note only the player whose backpack changes
 421:
 422:     return pPeer->emplace(::slot(slot.id, slot.count));
 423: }
 424:
 425: void item_change_object(ENetEvent &event, ::gamePacket gamePacket)
 426: {
 427:     gamePacket.type = 0x0e; // @note PACKET_ITEM_CHANGE_OBJECT
 428:
 429:     send_gamePacket(*event.peer, gamePacket);
 430: }
 431:
 432: void merge_object(ENetEvent &event, ::slot slot, const ::pos &pos, ::world &world)
 433: {
 434:     auto object = std::ranges::find_if(world.objects, [&](const ::object &object) {
 435:         return object.id == slot.id && (object.pos.by_32(true) == pos.by_32(true));
 436:     });
 437:     /* @todo avoid surpassing 200 and call add_object() for the remaining amount */ // @note future self reference peer::emplace()...
 438:     object->count += slot.count;
 439:
 440:     item_change_object(event, ::gamePacket{
 441:         .netid = (int)0xfffffffd,
 442:         .uid   = (int)object->uid,
 443:         .count = static_cast<float>(object->count),
 444:         .id    = object->id,
 445:         .pos   = object->pos
 446:     });
 447: }
 448:
 449: void remove_object(ENetEvent& event, signed uid)
 450: {
 451:     ::peer *pPeer = static_cast<::peer*>(event.peer->data);
 452:
 453:     item_change_object(event, ::gamePacket{
 454:         .netid = pPeer->netid,
 455:         .uid   = (int)0xffffffff,
 456:         .id    = uid
 457:     });
 458: }
 459:
 460: int add_object(ENetEvent& event, ::slot slot, const ::pos& pos, ::world &world)
 461: {
 462:     /* @todo got a little messy */
 463:     auto object = std::ranges::find_if(world.objects, [&](const ::object &object) {
 464:         return object.id == slot.id && (object.pos.by_32(true) == pos.by_32(true));
 465:     });
 466:     if (object != world.objects.end() && object->count < 200/*@todo*/)
 467:     {
 468:         merge_object(event, slot, pos, world);
 469:         return object->uid;
 470:     }
 471:     ::object it = world.objects.emplace_back(::object(slot.id, slot.count, pos, ++world.last_object_uid)); // @note a iterator ahead of time
 472:
 473:     item_change_object(event, ::gamePacket{
 474:         .netid = (int)0xffffffff,
 475:         .uid   = (int)it.uid,
 476:         .count = static_cast<float>(slot.count),
 477:         .id    = it.id,
 478:         .pos   = pos
 479:     });
 480:     return it.uid;
 481: }
 482:
 483: void add_drop(ENetEvent &event, ::slot im, ::pos pos, ::world &world) // @todo
 484: {
 485:     add_object(event, im, ::pos{
 486:         pos.x + RandomRange(0, 16),
 487:         pos.y + RandomRange(0, 16)
 488:     }, world);
 489: }
 490:
 491: void send_tile_update(ENetEvent &event, ::gamePacket gamePacket, ::block &block, ::world &world)
 492: {
 493:     gamePacket.type = 05; // @note PACKET_SEND_TILE_UPDATE_DATA
 494:     gamePacket.state = (int)gamePacketState::EXTENDED;
 495:     ::blob blob = compress_state(gamePacket);
 496:
 497:     blob.push_back(block.to_blob());
 498:
 499:     const ::item &item = id_to_item(block.fg);
 500:     blob.u8(get_type(id_to_item(block.fg)));
 501:     switch (item.type)
 502:     {
 503:         case type::DOOR:
 504:         {
 505:             auto door = std::ranges::find(world.doors, gamePacket.punch, &::door::pos);
 506:             if (door != world.doors.end())
 507:             {
 508:                 blob.push_back(door->to_blob());
 509:             }
 510:             break;
 511:         }
 512:         case type::SIGN:
 513:         {
 514:             auto sign = std::ranges::find(world.signs, gamePacket.punch, &::sign::pos);
 515:             if (sign != world.signs.end())
 516:             {
 517:                 blob.push_back(sign->to_blob());
 518:             }
 519:             break;
 520:         }
 521:         case type::LOCK:
 522:         {
 523:             if (!is_tile_lock(block.fg)) world.is_public = (block.state[2] & S_PUBLIC); // @note check if world lock has S_PUBLIC flag, i will change this later
 524:             int access = std::ranges::count_if(world.access, std::identity{});
 525:
 526:             blob.u8(world.lock_state);
 527:             blob.i32(world.owner);
 528:             blob.i32(access);
 529:         }
 530:         case type::SEED:
 531:         {
 532:             auto tree = std::ranges::find(world.trees, gamePacket.punch, &::tree::pos);
 533:             if (tree != world.trees.end())
 534:             {
 535:                 blob.push_back(tree->to_blob(true));
 536:             }
 537:             break;
 538:         }
 539:     }
 540:     ::peer *pPeer = static_cast<::peer*>(event.peer->data);
 541:     peers(pPeer->recent_worlds.back(), PeerSearch::WORLD, [&blob](ENetPeer *peer)
 542:     {
 543:         send_data(*peer, blob);
 544:     });
 545: }

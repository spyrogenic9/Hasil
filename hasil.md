===== A. FULL PROTOCOL HANDLER =====
PS C:\GTPS\Gurotopia> Get-Content .\include\action\protocol.cpp |
>>     Select-Object -First 230
#include "pch.hpp"

#include "https/server_data.hpp"
#include "admin/admin.hpp"
#include "security/login_session.hpp"
#include "security/guest_identity.hpp"

#include <algorithm>
#include <chrono>
#include <deque>
#include <mutex>
#include <unordered_map>

#include <cctype>

#include "protocol.hpp"

namespace
{
    std::mutex guest_rate_mutex;
    std::unordered_map<enet_uint32, std::deque<std::chrono::steady_clock::time_point>> guest_rate;

    bool allow_guest_creation(const ENetPeer* peer)
    {
        if (peer == nullptr) return false;
        const auto now = std::chrono::steady_clock::now();
        std::lock_guard lock(guest_rate_mutex);
        const auto& ip = peer->address.host.v4;
        const enet_uint32 ip_key =
            (static_cast<enet_uint32>(ip[0]) << 24) |
            (static_cast<enet_uint32>(ip[1]) << 16) |
            (static_cast<enet_uint32>(ip[2]) << 8)  |
            static_cast<enet_uint32>(ip[3]);
        auto& attempts = guest_rate[ip_key];
        while (!attempts.empty() && now - attempts.front() >= std::chrono::minutes(1))
            attempts.pop_front();
        if (attempts.size() >= 5) return false;
        attempts.push_back(now);
        return true;
    }

    std::string trim_protocol_value(std::string value)
    {
        const auto edge = [](unsigned char c)
        {
            return c == '\r' || c == '\n' || c == '\0' || c == ' ' || c == '\t';
        };
        while (!value.empty() && edge(static_cast<unsigned char>(value.front()))) value.erase(value.begin());
        while (!value.empty() && edge(static_cast<unsigned char>(value.back()))) value.pop_back();
        return value;
    }

    std::string decoded_field(const std::string& decoded, const std::string& key)
    {
        const std::string marker = key + "=";
        std::size_t pos = decoded.find(marker);
        if (pos == std::string::npos) return {};
        pos += marker.size();
        const std::size_t end = decoded.find('&', pos);
        return trim_protocol_value(decoded.substr(pos, end == std::string::npos ? end : end - pos));
    }
}

void action::protocol(ENetEvent& event, const std::string& header)
{
    if (event.peer == nullptr || event.peer->data == nullptr) return;
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    std::string normalized = header;
    // receive.cpp already converts LF delimiters to '|'. Remove the CR half
    // of CRLF instead of converting it again (which would create empty fields
    // and shift every key/value pair by one position).
    std::erase(normalized, '\r');
    for (char& c : normalized)
        if (c == '\n') c = '|';
    const std::vector<std::string> fields = readch(normalized, '|');

    std::string ltoken{};
    std::string protocol_number{};
    bool has_ltoken = false;
    bool explicit_guest = false;
    for (std::size_t i = 0; i + 1 < fields.size(); i += 2)
    {
        const std::string key = trim_protocol_value(fields[i]);
        const std::string value = trim_protocol_value(fields[i + 1]);
        if (key == "ltoken")
        {
            has_ltoken = true;
            ltoken = value;
        }
        else if (key == "protocol") protocol_number = value;
        else if (key == "guest" || key == "guestMode") explicit_guest = (value == "1" || value == "true");
    }

    try
    {
        if (protocol_number.empty() || std::stoi(protocol_number) <= 0)
            throw std::runtime_error("invalid protocol");
    }
    catch (...)
    {
        send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
        return;
    }

    bool is_registration = false;
    bool loaded = false;
    bool guest_login = false;

    if (!ltoken.empty())
    {
        const std::string decoded = base64_decode(ltoken);
        if (decoded.empty())
        {
            print("[AUTH] protocol stage rejected malformed login token\n");
            send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
            return;
        }

        const std::string growid = decoded_field(decoded, "growId");
        const std::string password = decoded_field(decoded, "password");
        const std::string registration = decoded_field(decoded, "reg");
        const std::string guest = decoded_field(decoded, "guest");
        is_registration = (registration == "1");

        if (guest == "1" || guest == "true")
        {
            guest_login = true;
            if (!allow_guest_creation(event.peer))
            {
                print("[AUTH] guest creation rate limit reached\n");
                send_gameMessage(event.peer, {.message = "action|log\nmsg|`4Guest login rate limit reached. Try again shortly.``"});
                send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
                return;
            }
            const std::string client_token = decoded_field(decoded, "_token");
            const std::string fingerprint = guest_identity::fingerprint_from_client_token(client_token);
            loaded = pPeer->create_guest_account(fingerprint);
        }
        else if (growid.empty() || password.empty())
        {
            print("[AUTH] protocol stage rejected token without GrowID/password or guest flag\n");
            send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
            return;
        }
        else
        {
            loaded = is_registration
                ? pPeer->create_account(growid, password)
                : pPeer->load(growid, password);
        }
    }
    else if (!has_ltoken || ltoken.empty() || explicit_guest)
    {
        // Guest means a new server-generated account, not an anonymous UID.
        // A malformed, non-empty ltoken never silently downgrades into guest.
        guest_login = true;
        if (!allow_guest_creation(event.peer))
        {
            print("[AUTH] guest creation rate limit reached\n");
            send_gameMessage(event.peer, {.message = "action|log\nmsg|`4Guest login rate limit reached. Try again shortly.``"});
            send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
            return;
        }
        loaded = pPeer->create_guest_account();
    }

    if (!loaded)
    {
        print(std::format("[AUTH] protocol stage authentication failed mode={} token_present={} guest_flag={}\n",
            ltoken.empty() ? "guest-or-empty" : "growid", has_ltoken, explicit_guest));
        send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
        return;
    }

    if (admin::is_banned(pPeer->growid))
    {
        print(std::format("[AUTH] blocked banned account at protocol stage: {}\n", pPeer->growid));
        send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
        enet_peer_disconnect_later(event.peer, 0);
        return;
    }
    pPeer->muted = admin::is_muted(pPeer->growid);

    const std::uint32_t session_token = login_session::issue(pPeer->user_id);
    if (session_token == 0)
    {
        print(std::format("[AUTH] failed to issue session ticket for uid={}\n", pPeer->user_id));
        send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
        enet_peer_disconnect_later(event.peer, 0);
        return;
    }

    print(std::format("[AUTH] protocol stage accepted growid={} uid={} guest={} ticket=issued\n",
        pPeer->growid, pPeer->user_id, guest_login));

    send_varlist(event.peer, {
        "OnSendToServer",
        (signed)gServer_data.port,
        0,
        pPeer->user_id,
        std::format("{}|{}|0", gServer_data.server, session_token),
        1,
        pPeer->growid.c_str()
    });
}
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== B. SEND_VARLIST IMPLEMENTATION ====="

===== B. SEND_VARLIST IMPLEMENTATION =====
PS C:\GTPS\Gurotopia> Get-ChildItem . -Recurse -File -Include *.cpp,*.hpp,*.h |
>>     Where-Object {
>>         $_.FullName -notmatch '\\build\\|\\.git\\'
>>     } |
>>     Select-String -Pattern 'send_varlist\s*\(' -Context 8,18 |
>>     Format-List Path,LineNumber,Context


Path       : C:\GTPS\Gurotopia\include\action\dialog_return\popup.cpp
LineNumber : 25
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\dialog_return\popup.cpp
LineNumber : 50
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\dialog_return\popup.cpp
LineNumber : 79
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\dialog_return\popup.cpp
LineNumber : 90
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\dialog_return\socialportal.cpp
LineNumber : 11
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\buy.cpp
LineNumber : 69
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\buy.cpp
LineNumber : 82
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\buy.cpp
LineNumber : 136
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\drop.cpp
LineNumber : 15
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\drop.cpp
LineNumber : 23
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\enter_game.cpp
LineNumber : 25
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\enter_game.cpp
LineNumber : 33
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\enter_game.cpp
LineNumber : 34
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\enter_game.cpp
LineNumber : 38
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\enter_game.cpp
LineNumber : 47
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\enter_game.cpp
LineNumber : 55
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\friends.cpp
LineNumber : 9
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\info.cpp
LineNumber : 53
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\input.cpp
LineNumber : 67
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\inventoryfavuitrigger.cpp
LineNumber : 9
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\itemfavourite.cpp
LineNumber : 19
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\itemfavourite.cpp
LineNumber : 23
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\join_request.cpp
LineNumber : 38
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\join_request.cpp
LineNumber : 111
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\join_request.cpp
LineNumber : 131
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\join_request.cpp
LineNumber : 147
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\join_request.cpp
LineNumber : 155
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\join_request.cpp
LineNumber : 161
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\mod_trade.cpp
LineNumber : 18
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\protocol.cpp
LineNumber : 197
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\quit_to_exit.cpp
LineNumber : 24
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\respawn.cpp
LineNumber : 9
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\respawn.cpp
LineNumber : 10
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\respawn.cpp
LineNumber : 14
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\respawn.cpp
LineNumber : 16
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\respawn_spike.cpp
LineNumber : 11
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\respawn_spike.cpp
LineNumber : 13
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\store.cpp
LineNumber : 13
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\tankIDName.cpp
LineNumber : 222
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\tankIDName.cpp
LineNumber : 225
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\trash.cpp
LineNumber : 15
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\trash.cpp
LineNumber : 25
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\worldlock_storage_modify_amount.cpp
LineNumber : 46
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\worldlock_storage_modify_amount.cpp
LineNumber : 51
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\wrench.cpp
LineNumber : 24
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\action\wrench.cpp
LineNumber : 80
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\admin\admin.cpp
LineNumber : 270
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\admin\admin.cpp
LineNumber : 363
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\commands\find.cpp
LineNumber : 17
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\commands\me.cpp
LineNumber : 15
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\commands\warp.cpp
LineNumber : 14
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\commands\weather.cpp
LineNumber : 81
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\commands\who.cpp
LineNumber : 16
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\database\peer.cpp
LineNumber : 348
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\database\peer.cpp
LineNumber : 349
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\database\peer.cpp
LineNumber : 352
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\item_activate.cpp
LineNumber : 27
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\item_activate.cpp
LineNumber : 42
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\item_activate.cpp
LineNumber : 54
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\movement.cpp
LineNumber : 51
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_activate.cpp
LineNumber : 48
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_activate.cpp
LineNumber : 52
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_activate.cpp
LineNumber : 57
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 59
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 140
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 232
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 365
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 387
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 427
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 441
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 455
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 466
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 563
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 604
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 631
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 649
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 670
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 714
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 783
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp
LineNumber : 838
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\Action.cpp
LineNumber : 19
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\BillboardChange.cpp
LineNumber : 9
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\ConsoleMessage.cpp
LineNumber : 7
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\CountryState.cpp
LineNumber : 9
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\EmoticonDataChanged.cpp
LineNumber : 29
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\EventButtonDataSet.cpp
LineNumber : 7
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\NameChanged.cpp
LineNumber : 9
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\RequestGazette.cpp
LineNumber : 48
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\RequestWorldSelectMenu.cpp
LineNumber : 29
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\SetBux.cpp
LineNumber : 16
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\SetBux.cpp
LineNumber : 27
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\SetClothing.cpp
LineNumber : 9
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\Spawn.cpp
LineNumber : 7
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\TradeStatus.cpp
LineNumber : 14
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\onVariant\WorldLockStorageResponse.cpp
LineNumber : 20
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\proton\Variant.cpp
LineNumber : 115
Context    : Microsoft.PowerShell.Commands.MatchInfoContext

Path       : C:\GTPS\Gurotopia\include\proton\Variant.hpp
LineNumber : 196
Context    : Microsoft.PowerShell.Commands.MatchInfoContext



PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== C. VARIANT LIST STRUCTURE ====="

===== C. VARIANT LIST STRUCTURE =====
PS C:\GTPS\Gurotopia> Get-Content .\include\proton\Variant.hpp |
>>     Select-Object -Skip 130 -First 100
        void SetDefaults()
        {
                m_type = TYPE_UNUSED;
        }
        eType m_type;

        union
        {
                u_char m_var[C_VAR_SPACE_BYTES]; //large enough so we can use the space for all the datatypes we care about

                //don't actually use these, these unions help me look at vars when debugging easier
                float m_as_floats[4];
                u_int m_as_uint32s[4];
                int m_as_int32s[4];
        };
        std::string m_string;

};

//a VariantList holds a group of variants, we pass these when we don't know in advance how many variants we want to use

#define C_MAX_VARIANT_LIST_PARMS 8

/*
//example of memory serialization of a VariantList

VariantList v;
v.Get(0).Set(uint32(42));
v.Get(1).Set("Hey guys");

//save to mem
byte *pData = v.SerializeToMem(&size, NULL);

//load from mem
VariantList b;
b.SerializeFromMem(pData, size);

//display
LogMsg("%s, the answer to life is %d", b.Get(1).GetString().c_str(), b.Get(0).GetUINT32());

//clean up the mem we initted earlier
SAFE_DELETE_ARRAY(pData);
*/

class VariantList
{
        public:

                VariantList(){};

                Variant & Get(int parmNum) {return m_variant[parmNum];}
                VariantList(Variant v0) {m_variant[0] = v0;}
                VariantList(Variant v0, Variant v1) {m_variant[0] = v0; m_variant[1] = v1;}
                VariantList(Variant v0, Variant v1, Variant v2) {m_variant[0] = v0; m_variant[1] = v1; m_variant[2] = v2;}
                VariantList(Variant v0, Variant v1, Variant v2, Variant v3) {m_variant[0] = v0; m_variant[1] = v1; m_variant[2] = v2; m_variant[3] = v3;}
                VariantList(Variant v0, Variant v1, Variant v2, Variant v3, Variant v4) {m_variant[0] = v0; m_variant[1] = v1; m_variant[2] = v2; m_variant[3] = v3; m_variant[4] = v4;}
                VariantList(Variant v0, Variant v1, Variant v2, Variant v3, Variant v4, Variant v5) {m_variant[0] = v0; m_variant[1] = v1; m_variant[2] = v2; m_variant[3] = v3; m_variant[4] = v4;  m_variant[5] = v5;}
                VariantList(Variant v0, Variant v1, Variant v2, Variant v3, Variant v4, Variant v5, Variant v6) {m_variant[0] = v0; m_variant[1] = v1; m_variant[2] = v2; m_variant[3] = v3; m_variant[4] = v4;  m_variant[5] = v5; m_variant[6] = v6;}

                u_char * SerializeToMem(u_int *pSizeOut, u_char *pDest); //pass in NULL for dest and it will new[] the memory itself
                Variant m_variant[C_MAX_VARIANT_LIST_PARMS]; //non-dynamic for speed
};

int GetSizeOfData(Variant::eType type);

void send_varlist(ENetPeer *peer, VariantList vlist, int netid = -1, int delay = 0);

[PS C:\GTPS\Gurotopia> Write-Host "`n===== INPUT COMMAND DISPATCHER ====="

===== INPUT COMMAND DISPATCHER =====
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

        if (auto it = cmd_pool.find(command); it != cmd_pool.end())
            it->second(event, std::move(text));
        else
            send_gameMessage(event.peer, {.message = "action|log\nmsg|`4Unknown command.`` Enter `$/?`` for a list of valid commands."});
    }
    else
    {
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
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== ROLE DEFINITIONS ====="

===== ROLE DEFINITIONS =====
PS C:\GTPS\Gurotopia> Get-Content .\include\database\peer.hpp |
>>     Select-Object -Skip 55 -First 35
    bool isBuying{};
    int price{1};
    bool perItem{}; // @note true if world locks per item, false if items per world lock
};

enum role : u_char
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
{
    OWNER     = 0,
    DEVELOPER = 1,
    MODERATOR = 2,
    PLAYER    = 3
};

enum pstate : int
{
    S_GHOST       = 0x00000001,
    S_DOUBLE_JUMP = 0x00000002,
    S_DUCT_TAPE   = 0x00002000
};

class peer {
public:
    ~peer();

PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== ALL COMMAND IMPLEMENTATIONS ====="

===== ALL COMMAND IMPLEMENTATIONS =====
PS C:\GTPS\Gurotopia> Get-ChildItem .\include\commands -Filter *.cpp |
>>     ForEach-Object {
>>         Write-Host "`n--- $($_.Name) ---"
>>         Get-Content $_.FullName
>>     }

--- find.cpp ---
#include "pch.hpp"

#include "find.hpp"

void find(ENetEvent& event, const std::string_view text)
{
    send_varlist(event.peer, {
        "OnDialogRequest",
        "set_default_color|`o\n"
        "add_text_input|n|Search: ||26|\n"
        "add_searchable_item_list||sourceType:allItems;listType:iconWithCustomLabel;resultLimit:30|n|\n"
        "add_quick_exit|\n"
        "end_dialog|find_item|||"
    });
}

--- ghost.cpp ---
#include "pch.hpp"

#include "onVariant/SetClothing.hpp"

#include "ghost.hpp"

void ghost(ENetEvent& event, const std::string_view text)
{
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    pPeer->state ^= S_GHOST;

    on::SetClothing(event.peer);
}

--- me.cpp ---
#include "pch.hpp"

#include "onVariant/ConsoleMessage.hpp"

#include "me.hpp"

void me(ENetEvent& event, const std::string_view text)
{

    const std::string message{ text.substr(sizeof("/me ")-1) };
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    peers(pPeer->recent_worlds.back(), PeerSearch::WORLD, [&event, &pPeer, message](ENetPeer *peer)
    {
        send_varlist(peer, {
            "OnTalkBubble",
            pPeer->netid,
            std::format(
                "player_chat= `6<{} `#{}```6>``",
                pPeer->display_growid, message).c_str(),
            0u
        });
        on::ConsoleMessage(peer,
            std::format(
                "CP:0_PL:0_OID:__CT:[W]_ `6<{} `#{}```6>``",
                pPeer->display_growid, message
            )
        );
    });
}

--- msg.cpp ---
#include "pch.hpp"

#include "msg.hpp"

void msg(ENetEvent& event, const std::string_view text)
{
    std::vector<std::string> spaces = readch(text.data(), ' ');
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    std::string growid = (spaces.size() > 1) ? spaces[1] : "";
    std::string msg;
    for (std::size_t i = 2/*@note skip growid*/; i < spaces.size(); ++i)
    {
        msg += spaces[i];
        if (i < spaces.size() - 1) msg += " ";
    }
    send_gameMessage(event.peer, {.message = std::format("action|log\nmsg|CT:[MSG]_ `6/msg {} {}``", growid, msg)});

    if (growid.empty() || msg.empty())
    {
        send_gameMessage(event.peer, {.message = "action|log\nmsg|Usage: /msg <`$full or first part of a name``> <`$your message``> - This will send a private message to someone anywhere in the universe.  If you don't include a message, you can just see if he/she is online or not."});
    }
    else {
        bool online = false;
        peers("", PeerSearch::EVERYONE, [&event, &pPeer, &online, growid, msg](ENetPeer *peer)
        {
            ::peer *pOthers = static_cast<::peer*>(peer->data);
            if (growid == pPeer->growid) // @todo add ignore
            {
                send_gameMessage(event.peer, {.message = "action|log\n`6>> `4SYSTEM``: Sorry! This player has ignored private messages from non-friends. Become friends to chat!"});
                online = true;
            }
            else if (pOthers->growid == growid)
            {
                send_gameMessage(event.peer, {.message = std::format("action|log\nmsg|CT:[MSG]_`6>> (Sent to `${}`)``", growid, msg)});
                online = true;
            }
            if (online) return;
        });
        if (!online)
        {
            std::string hint = (growid.length() < 5) ? " (you need to enter at least 5 letters if you meant a longer name!)" : "";
            send_gameMessage(event.peer, {.message = std::format("action|log\nmsg|`6>> `{}` is not online right now{}.``", growid, hint)});
        }
    }
}

--- news.cpp ---
#include "pch.hpp"

#include "onVariant/RequestGazette.hpp"

#include "news.hpp"

void news(ENetEvent& event, const std::string_view text)
{
    on::RequestGazette(event);
}

--- punch.cpp ---
#include "pch.hpp"

#include "onVariant/SetClothing.hpp"

#include "punch.hpp"

u_char get_punch_id(u_int item_id)
{
    switch (item_id)
    {
        case 138: case 2976: return 1; // @note https://growtopia.fandom.com/wiki/Mods/Eye_Beam
        case 366: return 2;
        case 472: return 3;
        case 594: return 4;
        case 768: return 5;
        case 900: return 6;

        case 930: return 8; // @todo or 12

        case 1204: return 10;
        case 1738: return 11;
        case 1484: return 12;

        case 3066: case 5206: case 7504: case 10288: return 17; // @note https://growtopia.fandom.com/wiki/Mods/Fire_Hose
        case 2636: case 2908: case 3070: case 3108: case 3466: case 2952: return 29; // @note https://growtopia.fandom.com/wiki/Mods/Slasher

        default: return 0;
    }
}

void punch(ENetEvent& event, const std::string_view text)
{
    const std::string id{ text.substr(sizeof("/punch ")-1) };
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    pPeer->punch_effect = (u_char)atoi(id.c_str());
    on::SetClothing(event.peer);
}

--- sb.cpp ---
#include "pch.hpp"

#include "onVariant/ConsoleMessage.hpp"

#include "sb.hpp"

void sb(ENetEvent& event, const std::string_view text)
{
    std::vector<std::string> spaces = readch(text.data(), ' ');
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    std::string message = (spaces.size() > 1) ? spaces[1] : "";
    u_int cost = host->connectedPeers * 30;

    if (message.empty())
    {
        send_gameMessage(event.peer, {.message = std::format(
            "action|log\nmsg|`5msg|>> This lets you send a message to {}`` random users online and make an annoying beep noise.  Costs `${} Gems`` to use. Example:`` `w/sb Hey guys, come to my world!",
            host->connectedPeers, cost)
        });
    }
    else {
        std::string display = pPeer->recent_worlds.back();
        peers("", PeerSearch::EVERYONE, [&pPeer, message, display](ENetPeer *peer)
        {
            on::ConsoleMessage(peer,
                std::format(
                    "CP:0_PL:0_OID:_CT:[SB]_ `5** from ({}```5) in [```${}```5] ** : ```${}``",
                    pPeer->display_growid, display, message
                )
            );
            send_gameMessage(peer, {.message = "action|play_sfx\nfile|audio/beep.wav\ndelayMS|0"});
        });
    }
}

--- skin.cpp ---
#include "pch.hpp"

#include "onVariant/SetClothing.hpp"

#include "skin.hpp"

void skin(ENetEvent& event, const std::string_view text)
{
    const std::string id{ text.substr(sizeof("/skin ")-1) };
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    try
    {
        pPeer->skin_color = (u_int)stoul(id);
        on::SetClothing(event.peer);
    }
    catch (const std::logic_error &le) {} // @note std::invalid_argument std::out_of_range
}

--- time.cpp ---
#include "pch.hpp"

#include "automate/holiday.hpp"
#include "onVariant/ConsoleMessage.hpp"

#include "time.hpp"

void command::time(ENetEvent& event, const std::string_view text)
{
    /* @todo cleanup this... */
    std::tm time = localtime();
    std::vector<std::string> month = { "January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December" };

    on::ConsoleMessage(event.peer,
        std::format("`2Growtopia Time (EDT/UTC-5): {} {}{}, {:02d}:{:02d}.", /* @todo remove hardcoded UTC zone */
            month[time.tm_mon], time.tm_mday,
            (time.tm_mday >= 11 && time.tm_mday <= 13) ? "th" :
            (time.tm_mday % 10 == 1) ? "st" :
            (time.tm_mday % 10 == 2) ? "nd" :
            (time.tm_mday % 10 == 3) ? "rd" : "th", time.tm_hour, time.tm_min
        )
    );
}

--- warp.cpp ---
#include "pch.hpp"

#include "action/join_request.hpp"
#include "action/quit_to_exit.hpp"

#include "warp.hpp"

void warp(ENetEvent& event, const std::string_view text)
{
    std::string world_name{ text.substr(sizeof("/warp ")-1) };
    for (char &c : world_name) c = std::toupper(c); // @note start -> START

    send_gameMessage(event.peer, {.message = std::format("action|log\nmsg| `6/warp {}``", world_name)});
    send_varlist(event.peer, { "OnSetFreezeState", 1 });
    send_gameMessage(event.peer, {.message = std::format("action|log\nmsg|Magically warping to world `5{}``...", world_name)});

    action::quit_to_exit(event, "", true);
    action::join_request(event, "", world_name);
}

--- weather.cpp ---
#include "pch.hpp"

#include "weather.hpp"

int get_weather_id(u_int item_id)
{
    switch (item_id)
    {
        case 830: return 1; // @note beach (blast)
        case 934: return 2; // @note night
        case 946: return 3; // @note arid

        case 984: return 5; // @note rainy city
        case 1060: return 6; // @note harvest moon (blast)
        case 1136: return 7; // @note mars (blast)
        case 1210: return 8; // @note spooky

        case 1490: return 10; // @note nothingness
        case 1364: return 11; // @note snowy

        case 1532: return 14; // @note undersea (blast)
        case 1750: return 15; // @note warp speed

        case 2046: return 17; // @note comet
        case 2284: return 18; // @note party
        case 2744: return 19; // @note pineapples
        case 3252: return 20; // @note snowy night
        case 3446: return 21; // @note spring
        case 3534: return 22; // @note howling sky

        case 3694: return 23; // @note heatwave (24-28)

        case 3832: return 29; // @note stuff
        case 4242: return 30; // @note pagoda
        case 4486: return 31; // @note apocalypse
        case 4774: return 32; // @note jungle (blast)
        case 4892: return 33; // @note balloon warz
        case 5000: return 34; // @note background
        case 5112: return 35; // @note autumn
        case 5654: return 36; // @note valentine's
        case 5716: return 37; // @note St. paddy's

        case 6854: return 42; // @note digital rain
        case 7380: return 43; // @note monochrome (blast)
        case 7644: return 44; // @note frozen cliffs
        case 8556: return 45; // @note surg world (blast)
        case 8738: return 46; // @note bountiful (blast)
        case 8836: return 47; // @note stargazing
        case 8896: return 48; // @note meteor shower

        case 10286: return 51; // @note celebrity hills
        case 11880: return 59; // @note plaza
        case 12054: return 60; // @note nebula
        case 12056: return 61; // @note protostar landing
        case 12408: return 62; // @note dark mountains

        case 12844: return 64; // @note Mt. growmore
        case 13004: return 65; // @note crack in reality
        case 13070: return 66; // @note å¹´å…½ (niÃ¡n) mountains

        case 13640: return 69; // @note realm of spirits
        case 13690: return 70; // @note black hole
        case 14032: return 71; // @note raining gems
        case 14094: return 72; // @note holiday heaven

        case 14598: return 76; // @note atlantis
        case 14802: return 77; // @note pinuski's petal purrfect haven
        case 14896: return 78; // @note candyland blast
        case 15150: return 79; // @note dragon's keep
        case 15240: return 80; // @note emerald city

        // @todo add newer weathers
    }
    return 0; // @note sunny
}

void weather(ENetEvent& event, const std::string_view text)
{
    const std::string id{ text.substr(sizeof("/weather ")-1) };

    send_varlist(event.peer, {
        "OnSetCurrentWeather",
        atoi(id.c_str())
    });
}

--- who.cpp ---
#include "pch.hpp"

#include "who.hpp"

void who(ENetEvent& event, const std::string_view text)
{
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    std::vector<std::string> names;
    peers(pPeer->recent_worlds.back(), PeerSearch::WORLD, [&pPeer, event, &names](ENetPeer *peer)
    {
        ::peer *pOthers = static_cast<::peer*>(peer->data);

        if (pOthers->user_id != pPeer->user_id)
        {
            send_varlist(event.peer, { "OnTalkBubble", pOthers->netid, pOthers->display_growid.c_str(), 1u });
        }
        names.emplace_back(pOthers->display_growid);
    });
    send_gameMessage(event.peer, {.message = std::format(
        "action|log\nmsg|`wWho's in `${}``:`` {}``",
        pPeer->recent_worlds.back(), join(names, ", ")
    )});

}

--- __command.cpp ---
#include "pch.hpp"

#include "onVariant/Action.hpp"

#include "msg.hpp"
#include "sb.hpp"
#include "time.hpp"
#include "who.hpp"
#include "me.hpp"
#include "find.hpp"
#include "warp.hpp"
#include "punch.hpp"
#include "skin.hpp"
#include "news.hpp"
#include "weather.hpp"
#include "ghost.hpp"

#include "__command.hpp"

/* if you plan to use this outside of this file, please include in __command.hpp (^-^) - and just make it a void. */
void help_return(ENetEvent& event, const std::string_view text)
{
    send_gameMessage(event.peer, {.message = "action|log\nmsg|>> Commands: /msg /sb /time /who /me /find /warp /punch /skin /news /weather /ghost /ageworld /wave /dance /love /sleep /facepalm /fp /smh /yes /no /omg /idk /shrug /furious /rolleyes /foldarms /stubborn /fold /dab /sassy /dance2 /march /grumpy /shy"});
}

const std::unordered_map<std::string_view, void(*)(ENetEvent&, std::string_view)> cmd_pool
{
    {"/help", help_return},
    {"/?", help_return},
    {"/msg", msg},
    {"/sb", sb},
    {"/time", command::time}, // @note namespace is to prevent mismatching C time
    {"/who", who},
    {"/me", me},
    {"/find", find},
    {"/warp", warp},
    {"/punch", punch},
    {"/skin", skin},
    {"/news", news},
    {"/weather", weather},
    {"/ghost", ghost},
    {"/wave", on::Action}, {"/dance", on::Action}, {"/love", on::Action}, {"/sleep", on::Action}, {"/facepalm", on::Action}, {"/fp", on::Action},
    {"/smh", on::Action}, {"/yes", on::Action}, {"/no", on::Action}, {"/omg", on::Action}, {"/idk", on::Action}, {"/shrug", on::Action},
    {"/furious", on::Action}, {"/rolleyes", on::Action}, {"/foldarms", on::Action}, {"/fa", on::Action}, {"/stubborn", on::Action}, {"/fold", on::Action},
    {"/dab", on::Action}, {"/sassy", on::Action}, {"/dance2", on::Action}, {"/march", on::Action}, {"/grumpy", on::Action}, {"/shy", on::Action}
};
](https://github.com/spyrogenic9/Hasil/blob/main/hasil.md?plain=1)

PS C:\GTPS\login-gurotopia> Select-String -Path .\index.ts `
>> -Pattern 'protocol stage accepted|ticket|checktoken|ltoken|uid' `
>> -Context 10,18

  index.ts:200:        if (confirmPassword && password !== confirmPassword) {
  index.ts:201:          const errorMessage = 'Passwords do not match.';
  index.ts:202:          const errorHtml = `<div class="text-danger text-danger-wrapper"><ul><li>${errorMessage}</li></
ul></div>`;
  index.ts:203:          let htmlContent = templateContent.replace('{{ data }}', Buffer.from(clientData).toString('base
64'));
  index.ts:204:          htmlContent = htmlContent.replace('<div class="row div-content-center">', `${errorHtml}<div cl
ass="row div-content-center">`);
  index.ts:205:          res.setHeader('Content-Type', 'text/html');
  index.ts:206:          res.send(htmlContent);
  index.ts:207:          return;
  index.ts:208:        }
  index.ts:209:
> index.ts:210:        const existing = await db`SELECT uid FROM peer WHERE growid = ${growId} LIMIT 1`;
  index.ts:211:        if (existing.length > 0) {
  index.ts:212:          const errorMessage = `GrowID "${growId}" is already taken. Please choose another name.`;
  index.ts:213:          const errorHtml = `<div class="text-danger text-danger-wrapper"><ul><li>${errorMessage}</li></
ul></div>`;
  index.ts:214:          let htmlContent = templateContent.replace('{{ data }}', Buffer.from(clientData).toString('base
64'));
  index.ts:215:          htmlContent = htmlContent.replace('<div class="row div-content-center">', `${errorHtml}<div cl
ass="row div-content-center">`);
  index.ts:216:          res.setHeader('Content-Type', 'text/html');
  index.ts:217:          res.send(htmlContent);
  index.ts:218:          return;
  index.ts:219:        }
  index.ts:220:
  index.ts:221:        resetAttempts(clientIp);
  index.ts:222:
  index.ts:223:        const token = Buffer.from(
  index.ts:224:          `_token=${_token}&growId=${growId}&password=${password}&reg=1`,
  index.ts:225:        ).toString('base64');
  index.ts:226:
  index.ts:227:        res.send(
  index.ts:228:          JSON.stringify({
  index.ts:300:      console.log(`[ERROR]: ${error}`);
  index.ts:301:      res.status(500).json({
  index.ts:302:        status: 'error',
  index.ts:303:        message: 'Internal Server Error',
  index.ts:304:      });
  index.ts:305:    }
  index.ts:306:  },
  index.ts:307:);
  index.ts:308:
  index.ts:309:/**
> index.ts:310: * @note first checktoken endpoint - redirects to validate endpoint
  index.ts:311: * @param req - express request with refreshToken and clientData
  index.ts:312: * @param res - express response with updated token
  index.ts:313: */
> index.ts:314:app.all('/player/growid/checktoken', async (_req: Request, res: Response) => {
> index.ts:315:  return res.redirect(307, '/player/growid/validate/checktoken');
  index.ts:316:});
  index.ts:317:
  index.ts:318:/**
> index.ts:319: * @note second checktoken endpoint - validates token and returns updated token
  index.ts:320: * @param req - express request with refreshToken and clientData
  index.ts:321: * @param res - express response with updated token
  index.ts:322: */
  index.ts:323:app.all(
> index.ts:324:  '/player/growid/validate/checktoken',
  index.ts:325:  async (req: Request, res: Response) => {
  index.ts:326:    try {
  index.ts:327:      let refreshToken: string | undefined;
  index.ts:328:      let clientData: string | undefined;
  index.ts:329:      let source = 'empty';
  index.ts:330:      const contentType = req.headers['content-type'] || '';
  index.ts:331:
  index.ts:332:      if (typeof req.body === 'object' && req.body !== null) {
  index.ts:333:        const formData = req.body as Record<string, string>;
  index.ts:334:
  index.ts:335:        if ('refreshToken' in formData || 'clientData' in formData) {
  index.ts:336:          refreshToken = formData.refreshToken;
  index.ts:337:          clientData = formData.clientData;
  index.ts:338:          source = contentType.includes('application/json')
  index.ts:339:            ? 'json/object'
  index.ts:340:            : 'form-urlencoded';
  index.ts:341:        } else if (Object.keys(formData).length === 1) {
  index.ts:342:          const rawPayload = Object.keys(formData)[0];
  index.ts:372:        if (rawBody) {
  index.ts:373:          const params = new URLSearchParams(rawBody);
  index.ts:374:          refreshToken = params.get('refreshToken') || refreshToken;
  index.ts:375:          clientData = params.get('clientData') || clientData;
  index.ts:376:          if (refreshToken || clientData) {
  index.ts:377:            source = 'raw-stream';
  index.ts:378:          }
  index.ts:379:        }
  index.ts:380:      }
  index.ts:381:
> index.ts:382:      console.log(`[CHECKTOKEN] Parsed as ${source}`);
  index.ts:383:
  index.ts:384:      if (!refreshToken || !clientData) {
  index.ts:385:        console.log(`[ERROR]: Missing refreshToken or clientData`);
  index.ts:386:        res.status(200).json({
  index.ts:387:          status: 'error',
  index.ts:388:          message: 'Missing refreshToken or clientData',
  index.ts:389:        });
  index.ts:390:        return;
  index.ts:391:      }
  index.ts:392:
  index.ts:393:      let decodedRefreshToken = Buffer.from(refreshToken, 'base64').toString(
  index.ts:394:        'utf-8',
  index.ts:395:      );
  index.ts:396:
  index.ts:397:      // @note sync credentials check with db
  index.ts:398:      const tokenParams = new URLSearchParams(decodedRefreshToken);
  index.ts:399:      const tokenGrowId = tokenParams.get('growId');
  index.ts:400:      const tokenPassword = tokenParams.get('password');
  index.ts:401:      const isReg = tokenParams.get('reg') === '1';
> index.ts:402:      console.log(`[CHECKTOKEN] parsed growId=${Boolean(tokenGrowId)} password=${Boolean(tokenPassword)}
 registration=${isReg}`);
  index.ts:403:
  index.ts:404:      if (tokenGrowId) {
  index.ts:405:        const rows = await db`SELECT password FROM peer WHERE growid = ${tokenGrowId} LIMIT 1`;
> index.ts:406:        console.log(`[CHECKTOKEN] accountFound=${rows.length > 0} passwordMatches=${rows.length > 0 && r
ows[0].password === tokenPassword}`);
  index.ts:407:        if (isReg) {
  index.ts:408:          if (rows.length > 0) {
  index.ts:409:            res.status(200).json({
  index.ts:410:              status: 'error',
  index.ts:411:              message: 'GrowID is already taken',
  index.ts:412:            });
  index.ts:413:            return;
  index.ts:414:          }
  index.ts:415:        } else if (tokenPassword) {
  index.ts:416:          if (rows.length === 0 || rows[0].password !== tokenPassword) {
  index.ts:417:            res.status(200).json({
  index.ts:418:              status: 'error',
  index.ts:419:              message: 'Invalid credentials in token',
  index.ts:420:            });
  index.ts:421:            return;
  index.ts:422:          }
  index.ts:423:        }
  index.ts:424:      }


PS C:\GTPS\login-gurotopia> cd C:\GTPS\Gurotopia
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Get-ChildItem .\include -Recurse -File -Include *.cpp,*.hpp,*.h |
>> Select-String `
>> -Pattern 'rejected game login|uid_field|ticket_field|ticket_status' `
>> -Context 15,25

  include\action\tankIDName.cpp:107:    // requestedName is also routed here by legacy dispatch. It is not a
  include\action\tankIDName.cpp:108:    // complete login packet and must not cause a disconnect by itself.
  include\action\tankIDName.cpp:109:    if (protocol.empty())
  include\action\tankIDName.cpp:110:    {
  include\action\tankIDName.cpp:111:        print("[AUTH] ignored non-auth name request (protocol field absent)\n");
  include\action\tankIDName.cpp:112:        return;
  include\action\tankIDName.cpp:113:    }
  include\action\tankIDName.cpp:114:    try
  include\action\tankIDName.cpp:115:    {
  include\action\tankIDName.cpp:116:        if (std::stoi(protocol) <= 0) return;
  include\action\tankIDName.cpp:117:    }
  include\action\tankIDName.cpp:118:    catch (...) { return; }
  include\action\tankIDName.cpp:119:
  include\action\tankIDName.cpp:120:    bool loaded = false;
  include\action\tankIDName.cpp:121:    bool ticket_accepted = false;
> include\action\tankIDName.cpp:122:    std::string ticket_status = "not-present";
  include\action\tankIDName.cpp:123:
  include\action\tankIDName.cpp:124:    if (has_user_id && user_id_valid && has_uuid_token && uuid_token_valid)
  include\action\tankIDName.cpp:125:    {
  include\action\tankIDName.cpp:126:        const auto result = login_session::consume_detailed(uuid_token, requested_u
id);
  include\action\tankIDName.cpp:127:        switch (result)
  include\action\tankIDName.cpp:128:        {
  include\action\tankIDName.cpp:129:            case login_session::consume_result::accepted:
  include\action\tankIDName.cpp:130:                ticket_accepted = true;
> include\action\tankIDName.cpp:131:                ticket_status = "accepted";
  include\action\tankIDName.cpp:132:                loaded = pPeer->load_by_uid(requested_uid);
  include\action\tankIDName.cpp:133:                break;
> include\action\tankIDName.cpp:134:            case login_session::consume_result::not_found: ticket_status = "not-fou
nd"; break;
> include\action\tankIDName.cpp:135:            case login_session::consume_result::uid_mismatch: ticket_status = "uid-
mismatch"; break;
> include\action\tankIDName.cpp:136:            case login_session::consume_result::expired: ticket_status = "expired";
 break;
  include\action\tankIDName.cpp:137:        }
  include\action\tankIDName.cpp:138:    }
  include\action\tankIDName.cpp:139:    else if (has_uuid_token)
  include\action\tankIDName.cpp:140:    {
> include\action\tankIDName.cpp:141:        ticket_status = "malformed";
  include\action\tankIDName.cpp:142:    }
  include\action\tankIDName.cpp:143:
  include\action\tankIDName.cpp:144:    if (!loaded && growid_field && password_field)
  include\action\tankIDName.cpp:145:    {
  include\action\tankIDName.cpp:146:        // Never trust the supplied UID: MariaDB must authenticate the account
  include\action\tankIDName.cpp:147:        // and resolve to precisely the UID sent by the client.
  include\action\tankIDName.cpp:148:        loaded = pPeer->load(requested_growid, requested_password);
  include\action\tankIDName.cpp:149:        if (loaded && has_user_id && (!user_id_valid || pPeer->user_id != requested
_uid))
  include\action\tankIDName.cpp:150:            loaded = false;
  include\action\tankIDName.cpp:151:    }
  include\action\tankIDName.cpp:152:
  include\action\tankIDName.cpp:153:    if (!loaded)
  include\action\tankIDName.cpp:154:    {
  include\action\tankIDName.cpp:155:        print(std::format(
> include\action\tankIDName.cpp:156:            "[AUTH] rejected game login; uid_field={} uid_valid={} ticket_field={}
ticket_numeric={} ticket_len={} ticket_status={} growid_field={} password_field={} protocol={}\n",
  include\action\tankIDName.cpp:157:            has_user_id, user_id_valid, has_uuid_token, uuid_token_valid,
> include\action\tankIDName.cpp:158:            uuid_text.size(), ticket_status, growid_field, password_field, protocol
));
  include\action\tankIDName.cpp:159:        send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
  include\action\tankIDName.cpp:160:        enet_peer_disconnect_later(event.peer, 0);
  include\action\tankIDName.cpp:161:        return;
  include\action\tankIDName.cpp:162:    }
  include\action\tankIDName.cpp:163:
> include\action\tankIDName.cpp:164:    print(std::format("[AUTH] accepted growid={} uid={} guest={} method={} ticket_s
tatus={}\n",
  include\action\tankIDName.cpp:165:        pPeer->growid, pPeer->user_id, pPeer->is_guest,
> include\action\tankIDName.cpp:166:        ticket_accepted ? "ticket" : "credential-fallback", ticket_status));
  include\action\tankIDName.cpp:167:
  include\action\tankIDName.cpp:168:    if (admin::is_banned(pPeer->growid))
  include\action\tankIDName.cpp:169:    {
  include\action\tankIDName.cpp:170:        print(std::format("[AUTH] blocked banned account at game stage: {}\n", pPee
r->growid));
  include\action\tankIDName.cpp:171:        send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
  include\action\tankIDName.cpp:172:        enet_peer_disconnect_later(event.peer, 0);
  include\action\tankIDName.cpp:173:        return;
  include\action\tankIDName.cpp:174:    }
  include\action\tankIDName.cpp:175:    pPeer->muted = admin::is_muted(pPeer->growid);
  include\action\tankIDName.cpp:176:
  include\action\tankIDName.cpp:177:    send_varlist(event.peer, { "OnOverrideGDPRFromServer", 18, 1, 0, 1 });
  include\action\tankIDName.cpp:178:
  include\action\tankIDName.cpp:179:    /* v5.61 */
  include\action\tankIDName.cpp:180:    send_varlist(event.peer, {
  include\action\tankIDName.cpp:181:        "OnSuperMainStartAcceptLogonHrdxs47254722215a",
  include\action\tankIDName.cpp:182:        1423368844u, // @note items.dat
  include\action\tankIDName.cpp:183:        "ubistatic-a.akamaihd.net",
  include\action\tankIDName.cpp:184:        "0098/01020126/cache/",
  include\action\tankIDName.cpp:185:        "cc.cz.madkite.freedom org.aqua.gg idv.aqua.bulldog com.cih.gamecih2 com.ci
h.gamecih com.cih.game_cih cn.maocai.gamekiller com.gmd.speedtime org.dax.attack com.x0.strai.frep com.x0.strai.free or
g.cheatengine.cegui org.sbtools.gamehack com.skgames.traffikrider org.sbtoods.gamehaca com.skype.ralder org.cheatengine
.cegui.xx.multi1458919170111 com.prohiro.macro me.autotouch.autotouch com.cygery.repetitouch.free com.cygery.repetitouc
h.pro com.proziro.zacro com.slash.gamebuster",
  include\action\tankIDName.cpp:186:        std::format(
  include\action\tankIDName.cpp:187:            "proto={}|choosemusic=audio/mp3/about_theme.mp3|active_holiday={}|wing_
week_day=0|ubi_week_day=0|server_tick=0|game_theme={}|clash_active=0|drop_lavacheck_faster=1|isPayingUser=1|usingStoreN
avigation=1|enableInventoryTab=1|bigBackpack=1|seed_diary_hash=3856714732",
  include\action\tankIDName.cpp:188:            protocol, (u_char)active_holiday, game_theme_string()
  include\action\tankIDName.cpp:189:        ) + "|m_clientBits=|eventButtons={\"EventButtonData\":[{\"active\":false,\"
buttonAction\":\"eventmenu\",\"buttonTemplate\":\"BaseEventButton\",\"counter\":0,\"counterMax\":0,\"itemIdIcon\":6244,
\"name\":\"ClashEventButton\",\"order\":9,\"rcssClass\":\"clash-event\",\"text\":\"\"},{\"active\":true,\"buttonAction\
":\"dailychallengemenu\",\"buttonTemplate\":\"BaseEventButton\",\"counter\":0,\"counterMax\":0,\"itemIdIcon\":23,\"name
\":\"DailyChallenge\",\"order\":10,\"rcssClass\":\"daily_challenge\",\"text\":\"\"},{\"active\":true,\"buttonAction\":\
"openPiggyBank\",\"buttonTemplate\":\"BaseEventButton\",\"counter\":0,\"counterMax\":0,\"name\":\"PiggyBankButton\",\"o
rder\":20,\"rcssClass\":\"piggybank\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"showdungeonsui\",\"buttonTemp
late\":\"DungeonEventButton\",\"counter\":0,\"counterMax\":20,\"name\":\"ScrollsPurchaseButton\",\"order\":30,\"rcssCla
ss\":\"scrollbank\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"show_mailbox_ui\",\"buttonTemplate\":\"BaseEven
tButton\",\"counter\":0,\"counterMax\":0,\"name\":\"MailboxButton\",\"order\":30,\"rcssClass\":\"mailbox\",\"text\":\"\
"},{\"active\":false,\"buttonAction\":\"show_auction_ui\",\"buttonTemplate\":\"BaseEventButton\",\"counter\":0,\"counte
rMax\":0,\"name\":\"AuctionButton\",\"order\":30,\"rcssClass\":\"auction\",\"text\":\"\"},{\"active\":false,\"buttonTem
plate\":\"ActiveAuctionEventButton\",\"counter\":0,\"counterMax\":20,\"name\":\"ActiveAuctionButton\",\"order\":30,\"rc
ssClass\":\"activeauction\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"eventmenu\",\"buttonTemplate\":\"BaseEv
entButton\",\"counter\":0,\"counterMax\":0,\"itemIdIcon\":6244,\"name\":\"ClashEventButton\",\"order\":21,\"rcssClass\"
:\"clash-event\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"show_bingo_ui\",\"buttonTemplate\":\"BaseEventButt
on\",\"counter\":0,\"counterMax\":0,\"name\":\"WinterBingoButton\",\"order\":49,\"rcssClass\":\"wf-bingo\",\"text\":\"\
"},{\"active\":false,\"buttonAction\":\"show_bingo_ui\",\"buttonTemplate\":\"BaseEventButton\",\"name\":\"UbiBingoButto
n\",\"order\":50,\"rcssClass\":\"ubi-bingo\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"winterrallymenu\",\"bu
ttonTemplate\":\"BaseEventButton\",\"counter\":0,\"counterMax\":0,\"name\":\"WinterRallyButton\",\"order\":50,\"rcssCla
ss\":\"winter-rally\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"leaderboardBtnClicked\",\"buttonTemplate\":\"
BaseEventButton\",\"counter\":0,\"counterMax\":0,\"name\":\"AnniversaryLeaderboardButton\",\"order\":50,\"rcssClass\":\
"anniversary-leaderboard\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"euphoriaBtnClicked\",\"buttonTemplate\":
\"BaseEventButton\",\"counter\":0,\"counterMax\":0,\"name\":\"AnniversaryEuphoriaButton\",\"order\":50,\"rcssClass\":\"
anniversary-euphoria\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"openLnySparksPopup\",\"buttonTemplate\":\"Ba
seEventButton\",\"counter\":0,\"counterMax\":5,\"name\":\"LnyButton\",\"order\":50,\"rcssClass\":\"cny\",\"text\":\"\"}
,{\"active\":false,\"buttonAction\":\"ShowValentinesQuestDialog\",\"buttonTemplate\":\"EventButtonWithCounter\",\"count
er\":0,\"counterMax\":100,\"name\":\"ValentinesButton\",\"order\":50,\"rcssClass\":\"valentines_day\",\"text\":\"\"},{\
"active\":false,\"buttonAction\":\"showegseeventui\",\"buttonTemplate\":\"EventButtonWithCounter\",\"counter\":0,\"coun
terMax\":20,\"name\":\"EasterButton\",\"order\":50,\"rcssClass\":\"easter_event\",\"text\":\"\"},{\"active\":false,\"bu
ttonAction\":\"openStPatrickPiggyBank\",\"buttonTemplate\":\"BaseEventButton\",\"name\":\"StPatrickPBButton\",\"order\"
:50,\"rcssClass\":\"st_patrick_event\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"dailyrewardmenu\",\"buttonTe
mplate\":\"BaseEventButton\",\"counter\":0,\"counterMax\":1,\"name\":\"CincoPinataButton\",\"order\":50,\"rcssClass\":\
"cinco_pinata_event\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"show_fruit_mixer_dialog\",\"buttonTemplate\":
\"BaseEventButton\",\"counter\":0,\"counterMax\":0,\"name\":\"SPP_TropicalFruitsButton\",\"order\":50,\"rcssClass\":\"s
pp_tropical_fruits\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"claimprogressbar\",\"buttonTemplate\":\"EventB
uttonWithCounter\",\"counter\":0,\"counterMax\":0,\"name\":\"SummerfestButton\",\"order\":50,\"rcssClass\":\"summerfest
\",\"text\":\"\"},{\"active\":false,\"buttonAction\":\"claimprogressbar\",\"buttonTemplate\":\"EventButtonWithCounter\"
,\"counter\":0,\"counterMax\":15,\"name\":\"HalloweenButton\",\"order\":50,\"rcssClass\":\"halloween\",\"text\":\"\"}]}
"
  include\action\tankIDName.cpp:190:    });
  include\action\tankIDName.cpp:191:}



  hasil log :
  [SERVER] Running on http://localhost:3000
[REQ] GET /player/login/dashboard → 127.0.0.1 | 200
[REQ] GET /player/login/dashboard → 127.0.0.1 | 200
[REQ] GET /player/login/dashboard → 127.0.0.1 | 200
[REQ] GET /player/login/dashboard → 127.0.0.1 | 200
[REQ] POST /player/growid/checktoken → 127.0.0.1 | 200
[REQ] POST /player/growid/validate/checktoken → 127.0.0.1 | 200
[CHECKTOKEN] Parsed as form-urlencoded
[CHECKTOKEN] parsed growId=true password=true registration=false
[CHECKTOKEN] accountFound=true passwordMatches=true
[REQ] POST /player/growid/checktoken → 127.0.0.1 | 200
[REQ] POST /player/growid/validate/checktoken → 127.0.0.1 | 200
[CHECKTOKEN] Parsed as form-urlencoded
[CHECKTOKEN] parsed growId=true password=true registration=false
[CHECKTOKEN] accountFound=true passwordMatches=true
[REQ] POST /player/growid/checktoken → 127.0.0.1 | 200
[REQ] POST /player/growid/validate/checktoken → 127.0.0.1 | 200
[CHECKTOKEN] Parsed as form-urlencoded
[CHECKTOKEN] parsed growId=true password=true registration=false
[CHECKTOKEN] accountFound=true passwordMatches=true
[REQ] POST /player/growid/checktoken → 127.0.0.1 | 200
[REQ] POST /player/growid/validate/checktoken → 127.0.0.1 | 200
[CHECKTOKEN] Parsed as form-urlencoded
[CHECKTOKEN] parsed growId=true password=true registration=false
[CHECKTOKEN] accountFound=true passwordMatches=true
[REQ] POST /player/login/dashboard → 127.0.0.1 | 200
[REQ] POST /player/growid/login/validate → 127.0.0.1 | 200
[REQ] POST /player/growid/checktoken → 127.0.0.1 | 200
[REQ] POST /player/growid/validate/checktoken → 127.0.0.1 | 200
[CHECKTOKEN] Parsed as form-urlencoded
[CHECKTOKEN] parsed growId=true password=true registration=false
[CHECKTOKEN] accountFound=true passwordMatches=true


[AUTH] rejected game login; uid_field=false uid_valid=false ticket_field=false ticket_numeric=false ticket_len=0 ticket_status=not-present growid_field=true password_field=false protocol=227

protocol|227
ltoken|[REDACTED]
platformID|0,1,1
adc|1

[AUTH] protocol stage accepted growid=aLL uid=2 guest=false ticket=issued

tankIDName|aLL
tankIDPass|[REDACTED]
requestedName|
f|1
protocol|227
game_version|5.61
fz|23883768
cbits|0
player_age|25
GDPR|1
FCMToken|
category|_-5100
totalPlaytime|0
klv|89da5b76dac0904dfe0ef95c9eed41c15ef57de461a4e831ad84dbf724317eab
hash2|1275626645
meta|gurotopia
fhash|-716928004
rid|0273982916A390420007CAF100EB0AB0
platformID|0,1,1
deviceVersion|0
country|us
hash|1459758263
mac|2c:f0:5d:05:6c:c7
wk|D2ACFFA50551B2DA9CE952EAE5E32426
zf|1575712169lmode|1
user|2
UUIDToken|[REDACTED]
doorID|658285972
aat|2
[AUTH] rejected game login; uid_field=false uid_valid=false ticket_field=false ticket_numeric=false ticket_len=0 ticket_status=not-present growid_field=true password_field=false protocol=227

protocol|227
ltoken|[REDACTED]
platformID|0,1,1
adc|1
╤
[AUTH] protocol stage accepted growid=aLL uid=2 guest=false ticket=issued

tankIDName|aLL
tankIDPass|[REDACTED]
requestedName|
f|1
protocol|227
game_version|5.61
fz|23883768
cbits|0
player_age|25
GDPR|1
FCMToken|
category|_-5100
totalPlaytime|0
klv|89da5b76dac0904dfe0ef95c9eed41c15ef57de461a4e831ad84dbf724317eab
hash2|1275626645
meta|gurotopia
fhash|-716928004
rid|0273982916A390420007CAF100EB0AB0
platformID|0,1,1
deviceVersion|0
country|us
hash|1459758263
mac|2c:f0:5d:05:6c:c7
wk|D2ACFFA50551B2DA9CE952EAE5E32426
zf|1575712169lmode|1
user|2
UUIDToken|[REDACTED]
doorID|1287944812
aat|2R
[AUTH] rejected game login; uid_field=false uid_valid=false ticket_field=false ticket_numeric=false ticket_len=0 ticket_status=not-present growid_field=true password_field=false protocol=227



2026/11/11 14:34:57.300 ←[34mINFO←[0m   maxprocs: Leaving GOMAXPROCS=4: CPU quota undefined
2026/11/11 14:34:57.300 ←[34mINFO←[0m   GOMEMLIMIT is updated   {"GOMEMLIMIT": 15428111155, "previous": 9223372036854775807}
2026/11/11 14:34:57.302 ←[34mINFO←[0m   using config from file  {"file": "C:\\GTPS\\Caddyfile"}
2026/11/11 14:34:57.302 ←[34mINFO←[0m   adapted config to JSON  {"adapter": "caddyfile"}
2026/11/11 14:34:57.302 ←[33mWARN←[0m   Caddyfile input is not formatted; run 'caddy fmt --overwrite' to fix inconsistencies    {"adapter": "caddyfile", "file": "C:\\GTPS\\Caddyfile", "line": 1}
2026/11/11 14:34:57.317 ←[34mINFO←[0m   admin   admin endpoint started  {"address": "localhost:2019", "enforce_origin": false, "origins": ["//localhost:2019", "//[::1]:2019", "//127.0.0.1:2019"]}
2026/11/11 14:34:57.317 ←[34mINFO←[0m   tls.cache.maintenance   started background certificate maintenance      {"cache": "0x3762985ba600"}
2026/11/11 14:34:57.318 ←[34mINFO←[0m   http.auto_https skipping automatic certificate management because one or more matching certificates are already loaded  {"domain": "www.growtopia1.com", "server_name": "srv0"}
2026/11/11 14:34:57.319 ←[34mINFO←[0m   http.auto_https skipping automatic certificate management because one or more matching certificates are already loaded  {"domain": "www.growtopia2.com", "server_name": "srv0"}
2026/11/11 14:34:57.319 ←[34mINFO←[0m   http.auto_https enabling automatic HTTP->HTTPS redirects        {"server_name": "srv0"}
2026/11/11 14:34:57.319 ←[34mINFO←[0m   http    enabling HTTP/3 listener        {"addr": "127.0.0.1:443"}
2026/11/11 14:34:57.319 ←[34mINFO←[0m   http.log        server running  {"name": "srv0", "protocols": ["h1", "h2", "h3"]}
2026/11/11 14:34:57.320 ←[33mWARN←[0m   http    HTTP/2 skipped because it requires TLS  {"network": "tcp", "addr": "127.0.0.1:80"}
2026/11/11 14:34:57.320 ←[33mWARN←[0m   http    HTTP/3 skipped because it requires TLS  {"network": "tcp", "addr": "127.0.0.1:80"}
2026/11/11 14:34:57.320 ←[34mINFO←[0m   http.log        server running  {"name": "remaining_auto_https_redirects", "protocols": ["h1", "h2", "h3"]}
2026/11/11 14:34:57.320 ←[34mINFO←[0m   autosaved config (load with --resume flag)      {"file": "C:\\Users\\putra\\AppData\\Roaming\\Caddy\\autosave.json"}
2026/11/11 14:34:57.321 ←[34mINFO←[0m   serving initial configuration
2026/11/11 14:34:57.323 ←[34mINFO←[0m   tls     storage cleaning happened too recently; skipping for now        {"storage": "FileStorage:C:\\Users\\putra\\AppData\\Roaming\\Caddy", "instance": "9783478c-36dd-44af-9c0d-6f5937fa0274", "try_again": "2026/11/12 14:34:57.323", "try_again_in": 86400}
2026/11/11 14:34:57.326 ←[34mINFO←[0m   tls     finished cleaning storage units

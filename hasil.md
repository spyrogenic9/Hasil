PS C:\GTPS\login-gurotopia> Get-Content .\index.ts | Select-Object -Skip 135 -First 180
/**
 * @note validate login endpoint - validates GrowID credentials from MySQL
 * @param req - express request with growId, password, _token
 * @param res - express response with token
 */
app.all(
  '/player/growid/login/validate',
  async (req: Request, res: Response) => {
    const clientIp = getClientIp(req);

    const { blocked, remaining } = checkIpBlocked(clientIp);
    if (blocked) {
      // @note generate error html directly
      const clientData = '';
      const errorMessage = 'Login attempts exhausted from your IP, Please try again later after 1 hour';
      const templatePath = path.join(process.cwd(), 'template', 'dashboard.html');
      const templateContent = fs.readFileSync(templatePath, 'utf-8');
      const errorHtml = `<div class="text-danger text-danger-wrapper"><ul><li>${errorMessage}</li></ul></div>`;
      let htmlContent = templateContent.replace('{{ data }}', Buffer.from(clientData).toString('base64'));
      htmlContent = htmlContent.replace('<div class="row div-content-center">', `${errorHtml}<div class="row div-content-center">`);
      res.setHeader('Content-Type', 'text/html');
      res.send(htmlContent);
      return;
    }

    try {
      const formData = req.body as Record<string, string>;
      const email = formData.email;
      const _token = formData._token;
      const growId = formData.growId;
      const password = formData.password;
      if (formData.guest === '1') {
        if (typeof _token !== 'string' || !_token || _token.length > 16384) {
          res.status(400).json({ status: 'error', message: 'Invalid client token' });
          return;
        }
        const token = Buffer.from(`_token=${_token}&guest=1&reg=0`).toString('base64');
        res.send(JSON.stringify({
          status: 'success',
          message: 'Guest session issued.',
          token,
          url: '',
          accountType: 'growtopia',
        }));
        return;
      }

      // @note registration flow when email is provided
      if (email) {
        const confirmPassword = formData.password_confirmation;
        const clientData = btoa(growId || '');
        const templatePath = path.join(process.cwd(), 'template', 'dashboard.html');
        const templateContent = fs.readFileSync(templatePath, 'utf-8');

        if (!growId || !password) {
          const errorMessage = 'Missing GrowID or password for registration.';
          const errorHtml = `<div class="text-danger text-danger-wrapper"><ul><li>${errorMessage}</li></ul></div>`;
          let htmlContent = templateContent.replace('{{ data }}', Buffer.from(clientData).toString('base64'));
          htmlContent = htmlContent.replace('<div class="row div-content-center">', `${errorHtml}<div class="row div-content-center">`);
          res.setHeader('Content-Type', 'text/html');
          res.send(htmlContent);
          return;
        }

        if (confirmPassword && password !== confirmPassword) {
          const errorMessage = 'Passwords do not match.';
          const errorHtml = `<div class="text-danger text-danger-wrapper"><ul><li>${errorMessage}</li></ul></div>`;
          let htmlContent = templateContent.replace('{{ data }}', Buffer.from(clientData).toString('base64'));
          htmlContent = htmlContent.replace('<div class="row div-content-center">', `${errorHtml}<div class="row div-content-center">`);
          res.setHeader('Content-Type', 'text/html');
          res.send(htmlContent);
          return;
        }

        const existing = await db`SELECT uid FROM peer WHERE growid = ${growId} LIMIT 1`;
        if (existing.length > 0) {
          const errorMessage = `GrowID "${growId}" is already taken. Please choose another name.`;
          const errorHtml = `<div class="text-danger text-danger-wrapper"><ul><li>${errorMessage}</li></ul></div>`;
          let htmlContent = templateContent.replace('{{ data }}', Buffer.from(clientData).toString('base64'));
          htmlContent = htmlContent.replace('<div class="row div-content-center">', `${errorHtml}<div class="row div-content-center">`);
          res.setHeader('Content-Type', 'text/html');
          res.send(htmlContent);
          return;
        }

        resetAttempts(clientIp);

        const token = Buffer.from(
          `_token=${_token}&growId=${growId}&password=${password}&reg=1`,
        ).toString('base64');

        res.send(
          JSON.stringify({
            status: 'success',
            message: 'Account Created and Validated.',
            token,
            url: '',
            accountType: 'growtopia',
          }),
        );
        return;
      }

      if (!growId || !password) {
        res.status(200).json({
          status: 'error',
          message: 'Missing growId or password',
        });
        return;
      }

      const rows = await db`SELECT * FROM peer WHERE growid = ${growId} LIMIT 1`;

      if (rows.length === 0) {
        const attemptsLeft = recordFailedAttempt(clientIp);
        // @note generate error html directly
        const clientData = btoa(`${growId}`);
        const errorMessage = attemptsLeft > 0
          ? `Account credentials missmatched. You have ${attemptsLeft} attempt(s) left.`
          : 'Login attempts exhausted from your IP, Please try again later after 1 hour';
        const templatePath = path.join(process.cwd(), 'template', 'dashboard.html');
        const templateContent = fs.readFileSync(templatePath, 'utf-8');
        const errorHtml = `<div class="text-danger text-danger-wrapper"><ul><li>${errorMessage}</li></ul></div>`;
        let htmlContent = templateContent.replace('{{ data }}', Buffer.from(clientData).toString('base64'));
        htmlContent = htmlContent.replace('<div class="row div-content-center">', `${errorHtml}<div class="row div-content-center">`);
        res.setHeader('Content-Type', 'text/html');
        res.send(htmlContent);
        return;
      }

      const user = rows[0];
      if (user.password !== password) {
        const attemptsLeft = recordFailedAttempt(clientIp);
        // @note generate error html directly
        const clientData = btoa(`${growId}`);
        const errorMessage = attemptsLeft > 0
          ? `Account credentials missmatched. You have ${attemptsLeft} attempt(s) left.`
          : 'Login attempts exhausted from your IP, Please try again later after 1 hour';
        const templatePath = path.join(process.cwd(), 'template', 'dashboard.html');
        const templateContent = fs.readFileSync(templatePath, 'utf-8');
        const errorHtml = `<div class="text-danger text-danger-wrapper"><ul><li>${errorMessage}</li></ul></div>`;
        let htmlContent = templateContent.replace('{{ data }}', Buffer.from(clientData).toString('base64'));
        htmlContent = htmlContent.replace('<div class="row div-content-center">', `${errorHtml}<div class="row div-content-center">`);
        res.setHeader('Content-Type', 'text/html');
        res.send(htmlContent);
        return;
      }

      resetAttempts(clientIp);

      const token = Buffer.from(
        `_token=${_token}&growId=${growId}&password=${password}&reg=0`,
      ).toString('base64');

      res.send(
        JSON.stringify({
          status: 'success',
          message: 'Account Validated.',
          token,
          url: '',
          accountType: 'growtopia',
        }),
      );
    } catch (error) {
      console.log(`[ERROR]: ${error}`);
      res.status(500).json({
        status: 'error',
        message: 'Internal Server Error',
      });
    }
  },
);

/**
 * @note first checktoken endpoint - redirects to validate endpoint
 * @param req - express request with refreshToken and clientData
 * @param res - express response with updated token
 */
app.all('/player/growid/checktoken', async (_req: Request, res: Response) => {
  return res.redirect(307, '/player/growid/validate/checktoken');
PS C:\GTPS\login-gurotopia> Get-ChildItem . -Recurse -File -Include *.ts |
>> Where-Object { $_.FullName -notmatch '\\node_modules\\|\\dist\\' } |
>> Select-String -Pattern 'checktoken|UUIDToken|ticket|ltoken|protocol stage|token_status' -Context 5,12

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


PS C:\GTPS\login-gurotopia> Set-Location C:\GTPS\Gurotopia
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Get-Content .\include\action\tankIDName.cpp |
>> Select-Object -First 180
#include "pch.hpp"

#include "automate/holiday.hpp"
#include "admin/admin.hpp"
#include "security/login_session.hpp"

#include <algorithm>

#include <charconv>
#include <cctype>

#include "tankIDName.hpp"

namespace
{
    std::string trim_field(std::string value)
    {
        const auto is_edge_space = [](unsigned char c)
        {
            return c == '\r' || c == '\n' || c == '\0' || c == ' ' || c == '\t';
        };
        while (!value.empty() && is_edge_space(static_cast<unsigned char>(value.front())))
            value.erase(value.begin());
        while (!value.empty() && is_edge_space(static_cast<unsigned char>(value.back())))
            value.pop_back();
        return value;
    }
}

/* GameLogicComponent::OnInitialLogonAccepted(VariantList*) */
void action::tankIDName(ENetEvent& event, const std::string& header)
{
    if (event.peer == nullptr || event.peer->data == nullptr) return;
    ::peer *pPeer = static_cast<::peer*>(event.peer->data);

    // The receive layer normalizes line breaks, but some client builds send
    // CRLF or a mixture of line and pipe separators. Normalize again here.
    std::string normalized = header;
    // receive.cpp already converts LF delimiters to '|'. Remove the CR half
    // of CRLF instead of converting it again (which would create empty fields
    // and shift every key/value pair by one position).
    std::erase(normalized, '\r');
    for (char& c : normalized)
        if (c == '\n') c = '|';

    const std::vector<std::string> fields = readch(normalized, '|');
    if (fields.size() < 2)
    {
        print("[AUTH] ignored empty/short tankIDName packet\n");
        return;
    }

    std::string protocol{};
    std::string requested_growid{};
    std::string requested_password{};
    std::string uuid_text{};
    int requested_uid{};
    bool has_user_id = false;
    bool user_id_valid = false;
    bool has_uuid_token = false;
    bool uuid_token_valid = false;
    std::uint32_t uuid_token{};
    bool growid_field = false;
    bool password_field = false;

    // Packet fields are key/value pairs. Step by two so an empty value
    // (e.g. requestedName|) cannot shift the parser onto the next key.
    for (std::size_t i = 0; i + 1 < fields.size(); i += 2)
    {
        const std::string key = trim_field(fields[i]);
        const std::string value = trim_field(fields[i + 1]);

        if (key == "tankIDName")
        {
            requested_growid = value;
            growid_field = !value.empty();
        }
        else if (key == "tankIDPass")
        {
            requested_password = value;
            password_field = !value.empty();
        }
        else if (key == "protocol") protocol = value;
        else if (key == "country") pPeer->country = value;
        else if (key == "user")
        {
            has_user_id = true;
            const auto parsed = std::from_chars(value.data(), value.data() + value.size(), requested_uid);
            user_id_valid = !value.empty() && parsed.ec == std::errc{} &&
                parsed.ptr == value.data() + value.size() && requested_uid > 0;
        }
        else if (key == "UUIDToken")
        {
            has_uuid_token = true;
            uuid_text = value;
            const auto parsed = std::from_chars(value.data(), value.data() + value.size(), uuid_token);
            uuid_token_valid = !value.empty() && parsed.ec == std::errc{} &&
                parsed.ptr == value.data() + value.size() && uuid_token != 0;
        }
        else if (key == "game_version")
        {
            try { pPeer->game_version = std::stof(value); }
            catch (const std::logic_error&) {}
        }
    }

    // requestedName is also routed here by legacy dispatch. It is not a
    // complete login packet and must not cause a disconnect by itself.
    if (protocol.empty())
    {
        print("[AUTH] ignored non-auth name request (protocol field absent)\n");
        return;
    }
    try
    {
        if (std::stoi(protocol) <= 0) return;
    }
    catch (...) { return; }

    bool loaded = false;
    bool ticket_accepted = false;
    std::string ticket_status = "not-present";

    if (has_user_id && user_id_valid && has_uuid_token && uuid_token_valid)
    {
        const auto result = login_session::consume_detailed(uuid_token, requested_uid);
        switch (result)
        {
            case login_session::consume_result::accepted:
                ticket_accepted = true;
                ticket_status = "accepted";
                loaded = pPeer->load_by_uid(requested_uid);
                break;
            case login_session::consume_result::not_found: ticket_status = "not-found"; break;
            case login_session::consume_result::uid_mismatch: ticket_status = "uid-mismatch"; break;
            case login_session::consume_result::expired: ticket_status = "expired"; break;
        }
    }
    else if (has_uuid_token)
    {
        ticket_status = "malformed";
    }

    if (!loaded && growid_field && password_field)
    {
        // Never trust the supplied UID: MariaDB must authenticate the account
        // and resolve to precisely the UID sent by the client.
        loaded = pPeer->load(requested_growid, requested_password);
        if (loaded && has_user_id && (!user_id_valid || pPeer->user_id != requested_uid))
            loaded = false;
    }

    if (!loaded)
    {
        print(std::format(
            "[AUTH] rejected game login; uid_field={} uid_valid={} ticket_field={} ticket_numeric={} ticket_len={} ticket_status={} growid_field={} password_field={} protocol={}\n",
            has_user_id, user_id_valid, has_uuid_token, uuid_token_valid,
            uuid_text.size(), ticket_status, growid_field, password_field, protocol));
        send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
        enet_peer_disconnect_later(event.peer, 0);
        return;
    }

    print(std::format("[AUTH] accepted growid={} uid={} guest={} method={} ticket_status={}\n",
        pPeer->growid, pPeer->user_id, pPeer->is_guest,
        ticket_accepted ? "ticket" : "credential-fallback", ticket_status));

    if (admin::is_banned(pPeer->growid))
    {
        print(std::format("[AUTH] blocked banned account at game stage: {}\n", pPeer->growid));
        send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
        enet_peer_disconnect_later(event.peer, 0);
        return;
    }
    pPeer->muted = admin::is_muted(pPeer->growid);

    send_varlist(event.peer, { "OnOverrideGDPRFromServer", 18, 1, 0, 1 });

    /* v5.61 */
    send_varlist(event.peer, {
PS C:\GTPS\Gurotopia> Get-ChildItem . -Recurse -File -Include *.cpp,*.hpp,*.h |
>> Where-Object { $_.FullName -notmatch '\\build\\|\\\.git\\' } |
>> Select-String -Pattern 'consume_detailed|login_session|class hPipe|struct hPipe|hPipe::|uid_field|ticket_field' -Context 4,10

  include\action\protocol.cpp:1:#include "pch.hpp"
  include\action\protocol.cpp:2:
  include\action\protocol.cpp:3:#include "https/server_data.hpp"
  include\action\protocol.cpp:4:#include "admin/admin.hpp"
> include\action\protocol.cpp:5:#include "security/login_session.hpp"
  include\action\protocol.cpp:6:#include "security/guest_identity.hpp"
  include\action\protocol.cpp:7:
  include\action\protocol.cpp:8:#include <algorithm>
  include\action\protocol.cpp:9:#include <chrono>
  include\action\protocol.cpp:10:#include <deque>
  include\action\protocol.cpp:11:#include <mutex>
  include\action\protocol.cpp:12:#include <unordered_map>
  include\action\protocol.cpp:13:
  include\action\protocol.cpp:14:#include <cctype>
  include\action\protocol.cpp:15:
  include\action\protocol.cpp:181:        return;
  include\action\protocol.cpp:182:    }
  include\action\protocol.cpp:183:    pPeer->muted = admin::is_muted(pPeer->growid);
  include\action\protocol.cpp:184:
> include\action\protocol.cpp:185:    const std::uint32_t session_token = login_session::issue(pPeer->user_id);
  include\action\protocol.cpp:186:    if (session_token == 0)
  include\action\protocol.cpp:187:    {
  include\action\protocol.cpp:188:        print(std::format("[AUTH] failed to issue session ticket for uid={}\n", pPeer
->user_id));
  include\action\protocol.cpp:189:        send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
  include\action\protocol.cpp:190:        enet_peer_disconnect_later(event.peer, 0);
  include\action\protocol.cpp:191:        return;
  include\action\protocol.cpp:192:    }
  include\action\protocol.cpp:193:
  include\action\protocol.cpp:194:    print(std::format("[AUTH] protocol stage accepted growid={} uid={} guest={} ticke
t=issued\n",
  include\action\protocol.cpp:195:        pPeer->growid, pPeer->user_id, guest_login));
  include\action\tankIDName.cpp:1:#include "pch.hpp"
  include\action\tankIDName.cpp:2:
  include\action\tankIDName.cpp:3:#include "automate/holiday.hpp"
  include\action\tankIDName.cpp:4:#include "admin/admin.hpp"
> include\action\tankIDName.cpp:5:#include "security/login_session.hpp"
  include\action\tankIDName.cpp:6:
  include\action\tankIDName.cpp:7:#include <algorithm>
  include\action\tankIDName.cpp:8:
  include\action\tankIDName.cpp:9:#include <charconv>
  include\action\tankIDName.cpp:10:#include <cctype>
  include\action\tankIDName.cpp:11:
  include\action\tankIDName.cpp:12:#include "tankIDName.hpp"
  include\action\tankIDName.cpp:13:
  include\action\tankIDName.cpp:14:namespace
  include\action\tankIDName.cpp:15:{
  include\action\tankIDName.cpp:122:    std::string ticket_status = "not-present";
  include\action\tankIDName.cpp:123:
  include\action\tankIDName.cpp:124:    if (has_user_id && user_id_valid && has_uuid_token && uuid_token_valid)
  include\action\tankIDName.cpp:125:    {
> include\action\tankIDName.cpp:126:        const auto result = login_session::consume_detailed(uuid_token, requested_u
id);
  include\action\tankIDName.cpp:127:        switch (result)
  include\action\tankIDName.cpp:128:        {
> include\action\tankIDName.cpp:129:            case login_session::consume_result::accepted:
  include\action\tankIDName.cpp:130:                ticket_accepted = true;
  include\action\tankIDName.cpp:131:                ticket_status = "accepted";
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
  include\action\tankIDName.cpp:141:        ticket_status = "malformed";
  include\action\tankIDName.cpp:142:    }
  include\action\tankIDName.cpp:143:
  include\action\tankIDName.cpp:144:    if (!loaded && growid_field && password_field)
  include\action\tankIDName.cpp:145:    {
  include\action\tankIDName.cpp:146:        // Never trust the supplied UID: MariaDB must authenticate the account
  include\action\tankIDName.cpp:152:
  include\action\tankIDName.cpp:153:    if (!loaded)
  include\action\tankIDName.cpp:154:    {
  include\action\tankIDName.cpp:155:        print(std::format(
> include\action\tankIDName.cpp:156:            "[AUTH] rejected game login; uid_field={} uid_valid={} ticket_field={}
ticket_numeric={} ticket_len={} ticket_status={} growid_field={} password_field={} protocol={}\n",
  include\action\tankIDName.cpp:157:            has_user_id, user_id_valid, has_uuid_token, uuid_token_valid,
  include\action\tankIDName.cpp:158:            uuid_text.size(), ticket_status, growid_field, password_field, protocol
));
  include\action\tankIDName.cpp:159:        send_gameMessage(event.peer, {.message = "action|logon_fail\n"});
  include\action\tankIDName.cpp:160:        enet_peer_disconnect_later(event.peer, 0);
  include\action\tankIDName.cpp:161:        return;
  include\action\tankIDName.cpp:162:    }
  include\action\tankIDName.cpp:163:
  include\action\tankIDName.cpp:164:    print(std::format("[AUTH] accepted growid={} uid={} guest={} method={} ticket_s
tatus={}\n",
  include\action\tankIDName.cpp:165:        pPeer->growid, pPeer->user_id, pPeer->is_guest,
  include\action\tankIDName.cpp:166:        ticket_accepted ? "ticket" : "credential-fallback", ticket_status));
  include\security\login_session.hpp:6:#include <unordered_map>
  include\security\login_session.hpp:7:
  include\security\login_session.hpp:8:#include <openssl/rand.h>
  include\security\login_session.hpp:9:
> include\security\login_session.hpp:10:namespace login_session
  include\security\login_session.hpp:11:{
  include\security\login_session.hpp:12:    struct ticket
  include\security\login_session.hpp:13:    {
  include\security\login_session.hpp:14:        int user_id{};
  include\security\login_session.hpp:15:        std::chrono::steady_clock::time_point expires{};
  include\security\login_session.hpp:16:    };
  include\security\login_session.hpp:17:
  include\security\login_session.hpp:18:    enum class consume_result
  include\security\login_session.hpp:19:    {
  include\security\login_session.hpp:20:        accepted,
  include\security\login_session.hpp:51:        }
  include\security\login_session.hpp:52:        return 0;
  include\security\login_session.hpp:53:    }
  include\security\login_session.hpp:54:
> include\security\login_session.hpp:55:    inline consume_result consume_detailed(std::uint32_t token, int user_id)
  include\security\login_session.hpp:56:    {
  include\security\login_session.hpp:57:        if (token == 0 || user_id <= 0) return consume_result::not_found;
  include\security\login_session.hpp:58:
  include\security\login_session.hpp:59:        std::lock_guard lock(ticket_mutex);
  include\security\login_session.hpp:60:        const auto it = active_tickets.find(token);
  include\security\login_session.hpp:61:        if (it == active_tickets.end()) return consume_result::not_found;
  include\security\login_session.hpp:62:
  include\security\login_session.hpp:63:        if (it->second.expires <= std::chrono::steady_clock::now())
  include\security\login_session.hpp:64:        {
  include\security\login_session.hpp:65:            active_tickets.erase(it);
  include\security\login_session.hpp:76:    }
  include\security\login_session.hpp:77:
  include\security\login_session.hpp:78:    inline bool consume(std::uint32_t token, int user_id)
  include\security\login_session.hpp:79:    {
> include\security\login_session.hpp:80:        return consume_detailed(token, user_id) == consume_result::accepted;
  include\security\login_session.hpp:81:    }
  include\security\login_session.hpp:82:}
  include\tools\string.hpp:6:    @return std::vector<std::string> storing each split off from c found in the str.
  include\tools\string.hpp:7:*/
  include\tools\string.hpp:8:extern std::vector<std::string> readch(const std::string &str, char deli) ;
  include\tools\string.hpp:9:
> include\tools\string.hpp:10:struct hPipe
  include\tools\string.hpp:11:{
  include\tools\string.hpp:12:    hPipe(const std::string &str)
  include\tools\string.hpp:13:    {
  include\tools\string.hpp:14:        std::vector<std::string> pipes = readch(str, '|');
  include\tools\string.hpp:15:        for (std::size_t i = 0; i + 1 < pipes.size(); ++i)
  include\tools\string.hpp:16:            mPairs.emplace_back(pipes[i], pipes[i + 1]);
  include\tools\string.hpp:17:    }
  include\tools\string.hpp:18:    std::string operator[](const std::string &key) const
  include\tools\string.hpp:19:    {
  include\tools\string.hpp:20:        for (const std::pair<std::string, std::string> &pair : mPairs)
  tests\login_session_smoke.cpp:1:#include "pch.hpp"
> tests\login_session_smoke.cpp:2:#include "security/login_session.hpp"
  tests\login_session_smoke.cpp:3:
  tests\login_session_smoke.cpp:4:#include <cassert>
  tests\login_session_smoke.cpp:5:
  tests\login_session_smoke.cpp:6:int main()
  tests\login_session_smoke.cpp:7:{
> tests\login_session_smoke.cpp:8:    const std::uint32_t token = login_session::issue(42);
  tests\login_session_smoke.cpp:9:    assert(token != 0);
> tests\login_session_smoke.cpp:10:    assert(login_session::consume_detailed(token, 99) == login_session::consume_resu
lt::uid_mismatch);
> tests\login_session_smoke.cpp:11:    assert(login_session::consume_detailed(token, 42) == login_session::consume_resu
lt::accepted);
> tests\login_session_smoke.cpp:12:    assert(login_session::consume_detailed(token, 42) == login_session::consume_resu
lt::not_found);
  tests\login_session_smoke.cpp:13:    return 0;
  tests\login_session_smoke.cpp:14:}

PS C:\GTPS\Gurotopia> Get-Content .\include\action\tankIDName.cpp |
>> Select-Object -First 110
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
PS C:\GTPS\Gurotopia> cd C:\GTPS\login-gurotopia
PS C:\GTPS\login-gurotopia>
PS C:\GTPS\login-gurotopia> Get-Content .\index.ts |
>> Select-Object -Skip 140 -First 165
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
PS C:\GTPS\login-gurotopia> Get-Content .\index.ts |
>> Select-Object -Skip 313 -First 150
app.all('/player/growid/checktoken', async (_req: Request, res: Response) => {
  return res.redirect(307, '/player/growid/validate/checktoken');
});

/**
 * @note second checktoken endpoint - validates token and returns updated token
 * @param req - express request with refreshToken and clientData
 * @param res - express response with updated token
 */
app.all(
  '/player/growid/validate/checktoken',
  async (req: Request, res: Response) => {
    try {
      let refreshToken: string | undefined;
      let clientData: string | undefined;
      let source = 'empty';
      const contentType = req.headers['content-type'] || '';

      if (typeof req.body === 'object' && req.body !== null) {
        const formData = req.body as Record<string, string>;

        if ('refreshToken' in formData || 'clientData' in formData) {
          refreshToken = formData.refreshToken;
          clientData = formData.clientData;
          source = contentType.includes('application/json')
            ? 'json/object'
            : 'form-urlencoded';
        } else if (Object.keys(formData).length === 1) {
          const rawPayload = Object.keys(formData)[0];
          const params = new URLSearchParams(rawPayload);
          refreshToken = params.get('refreshToken') || undefined;
          clientData = params.get('clientData') || undefined;
          if (refreshToken || clientData) {
            source = 'single-key-form-payload';
          }
        }
      } else if (typeof req.body === 'string' && req.body.length > 0) {
        const params = new URLSearchParams(req.body);
        refreshToken = params.get('refreshToken') || undefined;
        clientData = params.get('clientData') || undefined;
        source = 'string/body-parser';
      }

      if (
        (!refreshToken || !clientData) &&
        req.readable &&
        !req.readableEnded
      ) {
        const rawBody = await new Promise<string>((resolve, reject) => {
          let rawPayload = '';

          req.on('data', (chunk: Buffer | string) => {
            rawPayload += chunk.toString();
          });
          req.on('end', () => resolve(rawPayload));
          req.on('error', reject);
        });

        if (rawBody) {
          const params = new URLSearchParams(rawBody);
          refreshToken = params.get('refreshToken') || refreshToken;
          clientData = params.get('clientData') || clientData;
          if (refreshToken || clientData) {
            source = 'raw-stream';
          }
        }
      }

      console.log(`[CHECKTOKEN] Parsed as ${source}`);

      if (!refreshToken || !clientData) {
        console.log(`[ERROR]: Missing refreshToken or clientData`);
        res.status(200).json({
          status: 'error',
          message: 'Missing refreshToken or clientData',
        });
        return;
      }

      let decodedRefreshToken = Buffer.from(refreshToken, 'base64').toString(
        'utf-8',
      );

      // @note sync credentials check with db
      const tokenParams = new URLSearchParams(decodedRefreshToken);
      const tokenGrowId = tokenParams.get('growId');
      const tokenPassword = tokenParams.get('password');
      const isReg = tokenParams.get('reg') === '1';
      console.log(`[CHECKTOKEN] parsed growId=${Boolean(tokenGrowId)} password=${Boolean(tokenPassword)} registration=${isReg}`);

      if (tokenGrowId) {
        const rows = await db`SELECT password FROM peer WHERE growid = ${tokenGrowId} LIMIT 1`;
        console.log(`[CHECKTOKEN] accountFound=${rows.length > 0} passwordMatches=${rows.length > 0 && rows[0].password === tokenPassword}`);
        if (isReg) {
          if (rows.length > 0) {
            res.status(200).json({
              status: 'error',
              message: 'GrowID is already taken',
            });
            return;
          }
        } else if (tokenPassword) {
          if (rows.length === 0 || rows[0].password !== tokenPassword) {
            res.status(200).json({
              status: 'error',
              message: 'Invalid credentials in token',
            });
            return;
          }
        }
      }

      if (!isReg && decodedRefreshToken.includes('&reg=0')) {
        decodedRefreshToken = decodedRefreshToken.replace('&reg=0', '');
      }

      const token = Buffer.from(
        decodedRefreshToken.replace(
          /(_token=)[^&]*/,
          `$1${Buffer.from(clientData).toString('base64')}`,
        ),
      ).toString('base64');

      res.send(
        JSON.stringify({
          status: 'success',
          message: 'Account Validated.',
          token,
          url: '',
          accountType: 'growtopia',
          accountAge: 2,
        }),
      );
    } catch (error) {
      console.log(`[ERROR]: ${error}`);
      res.status(200).json({
        status: 'error',
        message: 'Internal Server Error',
      });
    }
  },
);

app.listen(PORT, '127.0.0.1', () => {
  console.log(`[SERVER] Running on http://localhost:${PORT}`);
});

export default app;
PS C:\GTPS\login-gurotopia> cd C:\GTPS\Gurotopia
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Get-ChildItem . -Recurse -File -Include *.cpp,*.hpp,*.h |
>> Where-Object { $_.FullName -notmatch '\\build\\|\\\.git\\' } |
>> Select-String -Pattern 'struct hPipe|class hPipe|hPipe::|consume_detailed|namespace login_session' -Context 5,12

  include\action\tankIDName.cpp:121:    bool ticket_accepted = false;
  include\action\tankIDName.cpp:122:    std::string ticket_status = "not-present";
  include\action\tankIDName.cpp:123:
  include\action\tankIDName.cpp:124:    if (has_user_id && user_id_valid && has_uuid_token && uuid_token_valid)
  include\action\tankIDName.cpp:125:    {
> include\action\tankIDName.cpp:126:        const auto result = login_session::consume_detailed(uuid_token, requested_u
id);
  include\action\tankIDName.cpp:127:        switch (result)
  include\action\tankIDName.cpp:128:        {
  include\action\tankIDName.cpp:129:            case login_session::consume_result::accepted:
  include\action\tankIDName.cpp:130:                ticket_accepted = true;
  include\action\tankIDName.cpp:131:                ticket_status = "accepted";
  include\action\tankIDName.cpp:132:                loaded = pPeer->load_by_uid(requested_uid);
  include\action\tankIDName.cpp:133:                break;
  include\action\tankIDName.cpp:134:            case login_session::consume_result::not_found: ticket_status = "not-fou
nd"; break;
  include\action\tankIDName.cpp:135:            case login_session::consume_result::uid_mismatch: ticket_status = "uid-
mismatch"; break;
  include\action\tankIDName.cpp:136:            case login_session::consume_result::expired: ticket_status = "expired";
 break;
  include\action\tankIDName.cpp:137:        }
  include\action\tankIDName.cpp:138:    }
  include\security\login_session.hpp:5:#include <mutex>
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
  include\security\login_session.hpp:21:        not_found,
  include\security\login_session.hpp:22:        uid_mismatch,
  include\security\login_session.hpp:50:            return token;
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
  include\security\login_session.hpp:66:            return consume_result::expired;
  include\security\login_session.hpp:67:        }
  include\security\login_session.hpp:75:        return consume_result::accepted;
  include\security\login_session.hpp:76:    }
  include\security\login_session.hpp:77:
  include\security\login_session.hpp:78:    inline bool consume(std::uint32_t token, int user_id)
  include\security\login_session.hpp:79:    {
> include\security\login_session.hpp:80:        return consume_detailed(token, user_id) == consume_result::accepted;
  include\security\login_session.hpp:81:    }
  include\security\login_session.hpp:82:}
  include\tools\string.hpp:5:    @param c the char to search for and split
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
  include\tools\string.hpp:21:            if (pair.first == key) return pair.second;
  include\tools\string.hpp:22:
  tests\login_session_smoke.cpp:5:
  tests\login_session_smoke.cpp:6:int main()
  tests\login_session_smoke.cpp:7:{
  tests\login_session_smoke.cpp:8:    const std::uint32_t token = login_session::issue(42);
  tests\login_session_smoke.cpp:9:    assert(token != 0);
> tests\login_session_smoke.cpp:10:    assert(login_session::consume_detailed(token, 99) == login_session::consume_resu
lt::uid_mismatch);
> tests\login_session_smoke.cpp:11:    assert(login_session::consume_detailed(token, 42) == login_session::consume_resu
lt::accepted);
> tests\login_session_smoke.cpp:12:    assert(login_session::consume_detailed(token, 42) == login_session::consume_resu
lt::not_found);
  tests\login_session_smoke.cpp:13:    return 0;
  tests\login_session_smoke.cpp:14:}

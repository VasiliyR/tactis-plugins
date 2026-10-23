# Restore the host's Tactis MCP connection

Use this only when connected work cannot discover Tactis tools, the host reports a startup/authentication failure, or the user asks to install/repair the connection. Loaded skills and installed package bytes do not establish an active MCP connection. A capability explanation or a draft from supplied text needs no setup.

## Identify the state before choosing a repair

1. Use the host's actual discovery for `list_projects` and `get_project_brief` (short English canonical names), once each if needed. If another Tactis tool is callable, inspect its actual schema: one missing/deferred command does not mean the whole server is unauthenticated. Use [tool recovery](session-recovery.md#missing-tool-or-compatibility-failure) for that command.
2. If no Tactis tools are registered, inspect the existing `tactis_ads` connection/source in the current host, workspace and session. Use supported connection status or the bounded startup error; do not invoke unavailable Tactis status/contract tools as a prerequisite for repair. Distinguish disabled/not selected, pending host approval, authentication required, failed connection and connected-but-tools-missing.
3. Check host authorization before compatibility/update diagnostics. A confirmed missing credential for the effective connection or an explicit authentication-required status means **host MCP is not authorized**. Unknown credential state means **host connection/authentication needs checking**, not a proven missing token. A stored token alone does not prove it is valid, bound to this workspace/source/resource, refreshed, or loaded by this session.

Do not stop at “tools unavailable”, repeatedly search the same empty catalogue, or start with `NESSY_CLI_DEBUG`, reinstall/update or “report version and missing capability”. Give the applicable concrete steps below. Inspect only the intended source's public configuration and sanitized status. Never dump credential files, token values, codes, callback query strings, client secrets, cookies or Authorization headers; never request them in chat. If local token storage is relevant, report only whether the matching record exists. Preserve other sources, grants and settings.

## Two different connections

**Host MCP authorization** lets the agent application connect to remote `tactis_ads`. Its normal browser consent selects accessible Tactis projects and displays requested scopes. Without that connection, project tools cannot run. **Provider authorization inside Tactis** connects Direct, Metrika or CRM through the cabinet's **Подключения** page. Provider consent cannot start the host MCP connection; host consent does not connect a provider or authorize advertising/spending. Use [connector setup](connector-setup.md) only after MCP works and the requested source needs it.

## Nessy: manual authorization that works without helper tools

Nessy is the user's local Craft Agents fork. Keep the working Nessy filenames and package identity; do not infer Qwen CLI commands, token storage, source schema or lifecycle from the extension manifest's similar shape.

When authentication is missing/required, give the user these steps directly:

1. Open **Nessy settings → MCP / Connections** (or **Sources** in a Craft-style build), in the workspace used by this chat.
2. Find the existing **tactis_ads** server/source and make sure it is enabled and selected for this chat. Use its actual source slug if different from the display name.
3. Click **Авторизовать / Подключить / Authorize / Connect**.
4. Complete the ordinary Tactis browser flow beginning at **https://app.tactis.ru**; it may send you to **https://tactis.ru** for login/consent. Check your account, selected projects and displayed rights.
5. Let Nessy save the credential in its own storage. In the reported CLI build this was `~/.nessy/mcp-oauth-tokens.json`, record `tactis_ads`. Craft-derived source builds can use encrypted, workspace/source-specific storage instead. Do not create, copy or edit token records by hand.
6. Start a **new Nessy session in the same workspace** and enable/select the source there. The reported build did not reload credentials into its existing connection; a supported native reconnect may activate other builds sooner. Verify actual project reads in that fresh session.

If the host actually exposes `source_oauth_trigger`, inspect its schema and use the existing source's exact `sourceSlug` only when starting browser authorization is authorized. This helper is optional; its absence never blocks the manual steps. If the user requested no browser/auth changes, give the steps and wait for that choice. Do not invent the tool or call Google/Slack/provider OAuth helpers for this MCP source.

## Craft Agents source checks, including a token that already exists

Upstream Craft Agents uses workspace `sources/<slug>/config.json`: `type="mcp"`, `enabled=true`, `mcp.transport="http"`, `mcp.url` set to the installed Tactis endpoint, `mcp.authType="oauth"`. Public package headers, where present, remain the six verified installed `X-Tactis-*` values. Source enabled, authenticated and selected for the current chat are separate states. Inspect the existing mapping; an imported extension does not prove its source is selected. Do not create a second connection or rewrite working source/identity settings to imitate Qwen.

Craft stores credentials encrypted and keys them by **workspace and source slug**. A token in another workspace, another source, or a legacy CLI file is not proof that the active source has credentials. The source's `isAuthenticated` flag is also not proof of a successful live call. Follow the installed fork's supported status/UI; upstream paths are reference information, not permission to search unrelated credential stores or migrate tokens.

For a stored credential plus a failed connection:

1. Read the actual source selection/enabled/auth status and first sanitized startup/connection error. Retain the source URL, host version and public installed version/digest; keep credentials private.
2. Distinguish an expired/revoked token or failed refresh (`401`, `invalid_grant`) from missing source activation, a transport/TLS/proxy/DNS failure, timeout, `5xx`, OAuth discovery/registration rejection or a rejected authorization request. These require different next actions; do not label them all “not authorized”. `403` requires current project/role checks, not changing identities.
3. With read-only network access, inspect public OAuth metadata and a credential-free MCP initialize probe at the actual endpoint. A normal native **GET `/mcp` returns `405`**; a credential-free POST initialize should challenge with `401`. Neither proves authenticated MCP works. TLS/network/`5xx` failures need their specific repair before another login. Public protected-resource metadata is at `https://app.tactis.ru/.well-known/oauth-protected-resource/mcp`, issuer metadata at `https://tactis.ru/.well-known/oauth-authorization-server`.
4. If authentication is valid but the source is inactive, use the supported enable/select/reconnect action for **that existing source** within the authorized repair. If the host identifies invalid credentials, request/complete normal reauthorization. Do not logout, erase caches, rotate tokens or retry refresh repeatedly as generic recovery. In Craft, `source_test` can save status, refresh credentials, download icons and activate tools; even `autoEnable=false` is not strictly read-only. Use it only when that maintenance is allowed.
5. If the same error remains after one supported reconnect/fresh session, report the concrete stage/error and needed user/operator action. Debug logs are a targeted follow-up after this classification. Do not claim a guessed cause or a successful restoration.

Upstream Craft native OAuth omits the optional authorization `scope` parameter. Tactis uses its documented default requested scopes `read reports write`, displays them on the ordinary consent page, and issues nothing before approval for selected projects. A server still returning `oauth_request_invalid` for that request needs the matching backend update; changing package headers or copying tokens cannot repair it. Craft's hosted relay callback is a separate, unsupported OAuth profile; native desktop loopback support does not establish hosted/WebUI support.

## Other supported hosts

Use the observed UI/status; verify CLI help before executing a command. Preserve the installed connection and host approval policy.

| Host | Concrete connection recovery |
| --- | --- |
| Qwen Code | Interactive `/mcp` → existing `tactis_ads` → **Auth** when authentication is required; reconnect through the supported dialog or open a fresh session. Qwen 0.25.2 no longer uses `/mcp auth`. Its `~/.qwen/mcp-oauth-tokens.json` is distinct from Craft source storage. A saved record may still have expired/failed refresh; inspect the actual error. |
| Codex | **Settings → MCP servers → tactis_ads → Authenticate**, when requested. Supported CLI: inspect `codex mcp list`/`get`, then `codex mcp login tactis_ads` only if login is needed. New session/restart, then discovery. Connected-but-missing-tools uses the existing [same-key Config delivery](plugin-updates.md#codex-mcp-delivery); do not reset OAuth. |
| Claude Code | `/mcp` → the actual plugin Tactis server → **Authenticate/Re-authenticate** for **Needs authentication**; **Failed to connect** → read Issue/error and use **Reconnect**. **Disabled/Pending approval** uses the displayed native action. Keep the plugin server instead of adding a duplicate. |
| ZCode | **Settings → MCP → Plugin MCP servers → Tactis → Open authorization** when required; complete browser consent. The host reconnects and loads tools; verify in a fresh chat. |
| Claude Cowork | **Customize → Plugins → Tactis Ads → Connectors**. **Not added** → Add (or workspace owner/admin); **Not connected** → Connect and browser consent; **Connected** → inspect the real connection error/selection. Keep the exact installed `/mcp/cloud/...` URL. Skills can load while a connector is disconnected. |
| ChatGPT Work | Open the existing personal/installed **Tactis Ads** plugin/connection in **Plugins**, complete its displayed connection/OAuth step, then a new Work chat with **@Tactis Ads**. Missing personal app/skills uses [cloud installation](plugin-updates.md#cloud-plugins); a ZIP alone does not install that connection. Keep the exact cloud URL. |
| DeepSeek Harness | Inspect the current profile's **tactis-dsh** bundle and applied/enabled skills/MCP using the available native manager. Read the packaged proxy's sanitized connection error, complete its normal OAuth only when required, and restart/reload that same profile. Keep the pinned proxy and existing credentials; do not delete `~/.mcp-auth` or invent a Harness login command. |

Qwen-specific stored-token caveat: in the inspected upstream 0.25.3 implementation, `oauth.enabled=true` can attempt refresh with only the configured `clientId`, ignoring a DCR client ID saved with the credential. An expired token may therefore lead to authentication-required despite a stored refresh credential. Apply this explanation only when the actual Qwen error/flow matches; it is not a Nessy diagnosis. Use one supported reauthorization when allowed, or a host update/fix confirmed to address it. Do not put a personal client ID into the shared manifest, remove OAuth settings, erase caches or loop logins. [Inspected Qwen refresh implementation](https://github.com/QwenLM/qwen-code/blob/76bdc7190d2e5368d7949fee070f11d994c5a951/packages/core/src/mcp/oauth-provider.ts).

## Verify and resume

After activation, discover real Tactis callables and perform only `get_plugin_update_status`, `list_projects`, then `get_project_brief` for the chosen accessible project (ask only when the choice is ambiguous). Verify installed host/version/digest and all eight declared skills separately from successful server reads. No Work, campaign, publication, grant change or spend is an installation test. If the current host cannot complete a step, state exactly what remains and resume any independent supplied-material work. Enter [plugin updates](plugin-updates.md) only for an installation/update request or an evidenced package/delivery incompatibility after connection checks.

Primary host references: [Craft MCP sources](https://thecraftagents.com/docs/sources/mcp-servers/overview/), [Craft OAuth](https://thecraftagents.com/docs/sources/mcp-servers/authentication/), [Craft sources](https://thecraftagents.com/docs/sources/overview/), [Qwen MCP](https://qwenlm.github.io/qwen-code-docs/en/developers/tools/mcp-server/), [Codex MCP](https://learn.chatgpt.com/docs/extend/mcp?surface=cli), [Claude MCP](https://code.claude.com/docs/en/mcp), [ZCode MCP](https://www.zcode.network/en/docs/mcp-services/), [Cowork connectors](https://claude.com/docs/plugins/overview), [ChatGPT personal MCP](https://developers.openai.com/plugins/quickstart), [Harness runtime](https://deepseek-harness.github.io/deepseek-harness/en/develop/practice/dynamic-cordis).

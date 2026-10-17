# Tactis Ads — Nessy

Official Tactis package for the user's private Qwen fork, based on the supplied `nessy-extension.json` interface. It contains the same canonical marketing skills as the other Tactis packages, a native Streamable HTTP MCP configuration (`httpUrl`) and its own `host=nessy` package identity. The package contains no credentials, project IDs or installation scripts.

Download the Nessy archive and SHA-256 from the current published [Tactis manifest](https://tactis.ru/install/manifest.json). Verify the hash and import the archive or extracted directory through this Nessy build's native extension manager. The exact payload is also available in `nessy/plugin` in the official repository. The archive root contains `nessy-extension.json`, `NESSY.md`, `skills`, `methodology.json` and `release.json`.

Nessy is a private fork. A user-provided acceptance report for Nessy CLI 0.13.12 on macOS confirmed the v1.15.0 dedicated Nessy archive hash, native installation and discovery of all eight skills in a fresh headless session. MCP and OAuth were not verified: the connection was blocked by an HTTP 503 network response. This is installation and skill-loading evidence for that version, not full installed-host end-to-end verification. Inspect the installed build's supported native import before installing; do not run the installer from the earlier user-supplied archive or overwrite existing settings and skills.

## Can Nessy use the Qwen package directly?

Not in the tested Nessy CLI 0.13.12: its native installer requires `nessy-extension.json` and rejected the unchanged v1.15.0 Qwen archive. Use the dedicated Nessy package. Another build could reuse the complete [Qwen package](https://github.com/VasiliyR/tactis-plugins/blob/main/qwen/README.md) only if it explicitly supports `qwen-extension.json`, `contextFileName`, skills, HTTP MCP/OAuth and headers; that compatibility needs separate evidence. If a build does support it, retain the complete Qwen package's `host=qwen` and digest. Do not rename its manifest or change its identity headers.

The official Nessy and Qwen packages use the same shared skills byte for byte. Their differences are the manifest filename, context filename and text, README and generated package identity. This Nessy wrapper is needed when the fork requires `nessy-extension.json`; it is not a separate marketing implementation.

Activate the native extension, authenticate `tactis_ads` in the browser, and start a fresh chat. Confirm every skill in `methodology.json`, `get_plugin_update_status`, `list_projects`, and read-only `get_project_brief` for a project the user selects. Those live checks require the actual Nessy application and account; artifact validation alone does not prove them.

Use the same native extension manager and installation scope to update or uninstall. Preserve other extensions, settings and OAuth credentials. The six public `X-Tactis-*` headers must match this package's `release.json`; they are compatibility hints, not credentials. Tactis access can be revoked separately in the account.

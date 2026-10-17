# Tactis Ads — Nessy

Official Tactis package for the user's private Qwen fork, based on the supplied `nessy-extension.json` interface. It contains the same canonical marketing skills as the other Tactis packages, a native Streamable HTTP MCP configuration (`httpUrl`) and its own `host=nessy` package identity. The package contains no credentials, project IDs or installation scripts.

Download the Nessy archive and SHA-256 from the current published [Tactis manifest](https://tactis.ru/install/manifest.json). Verify the hash and import the archive or extracted directory through this Nessy build's native extension manager. The exact payload is also available in `nessy/plugin` in the official repository. The archive root contains `nessy-extension.json`, `NESSY.md`, `skills`, `methodology.json` and `release.json`.

Nessy is a private fork: its marketplace format, exact native installation command and installed-host end-to-end behavior are not established by this package. Inspect the installed build's supported native import before installing. If it lacks extension loading, skills discovery or OAuth support, adapt that host component explicitly; do not run the installer from the earlier user-supplied archive or overwrite existing settings and skills.

## Can Nessy use the Qwen package directly?

Yes, conditionally: a Nessy build that retains native `qwen-extension.json` loading and honors `contextFileName`, skills, HTTP MCP/OAuth and headers can reuse the complete [Qwen package](https://github.com/VasiliyR/tactis-plugins/blob/main/qwen/README.md) unchanged. This has not been verified against the private build. The earlier supplied Nessy archive installs through a settings-copy script and provides no evidence of that native compatibility. Keep the Qwen package's `host=qwen` and digest if using it; the OAuth client's name may still be Nessy. Do not rename its manifest or change its identity headers.

The official Nessy and Qwen packages use the same shared skills byte for byte. Their differences are the manifest filename, context filename and text, README and generated package identity. This Nessy wrapper is needed when the fork requires `nessy-extension.json`; it is not a separate marketing implementation.

Activate the native extension, authenticate `tactis_ads` in the browser, and start a fresh chat. Confirm every skill in `methodology.json`, `get_plugin_update_status`, `list_projects`, and read-only `get_project_brief` for a project the user selects. Those live checks require the actual Nessy application and account; artifact validation alone does not prove them.

Use the same native extension manager and installation scope to update or uninstall. Preserve other extensions, settings and OAuth credentials. The six public `X-Tactis-*` headers must match this package's `release.json`; they are compatibility hints, not credentials. Tactis access can be revoked separately in the account.

# Tactis Ads — Qwen Code

Native Qwen Code extension: `qwen-extension.json`, all canonical skills and browser OAuth for `https://app.tactis.ru/mcp`. The MCP transport is Streamable HTTP (`httpUrl`). There are no credentials or project IDs in the package.

If skills load but MCP tools are absent, check the existing server's status in `/mcp` first. Choose `tactis_ads` → Auth only when authentication is required, then reconnect through the supported UI or start a new session. A token record alone does not establish a valid refreshed connection. Follow [MCP connection recovery](skills/tactis/references/mcp-connection.md) before reinstall/update or compatibility diagnostics. Provider OAuth inside Tactis is separate from this host authorization.

Download the Qwen archive and its SHA-256 from the current published [Tactis manifest](https://tactis.ru/install/manifest.json). Verify its hash and retain it at a stable path in a dedicated Tactis directory, such as `<your-Tactis-directory>/qwen/tactis.tar.gz`. Run `qwen extensions install <that-stable-path>` or install the extracted extension directory with `qwen extensions install <directory>`. The published repository also contains this exact payload in `qwen/plugin`. Qwen's `VasiliyR/tactis-plugins` marketplace entry currently describes Claude; native Qwen installation uses the explicit Qwen archive or directory.

Inspect extension permissions before accepting the native prompt. Restart Qwen or refresh extensions, authenticate `tactis_ads` through its native MCP OAuth flow, then start a fresh chat. Verify all skills listed in `methodology.json`, `get_plugin_update_status`, `list_projects` and `get_project_brief` for a project you select. Installation alone does not establish live access or a completed marketing task.

For updates, verify the new published archive and replace only the archive at the same stable source path, then run `qwen extensions update tactis`. For a local directory source, update that same verified source directory before running the command. Qwen rereads the original source; a version-specific download URL does not automatically select a newer release, and installing a second archive while `tactis` exists is not an update. Preserve other extensions, settings and authorization.

The exact package identity and normalized payload hashes are in `release.json`. Verify its listed payload files; the native manager's `.qwen-extension-install.json` is installation metadata outside the published payload. Public headers carry identity and do not grant access. Remove the extension through the native manager to uninstall; revoke Tactis access separately in the account if needed.

## Compatibility with Nessy


Both packages carry byte-identical shared skills, with distinct host wrappers and package identity. Renaming a manifest or editing identity headers invalidates that package; do not substitute Qwen identity to repair Nessy.

Official host documentation: [extensions](https://qwenlm.github.io/qwen-code-docs/en/users/extension/introduction/), [distribution](https://qwenlm.github.io/qwen-code-docs/en/users/extension/extension-releasing/), [MCP](https://qwenlm.github.io/qwen-code-docs/en/developers/tools/mcp-server/).

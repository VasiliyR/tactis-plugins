# Tactis Ads

Generated marketplace for Codex, Claude Code and ZCode, native Qwen Code extensions, and separate Claude Cowork and ChatGPT cloud packages. Install `tactis@tactis-ads` through your program's native plugin manager using its host instructions.

- Codex: add this Git repository with `--ref main`; its catalog is `.agents/plugins/marketplace.json`.
- Claude Code: add this Git repository with `#main` and the observed scope; its catalog is `.claude-plugin/marketplace.json`.
- ZCode: verify native CLI support, then use `zcode plugins marketplace add https://github.com/VasiliyR/tactis-plugins.git#main --sparse zcode` and `zcode plugins install tactis@tactis-ads --scope user`. Its selected root `marketplace.json` must point to `./zcode/plugin`; verify installed `release.json` has `host=zcode`. A plain repository-root add can select the Claude catalog instead. If the native CLI or explicit ZCode catalog selection is unavailable, the installation requires a supported user action.

- Qwen Code: install its explicit Release archive or the `qwen/plugin` directory with `qwen extensions install`. The repository's Claude marketplace entry is not the native Qwen package.
- Claude Cowork: use the plugin-only `tactis-ads-claude-cowork-v1.24.32.zip` Release asset, then connect its bundled MCP through browser OAuth. The root Claude marketplace remains Claude Code. See [Cowork installation](claude-cowork/README.md).
- ChatGPT Work: see [cloud installation](chatgpt/README.md) for personal MCP registration and skills delivery. The `tactis-ads-chatgpt-v1.24.32.zip` asset is a portable submission package; GitHub import alone does not establish a working cloud plugin or a public OpenAI directory listing.

### Skills loaded, MCP tools absent

Check the existing host connection's authentication, enabled/selected state and sanitized startup error before package/update diagnostics. Missing credentials need normal OAuth; a stored token with failed startup needs its actual activation/refresh/transport diagnosis. Every package ships `skills/tactis/references/mcp-connection.md` with concrete host steps. Do not dump tokens or reset auth caches.

Install and update instructions: https://tactis.ru/install.md

The compatible channel is `v1` on `main`. OAuth access is selected separately in your browser. DeepSeek Harness is a preview TGZ attached to a GitHub Release.

Generated output; the source method and host adapters belong to Tactis Platform.

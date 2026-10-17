# Tactis Ads

Generated marketplace for Codex, Claude Code and ZCode, with native Qwen Code and Nessy extensions. Install `tactis@tactis-ads` through your program's native plugin manager using its host instructions.

- Codex: add this Git repository with `--ref main`; its catalog is `.agents/plugins/marketplace.json`.
- Claude Code: add this Git repository with `#main` and the observed scope; its catalog is `.claude-plugin/marketplace.json`.
- ZCode: verify native CLI support, then use `zcode plugins marketplace add https://github.com/VasiliyR/tactis-plugins.git#main --sparse zcode` and `zcode plugins install tactis@tactis-ads --scope user`. Its selected root `marketplace.json` must point to `./zcode/plugin`; verify installed `release.json` has `host=zcode`. A plain repository-root add can select the Claude catalog instead. If the native CLI or explicit ZCode catalog selection is unavailable, the installation requires a supported user action.

- Qwen Code: install its explicit Release archive or the `qwen/plugin` directory with `qwen extensions install`. The repository's Claude marketplace entry is not the native Qwen package.
- Nessy (private Qwen fork): the `nessy/plugin` directory and explicit Release archive contain `nessy-extension.json`. Use the private build's supported native importer; its marketplace and live end-to-end behavior require host verification.

### Qwen / Nessy compatibility

Both packages contain byte-identical shared skills. Nessy builds that accept `qwen-extension.json` and preserve its declared context, skills, HTTP MCP/OAuth and identity headers can use the Qwen archive unchanged. That cross-host installation has not been verified against the private Nessy build. Keep `host=qwen` and its digest when using the Qwen archive; use the dedicated Nessy archive when the fork requires `nessy-extension.json`. See [Qwen](qwen/README.md) and [Nessy](nessy/README.md) for details.

Install and update instructions: https://tactis.ru/install.md

The compatible channel is `v1` on `main`. OAuth access is selected separately in your browser. DeepSeek Harness is a preview TGZ attached to a GitHub Release.

Generated output; the source method and host adapters belong to Tactis Platform.

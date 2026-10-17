# Tactis Ads

This extension targets Nessy, the user's private Qwen fork. It supplies the canonical Tactis marketing skills and the `tactis_ads` remote MCP server with `host=nessy`.

For a marketing task, read the matching local `skills/<skill>/SKILL.md` and its referenced resources. For mixed work or continuation, start with `skills/tactis/SKILL.md`. The complete inventory is in `methodology.json`. Use the current MCP schemas and select an accessible project through browser OAuth. Installation does not authorize advertising changes, spending, publishing or changes to access.

Use Nessy's supported native extension import for `nessy-extension.json`. Preserve existing extensions, settings, host permissions and OAuth credentials. Do not replace global skills or manually rewrite unrelated MCP configuration. If this private build cannot load the declared manifest or native OAuth, report its exact version and missing capability instead of substituting another host identity. After native activation, verify the skill inventory, `get_plugin_update_status`, `list_projects` and a read-only `get_project_brief` for the selected project.

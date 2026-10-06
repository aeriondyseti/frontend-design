# frontend-design

Design skills, browser automation, and UI auditing for frontend development in Claude Code.

## Install

```bash
/plugin marketplace add AerionDyseti/aeriondyseti-plugins
/plugin install frontend-design@aeriondyseti-plugins
```

## Skills

| Skill | Triggers On |
|-------|-------------|
| **Frontend Design** | "build a landing page", "create a component", creative/marketing UI tasks |
| **Interface Design** | "build a dashboard", "design an admin panel", SaaS/tool/data interface tasks |
| **Playwright** | "test my website", "take a screenshot", browser automation tasks |
| **Web Design Guidelines** | "review my UI", "check accessibility", "audit design" |

## Commands

| Command | Description |
|---------|-------------|
| `/init` | Overview of the plugin — all skills, commands, and design system workflow |
| `/design:status` | Show current design system state from `.frontend-design/system.md` |
| `/design:audit` | Check code against design system patterns + web interface guidelines |
| `/design:extract` | Scan existing code and generate a `.frontend-design/system.md` |
| `/design:critique` | Self-critique the UI just built, then rebuild what defaulted |

## MCP Server (auto-loaded)

The [@playwright/mcp](https://github.com/microsoft/playwright-mcp) server provides 25+ browser control tools (navigate, click, fill, snapshot, etc.) accessible directly as MCP tools.

## Design System

Uses `.frontend-design/system.md` in your project to persist design decisions (style identity, visual language with exact CSS values, rules/constraints, tokens, component patterns, and decision rationale) across sessions.

## Releasing

Always release with [plugin-kit](https://github.com/aeriondyseti/plugin-kit)'s `release` command. It bumps the version, tags the release, and pins this plugin's entry in the [aeriondyseti-plugins](https://github.com/aeriondyseti/aeriondyseti-plugins) marketplace to that exact tag and commit in one step, so the published plugin never drifts from this repo. Don't bump versions, create tags, or edit the marketplace entry by hand.

1. Add your changes under `## [Unreleased]` in `CHANGELOG.md` and commit them. `release` refuses to run with an empty `[Unreleased]` section or a dirty tree.
2. Optionally run `npx @aeriondyseti/plugin-kit doctor` to catch anything that would break the plugin once installed.
3. From this repo, with the marketplace repo cloned alongside it (adjust the path if yours lives elsewhere), preview and then release:

   ```bash
   npx @aeriondyseti/plugin-kit release patch --plugin . --marketplace ../aeriondyseti-plugins/.claude-plugin/marketplace.json --dry-run
   npx @aeriondyseti/plugin-kit release patch --plugin . --marketplace ../aeriondyseti-plugins/.claude-plugin/marketplace.json
   ```

   Use `patch`, `minor`, `major`, or an explicit `x.y.z`. This bumps `.claude-plugin/plugin.json`, moves `[Unreleased]` under the new version in `CHANGELOG.md`, commits `Release x.y.z`, tags `vx.y.z`, and updates `ref`, `sha`, and `version` in the marketplace entry. It never pushes.
4. Push this repo first: `git push origin main --follow-tags`.
5. Then commit and push the marketplace change. Pushing it first would pin a commit GitHub doesn't have yet, and installs would fail.

## License

MIT

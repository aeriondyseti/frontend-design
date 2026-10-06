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

## License

MIT

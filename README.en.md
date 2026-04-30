# Claude Code Plugins by jeongph

[한국어](README.md)

A plugin directory for Claude Code.

> **Note:** Please review each plugin's repository before installing. MCP servers, files, and other software included in each plugin are managed in their respective repositories. See each plugin's homepage for details.

## Installation

**1. Add the marketplace** (one-time)

```
/plugin marketplace add jeongph/claude-plugins
```

**2. Install a plugin**

```
/plugin install <plugin-name>@jeongph-claude-plugins
```

Or browse via `/plugin > Discover`.

## Available Plugins

| Plugin | Description | Category |
|--------|-------------|----------|
| [why-is-my-claude-dumb](#why-is-my-claude-dumb) | Environment analysis and plugin recommendations | productivity |
| [claude-telemetry](#claude-telemetry) | Real-time session telemetry status line | productivity |
| [claude-intent](#claude-intent) | Records work cycle intent, alternatives, and trade-offs | productivity |
| [pdf-scan-audit](#pdf-scan-audit) | Scan PDF quality audit (Korean docs) | utility |
| [pdf-toolkit](#pdf-toolkit) | General-purpose PDF manipulation toolkit (Korean docs) | utility |

---

### why-is-my-claude-dumb

> Why is my Claude so dumb? Let's find out.

Analyzes your local environment (OS, languages, plugins, MCP servers, project context) and recommends missing plugins from the official marketplace.

[View repo →](https://github.com/jeongph/why-is-my-claude-dumb)

---

### claude-telemetry

> Customizable multi-line status line for Claude Code.

Displays remaining context, rate limits, git status, session time, and token usage in a compact color-coded status line. Auto-detects OAuth vs. API key users.

[View repo →](https://github.com/jeongph/claude-telemetry)

---

### claude-intent

> Code is the shadow of intent.

Records the intent, alternatives, and trade-offs of each work cycle in `docs/intent/` so you can later trace the "why" behind code.

[View repo →](https://github.com/jeongph/claude-intent)

---

### pdf-scan-audit

> Detects missing/misordered/rotated/cropped pages in scanned PDF books.

Audits scanned PDF book quality beyond surface metadata — checks rotation suspects, page-number continuity, and image cropping, then visually re-verifies suspect pages. **Korean-first documentation.**

[View repo →](https://github.com/jeongph/pdf-scan-audit)

---

### pdf-toolkit

> General-purpose PDF manipulation — rotate, delete, reorder, extract pages; merge or split PDFs; edit metadata.

PyMuPDF-based non-destructive PDF toolkit. Invoke via natural language or slash commands; originals are always preserved. **Korean-first documentation.**

[View repo →](https://github.com/jeongph/pdf-toolkit)

## Plugin Structure

Each plugin follows this standard structure:

```
plugin-name/
├── .claude-plugin/
│   └── plugin.json      # Plugin metadata (required)
├── .mcp.json            # MCP server configuration (optional)
├── commands/            # Slash commands (optional)
├── agents/              # Agent definitions (optional)
├── skills/              # Skill definitions (optional)
└── README.md            # Documentation
```

## Documentation

For more information on developing Claude Code plugins, see the [official documentation](https://code.claude.com/docs/en/plugins).

## License

Please see each plugin's repository for the relevant license.

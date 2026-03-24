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

---

### why-is-my-claude-dumb

> Why is my Claude so dumb? Let's find out.

Analyzes your local environment — OS, languages, installed plugins, MCP servers, project context — and recommends official marketplace plugins tailored to your workflow.

```
/plugin install why-is-my-claude-dumb@jeongph-claude-plugins
```

#### Features

- **Environment analysis** — scans OS, installed runtimes, Claude Code settings, and MCP servers
- **Tailored recommendations** — finds missing plugins from the official catalog (80+ plugins)
- **Auto-trigger** — `dumb-doctor` agent automatically offers an environment check when you express frustration with Claude
- **One-click install** — install recommended plugins directly from the conversation

#### What gets analyzed

| Category | Details |
|----------|---------|
| System | OS, platform, architecture |
| Languages | Node, Python, Java, Go, Rust, and other installed runtimes |
| Plugins | Installed plugins vs. official catalog |
| Config | Claude Code settings, hooks, permissions |
| Integrations | Connected MCP servers |
| Project | Project type, CLAUDE.md presence |

[View repo →](https://github.com/jeongph/why-is-my-claude-dumb)

---

### claude-telemetry

> Customizable multi-line status line for Claude Code.

Displays remaining context window, rate limits, git status, session duration, token usage, and more — all in a compact, color-coded status line. Auto-detects OAuth vs. API key users.

```
/plugin install claude-telemetry@jeongph-claude-plugins
```

#### Features

- **Remaining % display** — all bars show remaining capacity (like a battery), not usage
- **Auto user detection** — OAuth users see rate limits, API key users see cost
- **Git integration** — branch, push/pull, changes, stash, worktrees
- **Color coding** — auto transitions green → yellow → red based on remaining capacity
- **Adaptive width** — auto-adjusts to terminal width
- **i18n** — English, Korean, Japanese, Chinese (auto-detected)

#### Sections

| Line | Content |
|------|---------|
| 1 | Model, elapsed time, git (branch, push/pull, changes, stash, worktrees) |
| 2 | Context remaining %, rate limit countdown, cost, lines changed |
| 3 | Active agent, vim mode (shown only when data is available) |

[View repo →](https://github.com/jeongph/claude-telemetry)

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

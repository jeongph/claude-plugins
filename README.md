# jeongph/claude-plugins

A unified marketplace for Claude Code plugins by [@jeongph](https://github.com/jeongph).

One marketplace, all plugins. Add once, install any.

## Quick Start

**1. Add the marketplace**

```
/plugin marketplace add jeongph/claude-plugins
```

**2. Browse and install**

```
/plugin install <plugin-name>@jeongph-claude-plugins
```

That's it. No per-plugin marketplace setup needed.

## Available Plugins

### why-is-my-claude-dumb

> Your Claude Code might be missing plugins that could make it significantly smarter.

Analyzes your local environment — OS, languages, installed plugins, MCP servers, project context — and recommends official marketplace plugins tailored to your workflow. When you express frustration, it even triggers automatically.

```
/plugin install why-is-my-claude-dumb@jeongph-claude-plugins
```

**Usage:**

```
/why-is-my-claude-dumb:why-dumb
```

| What it checks | Details |
|----------------|---------|
| System | OS, platform, architecture |
| Languages | Node, Python, Java, Go, Rust, and more |
| Plugins | Installed vs. available in the official catalog |
| Config | Claude Code settings, hooks, permissions |
| Integrations | Connected MCP servers |
| Project | Project type, CLAUDE.md presence |

[View repo →](https://github.com/jeongph/why-is-my-claude-dumb)

---

### claude-telemetry

> Customizable multi-line status line for Claude Code — real-time session telemetry in your terminal.

Displays remaining context window, rate limits, git status, session duration, token usage, and more — all in a compact, color-coded status line. Auto-detects OAuth vs. API key users.

```
/plugin install claude-telemetry@jeongph-claude-plugins
```

**Usage:**

```
/claude-telemetry:setup
```

| Line | Sections |
|------|----------|
| 1 | Model, elapsed time, git (branch, push/pull, changes, stash, worktrees) |
| 2 | Context remaining %, rate limits with countdown, cost, lines changed |
| 3 | Active agent, vim mode |

[View repo →](https://github.com/jeongph/claude-telemetry)

## Why a Unified Marketplace?

Claude Code plugins are installed from marketplaces. Without this repo, each plugin needs its own marketplace registration:

```
# Without unified marketplace (per-plugin setup)
/plugin marketplace add jeongph/why-is-my-claude-dumb
/plugin marketplace add jeongph/claude-telemetry
/plugin install why-is-my-claude-dumb@jeongph-why-is-my-claude-dumb
/plugin install claude-telemetry@jeongph-claude-telemetry
```

```
# With unified marketplace (one-time setup)
/plugin marketplace add jeongph/claude-plugins
/plugin install why-is-my-claude-dumb@jeongph-claude-plugins
/plugin install claude-telemetry@jeongph-claude-plugins
```

Add the marketplace once. Install any plugin from it.

## License

[MIT](LICENSE)

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

Click a plugin name to open its repository. Installation, usage, and full documentation live in each repository's README.

| Plugin | Description | Category |
|--------|-------------|----------|
| [claude-intent](https://github.com/jeongph/claude-intent) | Code is the shadow of intent — records each work cycle's intent, alternatives, and trade-offs in `docs/intent/` so you can trace the "why" | productivity |
| [claude-mbti](https://github.com/jeongph/claude-mbti) | Give Claude a personality 🎭 — injects one of 16 MBTI types (tone + behavior), toggled with `/mbti` | fun |
| [claude-okf](https://github.com/jeongph/claude-okf) | Code remembers what; the wiki remembers why — OKF-based LLM-wiki with node drafting, auto-validation, lint, and grounded answers | productivity |
| [claude-telemetry](https://github.com/jeongph/claude-telemetry) | Remaining context, rate limits, effort level, git status, and token usage in a compact color-coded status line | productivity |
| [claude-tidy](https://github.com/jeongph/claude-tidy) | When the context is gone, so is the memory of what you missed — end-of-session cleanup checks (commits, history, docs, issues, forgotten tasks) and handoff | productivity |
| [git-flow](https://github.com/jeongph/git-flow) | Mistakes happen when you finish a branch, not when you create one — automates Git Flow over pull requests and blocks violations | productivity |
| [pdf-scan-audit](https://github.com/jeongph/pdf-scan-audit) | Detects missing pages, ordering, rotation, cropping, and resolution defects in scanned PDFs (Korean docs) | utility |
| [pdf-toolkit](https://github.com/jeongph/pdf-toolkit) | General-purpose PDF toolkit — rotate, delete, reorder, extract, merge, split, and edit metadata, non-destructively (Korean docs) | utility |
| [why-is-my-claude-dumb](https://github.com/jeongph/why-is-my-claude-dumb) | Why is my Claude so dumb? Let's find out — analyzes your environment and recommends missing official-marketplace plugins | productivity |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for what to update when adding or changing a plugin.

## License

Each plugin's license is listed in its own repository.

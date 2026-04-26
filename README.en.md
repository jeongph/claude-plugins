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
| [pdf-scan-audit](#pdf-scan-audit) | Scan PDF quality audit (Korean docs) | utility |
| [pdf-toolkit](#pdf-toolkit) | General-purpose PDF manipulation toolkit (Korean docs) | utility |

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

---

### pdf-scan-audit

> Detects missing/misordered/rotated/cropped pages in scanned PDF books.

Audits scanned PDF books beyond surface metadata — checks rotation suspects, page-number continuity, and image cropping, then visually re-verifies suspect pages and reports a readable table. **Korean-first documentation; UI prompts also in Korean.**

```
/plugin install pdf-scan-audit@jeongph-claude-plugins
```

#### Features

- **Page metadata audit** — size distribution, rotation, orientation, DPI consistency
- **Blank/cropped detection** — pages without text+image, images extending past page boundaries
- **Rotation suspects** — flags pages by text-line aspect ratio; visually verified
- **Page-number continuity** — extracts header/footer sequences, auto-classifies OCR misreads vs. real gaps
- **Auto offset estimation** — detects PDF↔book page offset
- **Clean by default** — temp directory auto-removed; nothing left in your working directory

#### Audit checks

| Check | Detail |
|-------|--------|
| Page metadata | Size distribution, rotation, portrait/landscape orientation |
| DPI | Estimated per-page DPI based on largest embedded image |
| Blank pages | Pages with neither text nor image |
| Rotation suspects | Estimated by text-line aspect ratio + visual verification |
| Page-number continuity | Header/footer sequence gap analysis with OCR misread classification |
| Visual re-verification | Suspect pages extracted to PNG and reviewed by Claude |

#### Usage

```
Audit this scanned PDF for me
/audit-pdf book1.pdf book2.pdf
```

Korean prompts also work: `이 PDF 스캔 검사해줘`

#### Dependencies

- Python 3.8+
- PyMuPDF (`pip install pymupdf`)

[View repo →](https://github.com/jeongph/pdf-scan-audit)

---

### pdf-toolkit

> General-purpose PDF manipulation — rotate, delete, reorder, extract pages; merge or split PDFs; edit metadata.

PyMuPDF-based toolkit covering ~90% of common PDF operations. Invoke via natural language or slash commands. **Originals are always preserved** by default. **Korean-first documentation; UI prompts also in Korean.**

```
/plugin install pdf-toolkit@jeongph-claude-plugins
```

#### Features

- **Page operations** — rotate, delete, reorder, extract (single/range/all)
- **Document operations** — merge multiple PDFs, split by page ranges
- **Metadata editing** — title, author, subject, keywords, creator
- **Non-destructive by default** — output goes to new file; `--in-place` is explicit
- **Natural language and slash** — `이 PDF 54페이지 회전시켜줘` or `/pdf-rotate`

#### Slash commands

| Command | Operation |
|---------|-----------|
| `/pdf-rotate` | Rotate pages |
| `/pdf-delete` | Delete pages |
| `/pdf-reorder` | Reorder or swap pages |
| `/pdf-extract` | Extract pages into new PDF |
| `/pdf-merge` | Merge multiple PDFs |
| `/pdf-split` | Split by page ranges |
| `/pdf-meta` | Show or edit metadata |

#### Pairs with pdf-scan-audit

```
1. /audit-pdf book.pdf       → "p.54, p.98 rotation suspect"
2. /pdf-rotate book.pdf 54,98 180
3. /audit-pdf book.fixed.pdf → confirm fix
```

#### Dependencies

- Python 3.8+
- PyMuPDF (`pip install pymupdf`)

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

# Claude Code Plugins by jeongph

[한국어](README.md)

Claude Code plugins I build and use.

Each repository below describes what the plugin does, how to install it, and which tools it needs.

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
| [agentic-devflow](https://github.com/jeongph/agentic-devflow) | Works from a GitHub issue through implementation, review, and PR creation. Can resume interrupted work. | productivity |
| [claude-intent](https://github.com/jeongph/claude-intent) | Records why code was written a certain way and which alternatives were considered, so you can look them up later. | productivity |
| [claude-mbti](https://github.com/jeongph/claude-mbti) | Sets Claude’s tone and behavior to one of 16 MBTI types. | fun |
| [claude-telemetry](https://github.com/jeongph/claude-telemetry) | Shows remaining context and usage limits, effort level, Git status, and token counts at the bottom of the terminal. | productivity |
| [claude-tidy](https://github.com/jeongph/claude-tidy) | Checks for missed commits, docs, and issue updates, then prepares notes for the next session. | productivity |
| [claude-wiki](https://github.com/jeongph/claude-wiki) | Builds a wiki from code and documents, checks its contents, and finds answers in the wiki. | productivity |
| [git-flow](https://github.com/jeongph/git-flow) | Creates branches and merges through PRs using Git Flow. Checks for incorrect branching and tagging. | productivity |
| [pdf-scan-audit](https://github.com/jeongph/pdf-scan-audit) | Checks scanned PDFs for missing pages, incorrect order or rotation, cropping, and resolution issues. Korean documentation. | utility |
| [pdf-toolkit](https://github.com/jeongph/pdf-toolkit) | Rotates or deletes PDF pages, and merges or splits documents. Keeps the original files by default. Korean documentation. | utility |
| [why-is-my-claude-dumb](https://github.com/jeongph/why-is-my-claude-dumb) | Checks your development environment and installed tools, then suggests official marketplace plugins that may help with your work. | productivity |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for what to update when adding or changing a plugin.

## License

Each plugin's license is listed in its own repository.

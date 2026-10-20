# mvnpm Claude Code Plugin

A [Claude Code](https://claude.ai/code) plugin that connects to [mvnpm.org](https://mvnpm.org) — a Maven repository facade for NPM packages. It lets Claude search, convert, and manage NPM packages as Maven/Gradle dependencies.

## Installation

### From the marketplace

```
/plugin marketplace add mvnpm/mvnpm-claude-plugin
/plugin install mvnpm@mvnpm-marketplace
```

### Manual MCP setup (without the plugin)

```bash
claude mcp add --transport http mvnpm https://mvnpm.org/mcp
```

## What it does

This plugin gives Claude access to mvnpm tools so it can:

- **Search** NPM packages available as Maven artifacts
- **Convert** NPM package names to Maven/Gradle dependency snippets
- **Generate** POM files and ES module import maps
- **Browse** artifact contents (JAR/TGZ files)
- **Check** Maven Central sync status
- **Monitor** the sync pipeline and event logs

## Example prompts

- "Add the lit web component library to my pom.xml"
- "What's the Maven coordinate for @hotwired/stimulus?"
- "Is htmx synced to Maven Central?"
- "Generate an import map for lit and @vaadin/router"

## NPM to Maven name mapping

| NPM | Maven |
|-----|-------|
| `lit` | `org.mvnpm:lit` |
| `@hotwired/stimulus` | `org.mvnpm.at.hotwired:stimulus` |
| `@vaadin/router` | `org.mvnpm.at.vaadin:router` |

## More info

- [mvnpm.org](https://mvnpm.org)
- [AI Agent setup guide](https://mvnpm.org/ai-agent/)
- [GitHub](https://github.com/mvnpm/mvnpm)

## License

Apache-2.0

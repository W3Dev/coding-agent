# W3Dev Coding Agent - Claude Code Plugin Marketplace

A curated Claude Code plugin marketplace providing essential development tools with MCP servers for documentation lookup and code search, plus LSP support for Go and TypeScript.

## Installation

### Add Marketplace

```bash
/plugin marketplace add w3dev/coding-agent
```

### Install Plugins

```bash
# Basic development tools
/plugin install basic-development-plugin@w3dev

# Next.js development toolkit
/plugin install nextjs-devtools-plugin@w3dev
```

## Included Plugins

### 1. basic-development-plugin

Essential development tools for any project:

#### MCP Servers
| Server | Description |
|--------|-------------|
| **deepwiki** | Ask questions about any GitHub repository |
| **context7** | Query up-to-date documentation for any library |
| **exa** | Web search and code context retrieval |
| **grep** | Search real-world code examples from public GitHub repos |

#### LSP Support
| Language | Server | Extensions |
|----------|--------|------------|
| **TypeScript/JavaScript** | `typescript-language-server` | `.ts`, `.tsx`, `.js`, `.jsx` |
| **Go** | `gopls` | `.go`, `.mod`, `.work` |

#### Commands
| Command | Description |
|---------|-------------|
| `/docs` | Look up library documentation using Context7 |
| `/search-code` | Find real-world code examples from GitHub |

#### Skills
| Skill | Description |
|-------|-------------|
| `docs-lookup` | Intelligent documentation and example lookup |

---

### 2. nextjs-devtools-plugin

Complete Next.js development toolkit with everything you need:

#### MCP Servers
| Server | Description |
|--------|-------------|
| **next-devtools** | Official Vercel MCP for Next.js development |
| **deepwiki** | Ask questions about any GitHub repository |
| **context7** | Query up-to-date documentation for any library |
| **grep** | Search real-world code examples from public GitHub repos |

#### LSP Support
| Language | Server | Extensions |
|----------|--------|------------|
| **TypeScript/JavaScript** | `typescript-language-server` | `.ts`, `.tsx`, `.js`, `.jsx` |

#### Capabilities
- Real-time build, runtime, and TypeScript error detection
- Live application state queries
- Page routes and metadata inspection
- Server Actions debugging
- Automatic codemod upgrades
- Documentation lookup via Context7
- Code search via Grep

#### Commands
| Command | Description |
|---------|-------------|
| `/nextjs-errors` | Check build and runtime errors |
| `/nextjs-routes` | Inspect application routes |
| `/nextjs-upgrade` | Upgrade Next.js version |

#### Skills
| Skill | Description |
|-------|-------------|
| `nextjs-debug` | Debug Next.js applications |

#### Requirements
- Node.js v20.19 or newer
- Next.js 16+ with dev server running

## Project Structure

```
w3dev-agent/
├── .claude-plugin/
│   └── marketplace.json        # Marketplace registry
├── plugins/
│   ├── basic-development/      # Basic development plugin
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── commands/
│   │   ├── skills/
│   │   ├── .mcp.json
│   │   ├── .lsp.json
│   │   └── README.md
│   └── nextjs-devtools/        # Next.js devtools plugin
│       ├── .claude-plugin/
│       │   └── plugin.json
│       ├── commands/
│       ├── skills/
│       ├── .mcp.json
│       ├── .lsp.json
│       └── README.md
└── README.md
```

## Requirements

### For basic-development-plugin

**TypeScript/JavaScript LSP:**
```bash
npm install -g typescript-language-server typescript
```

**Go LSP:**
```bash
go install golang.org/x/tools/gopls@latest
```

### For nextjs-devtools-plugin

**TypeScript LSP:**
```bash
npm install -g typescript-language-server typescript
```

**Next.js Requirements:**
- Node.js v20.19 or newer
- Next.js 16+ with dev server running

## Usage Examples

### Look up documentation
```
/docs react useState hook
/docs next.js server components
```

### Search for code patterns
```
/search-code "useEffect(" --lang=TypeScript
/search-code "http.HandleFunc" --lang=Go
```

### Debug Next.js application
```
/nextjs-errors          # Check for build/runtime errors
/nextjs-routes          # List all routes
/nextjs-upgrade         # Upgrade to latest Next.js
```

## Contributing

1. Fork the repository
2. Add your plugin to the `plugins/` directory
3. Update `.claude-plugin/marketplace.json` to include your plugin
4. Submit a pull request

## License

MIT

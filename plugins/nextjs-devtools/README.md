# Next.js DevTools Plugin

A complete Claude Code plugin for Next.js development with real-time error detection, live state queries, route inspection, documentation lookup, and TypeScript LSP support.

## Features

### MCP Servers
| Server | Description |
|--------|-------------|
| **next-devtools** | Official Vercel MCP for Next.js development |
| **deepwiki** | Ask questions about any GitHub repository |
| **context7** | Query up-to-date documentation for any library |
| **grep** | Search real-world code examples from public GitHub repos |

### LSP Support
| Language | Server | Extensions |
|----------|--------|------------|
| **TypeScript/JavaScript** | `typescript-language-server` | `.ts`, `.tsx`, `.js`, `.jsx` |

### Capabilities
- Real-time build, runtime, and TypeScript error detection
- Live application state queries
- Page routes and metadata inspection
- Server Actions debugging
- Automatic codemod upgrades
- Documentation lookup via Context7
- Code search via Grep

### Commands
| Command | Description |
|---------|-------------|
| `/nextjs-errors` | Check build and runtime errors |
| `/nextjs-routes` | Inspect application routes |
| `/nextjs-upgrade` | Upgrade Next.js version |

### Skills
| Skill | Description |
|-------|-------------|
| `nextjs-debug` | Debug Next.js applications |

## Requirements

- Node.js v20.19 or newer
- Next.js 16+ with dev server running
- TypeScript language server (`npm install -g typescript-language-server typescript`)

## Installation

```bash
/plugin install nextjs-devtools-plugin@w3dev
```

## Usage

Start your Next.js dev server, then use the commands:

```
/nextjs-errors          # Check for errors
/nextjs-routes          # List all routes
/nextjs-upgrade         # Upgrade Next.js
```

## License

MIT

# Basic Development Plugin

Essential development tools with MCP servers for documentation lookup and code search, plus LSP support for Go and TypeScript.

## Features

### MCP Servers
| Server | Description |
|--------|-------------|
| **deepwiki** | Ask questions about any GitHub repository |
| **context7** | Query up-to-date documentation for any library |
| **exa** | Web search and code context retrieval |
| **grep** | Search real-world code examples from public GitHub repos |

### LSP Support
| Language | Server | Extensions |
|----------|--------|------------|
| **TypeScript/JavaScript** | `typescript-language-server` | `.ts`, `.tsx`, `.js`, `.jsx` |
| **Go** | `gopls` | `.go`, `.mod`, `.work` |

### Commands
| Command | Description |
|---------|-------------|
| `/docs` | Look up library documentation using Context7 |
| `/search-code` | Find real-world code examples from GitHub |

### Skills
| Skill | Description |
|-------|-------------|
| `docs-lookup` | Intelligent documentation and example lookup |

## Installation

```bash
/plugin install basic-development-plugin@w3dev
```

## Requirements

**TypeScript/JavaScript:**
```bash
npm install -g typescript-language-server typescript
```

**Go:**
```bash
go install golang.org/x/tools/gopls@latest
```

## Usage

### Look up documentation
```
/docs react useState hook
/docs express middleware
```

### Search for code patterns
```
/search-code "useEffect(" --lang=TypeScript
/search-code "http.HandleFunc" --lang=Go
```

## License

MIT

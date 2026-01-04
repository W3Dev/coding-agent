# Basic Development Plugin

A Claude Code plugin that provides essential development tools including MCP servers for documentation lookup and code search, plus LSP support for Go and TypeScript.

## Features

### MCP Servers
- **deepwiki** - Ask questions about GitHub repositories
- **context7** - Query up-to-date documentation for any library
- **exa** - Web search and code context retrieval
- **grep** - Search real-world code examples from public GitHub repositories

### LSP Support
- **Go** - via `gopls`
- **TypeScript/JavaScript** - via `typescript-language-server`

## Installation


### From GitHub
```bash
claude /plugin add github:w3dev/coding-agent
```

## Requirements

### For LSP Support
Ensure the following language servers are installed:

**Go:**
```bash
go install golang.org/x/tools/gopls@latest
```

**TypeScript:**
```bash
npm install -g typescript-language-server typescript
```

## Structure

```
w3dev-agent/
├── .claude-plugin/
│   └── plugin.json      # Plugin manifest
├── .mcp.json            # MCP server configuration
├── .lsp.json            # LSP server configuration
├── .gitignore
└── README.md
```

## Configuration

### MCP Servers (.mcp.json)
The plugin connects to the following HTTP-based MCP servers:
- `https://mcp.deepwiki.com/mcp`
- `https://mcp.context7.com/mcp`
- `https://mcp.exa.ai/mcp`
- `https://mcp.grep.app`

### LSP Servers (.lsp.json)
Language servers are configured for:
- Go files (`.go`)
- TypeScript files (`.ts`, `.tsx`)
- JavaScript files (`.js`, `.jsx`)

## License

MIT

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

W3Dev Coding Agent is a Claude Code Plugin Marketplace - a curated collection of development plugins providing MCP (Model Context Protocol) servers and LSP (Language Server Protocol) support for various frameworks: Next.js, Expo/React Native, Flutter, and general development tools.

## Repository Structure

```
w3dev-agent/
├── .claude-plugin/marketplace.json   # Central plugin registry
├── plugins/
│   ├── basic-development/            # Core dev tools (docs, code search)
│   ├── nextjs-devtools/              # Next.js debugging & upgrades
│   ├── expo-devtools/                # Expo/React Native visual testing
│   └── flutter-devtools/             # Flutter/Dart analysis & testing
```

## Plugin Architecture

Each plugin follows this structure:
```
plugin-name/
├── .claude-plugin/plugin.json        # Metadata, links to MCP/LSP configs
├── .mcp.json                         # MCP server definitions
├── .lsp.json                         # Language server configs
├── README.md                         # Plugin documentation
├── commands/                         # Command definitions (*.md files)
└── skills/                           # Skill workflows (*/SKILL.md files)
```

## Adding a New Plugin

1. Create plugin directory under `plugins/`
2. Add `.claude-plugin/plugin.json` with metadata:
   ```json
   {
     "name": "plugin-name",
     "description": "...",
     "version": "1.0.0",
     "mcpServers": "${CLAUDE_PLUGIN_ROOT}/.mcp.json",
     "lspServers": "${CLAUDE_PLUGIN_ROOT}/.lsp.json"
   }
   ```
3. Define `.mcp.json` (HTTP endpoints or command-based servers)
4. Define `.lsp.json` with language server configs
5. Add commands in `commands/command-name.md`
6. Add skills in `skills/skill-name/SKILL.md`
7. Register in `.claude-plugin/marketplace.json`

## MCP Server Patterns

**HTTP-based** (remote services):
```json
{
  "server-name": {
    "type": "http",
    "url": "https://mcp.example.com/sse"
  }
}
```

**Command-based** (local processes):
```json
{
  "server-name": {
    "type": "command",
    "command": "npx",
    "args": ["-y", "@example/mcp-server"]
  }
}
```

## Shared MCP Services

All plugins share these common services:
- `deepwiki` - GitHub repository Q&A
- `context7` - Library documentation lookup
- `grep` - Public GitHub code search
- `exa` - Web search (basic-development only)

## LSP Configuration

LSP servers are defined with root patterns for automatic workspace detection:
- TypeScript/JS: `tsconfig.json`, `jsconfig.json`, `package.json`
- Go: `go.mod`, `go.work`
- Dart: `pubspec.yaml`, `analysis_options.yaml`
- Next.js: adds `next.config.js`, `next.config.ts`

## Command Definition Format

Commands are markdown files in `commands/` with:
- YAML frontmatter (name, description, arguments)
- Usage instructions
- Example invocations

## Skill Definition Format

Skills are `SKILL.md` files containing:
- When to Use - trigger scenarios
- Instructions - step-by-step workflow
- Available MCP Tools - tool references
- Example Workflows - usage patterns

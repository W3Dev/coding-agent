# Claude Plugin Builder Skill

Use this skill when you need to create, modify, or understand Claude Code plugins and marketplaces. This is a comprehensive reference for plugin architecture, configuration patterns, and best practices.

## When to Use

- User wants to create a new Claude Code plugin
- User wants to add a plugin to a marketplace
- User asks about plugin structure or configuration
- User needs to add MCP servers, LSP servers, commands, or skills
- User wants to understand how plugins work
- User is debugging plugin configuration issues

## Plugin Architecture Overview

### Directory Structure

A Claude Code plugin marketplace follows this structure:

```
marketplace-root/
├── .claude-plugin/
│   └── marketplace.json        # Marketplace registry (lists all plugins)
├── plugins/
│   └── my-plugin/              # Individual plugin
│       ├── .claude-plugin/
│       │   └── plugin.json     # Plugin manifest
│       ├── commands/           # Slash commands (*.md files)
│       ├── skills/             # Agent skills (subdirs with SKILL.md)
│       ├── agents/             # Subagent definitions (*.md files)
│       ├── hooks/              # Event hooks (hooks.json)
│       ├── .mcp.json           # MCP server configuration
│       ├── .lsp.json           # LSP server configuration
│       └── README.md           # Plugin documentation
├── skills/                     # Marketplace-level skills (optional)
└── README.md                   # Marketplace documentation
```

### Key Rules

1. **Manifest Location**: `plugin.json` MUST be in `.claude-plugin/` directory
2. **Component Directories**: `commands/`, `skills/`, `agents/`, `hooks/` stay at plugin root (NOT inside `.claude-plugin/`)
3. **Naming Convention**: Use kebab-case for all names (plugin-name, command-name)
4. **Portable Paths**: Use `${CLAUDE_PLUGIN_ROOT}` for intra-plugin references

---

## Configuration Files

### 1. marketplace.json

**Location**: `.claude-plugin/marketplace.json`

```json
{
    "name": "my-marketplace",
    "owner": {
        "name": "Your Name",
        "email": "you@example.com"
    },
    "metadata": {
        "description": "Description of your marketplace",
        "version": "1.0.0",
        "homepage": "https://github.com/you/repo",
        "keywords": ["keyword1", "keyword2"]
    },
    "plugins": [
        {
            "name": "my-plugin",
            "source": "./plugins/my-plugin",
            "description": "Brief description of the plugin"
        }
    ]
}
```

**Key Fields**:
- `name`: Marketplace identifier (used in `@marketplace-name` syntax)
- `source`: Relative path to plugin directory
- `plugins`: Array of all available plugins

---

### 2. plugin.json

**Location**: `plugins/my-plugin/.claude-plugin/plugin.json`

```json
{
    "name": "my-plugin",
    "description": "What the plugin does",
    "version": "1.0.0",
    "author": {
        "name": "Your Name",
        "email": "you@example.com"
    },
    "license": "MIT",
    "homepage": "https://github.com/you/repo",
    "repository": {
        "type": "git",
        "url": "https://github.com/you/repo.git"
    },
    "keywords": ["keyword1", "keyword2"],
    "mcpServers": "${CLAUDE_PLUGIN_ROOT}/.mcp.json",
    "lspServers": "${CLAUDE_PLUGIN_ROOT}/.lsp.json",
    "requires": {
        "node": ">=18.0.0"
    }
}
```

**Key Fields**:
- `name`: Plugin identifier (kebab-case, typically ends with `-plugin`)
- `mcpServers`: Path to MCP configuration (use `${CLAUDE_PLUGIN_ROOT}`)
- `lspServers`: Path to LSP configuration (use `${CLAUDE_PLUGIN_ROOT}`)
- `requires`: Runtime requirements (node, dart, etc.)

---

### 3. .mcp.json (MCP Server Configuration)

**Location**: `plugins/my-plugin/.mcp.json`

Two types of MCP servers:

#### HTTP Remote Servers
```json
{
    "mcpServers": {
        "server-name": {
            "type": "http",
            "url": "https://mcp.example.com/mcp"
        }
    }
}
```

#### Command-based Local Servers
```json
{
    "mcpServers": {
        "server-name": {
            "command": "npx",
            "args": ["-y", "package-name@latest"]
        }
    }
}
```

**Common MCP Servers**:
| Server | Type | URL/Command |
|--------|------|-------------|
| deepwiki | HTTP | `https://mcp.deepwiki.com/mcp` |
| context7 | HTTP | `https://mcp.context7.com/mcp` |
| exa | HTTP | `https://mcp.exa.ai/mcp` |
| grep | HTTP | `https://mcp.grep.app` |
| expo-mcp | HTTP | `https://mcp.expo.dev/mcp` |
| next-devtools | Command | `npx -y next-devtools-mcp@latest` |
| dart | Command | `dart mcp-server` |

---

### 4. .lsp.json (LSP Server Configuration)

**Location**: `plugins/my-plugin/.lsp.json`

```json
{
    "servers": {
        "language-name": {
            "command": ["executable", "--flags"],
            "filetypes": ["filetype1", "filetype2"],
            "extensions": [".ext1", ".ext2"],
            "rootPatterns": ["config-file.json"],
            "initializationOptions": {
                "preference": "value"
            }
        }
    }
}
```

**Common LSP Configurations**:

#### TypeScript/JavaScript
```json
{
    "typescript": {
        "command": ["typescript-language-server", "--stdio"],
        "filetypes": ["typescript", "typescriptreact", "javascript", "javascriptreact"],
        "extensions": [".ts", ".tsx", ".js", ".jsx"],
        "rootPatterns": ["tsconfig.json", "jsconfig.json", "package.json"],
        "initializationOptions": {
            "preferences": {
                "includeInlayParameterNameHints": "all",
                "includeInlayPropertyDeclarationTypeHints": true
            }
        }
    }
}
```

#### Go
```json
{
    "go": {
        "command": ["gopls", "serve"],
        "filetypes": ["go", "gomod"],
        "extensions": [".go", ".mod"],
        "rootPatterns": ["go.mod", "go.work"],
        "initializationOptions": {
            "staticcheck": true,
            "gofumpt": true
        }
    }
}
```

#### Dart
```json
{
    "dart": {
        "command": ["dart", "language-server", "--protocol=lsp"],
        "filetypes": ["dart"],
        "extensions": [".dart"],
        "rootPatterns": ["pubspec.yaml", "analysis_options.yaml"]
    }
}
```

---

## Commands

Commands are markdown files in the `commands/` directory that define slash commands.

**Location**: `plugins/my-plugin/commands/my-command.md`

### Command Template

```markdown
# /command-name - Brief description

Longer description of what the command does.

## Usage

\`\`\`
/command-name <required-arg> [optional-arg] [--flag=value]
\`\`\`

## Examples

\`\`\`
/command-name foo
/command-name foo bar
/command-name foo --flag=value
\`\`\`

## Behavior

1. First step the command takes
2. Second step
3. Third step

## Requirements

- Any prerequisites (optional section)

## Arguments

- \`required-arg\` (required): Description
- \`optional-arg\` (optional): Description
- \`--flag\` (optional): Description

## Notes

Additional information (optional section)
```

---

## Skills

Skills are directories containing a `SKILL.md` file that define complex agent behaviors.

**Location**: `plugins/my-plugin/skills/my-skill/SKILL.md`

### Skill Template

```markdown
# Skill Name

Brief description of when to use this skill.

## When to Use

- Trigger condition 1
- Trigger condition 2
- User asks about X
- User wants to do Y

## Instructions

### For Use Case A

1. Step one
2. Step two
3. Step three

### For Use Case B

1. Different step one
2. Different step two

## Available MCP Tools

- \`tool_name\` - What it does
- \`another_tool\` - What it does

## Example Workflow

When user says: "Example query"

1. First action: \`tool.method("params")\`
2. Second action
3. Third action
```

---

## Creating a New Plugin

### Step-by-Step Process

1. **Create Directory Structure**
   ```bash
   mkdir -p plugins/my-plugin/.claude-plugin
   mkdir -p plugins/my-plugin/commands
   mkdir -p plugins/my-plugin/skills/my-skill
   ```

2. **Create plugin.json**
   - Set name, description, version, author
   - Reference MCP/LSP configs with `${CLAUDE_PLUGIN_ROOT}`
   - Add relevant keywords

3. **Create .mcp.json**
   - Add required MCP servers (HTTP or command-based)
   - Include shared servers (context7, deepwiki, grep) for documentation

4. **Create .lsp.json**
   - Configure language servers for target languages
   - Set appropriate root patterns and options

5. **Create Commands**
   - One .md file per command in `commands/`
   - Follow the command template structure

6. **Create Skills**
   - One directory per skill in `skills/`
   - Each skill has a `SKILL.md` file

7. **Create README.md**
   - Document features, requirements, installation, usage

8. **Update marketplace.json**
   - Add plugin to the `plugins` array
   - Update marketplace keywords if needed

---

## Best Practices

### Naming
- Plugin names: `feature-plugin` (kebab-case with `-plugin` suffix)
- Command names: `/feature-action` (kebab-case with leading slash)
- Skill directories: `feature-name` (kebab-case)
- MCP servers: `server-name` (kebab-case)

### Configuration
- Always use `${CLAUDE_PLUGIN_ROOT}` for portable paths
- Include version requirements in `requires` field
- Use semantic versioning (1.0.0)

### MCP Servers
- Include shared servers (context7, deepwiki, grep) for documentation lookup
- Use HTTP servers when available (simpler, no local install)
- Use command servers for local tools (next-devtools, dart mcp-server)

### Documentation
- Every plugin needs a README.md
- Commands should have clear usage examples
- Skills should list trigger conditions and workflows

---

## Troubleshooting

### Plugin Not Loading
- Check `marketplace.json` source path is correct
- Verify `plugin.json` is in `.claude-plugin/` directory
- Ensure JSON syntax is valid

### MCP Server Not Connecting
- HTTP servers: Check URL is correct and accessible
- Command servers: Ensure executable is installed and in PATH
- Check for authentication requirements (e.g., EAS paid plan for Expo)

### LSP Not Working
- Verify language server is installed globally
- Check command array format: `["executable", "--flag"]`
- Ensure rootPatterns match your project files

### Commands Not Appearing
- Check file is in `commands/` directory (not `.claude-plugin/commands/`)
- Verify markdown format with `# /command-name` header
- File must have `.md` extension

---

## Quick Reference

### Installation Commands
```bash
# Add marketplace
/plugin marketplace add owner/repo-name

# Install plugin
/plugin install plugin-name@marketplace-name

# Validate plugin
/plugin validate .
```

### File Locations
| File | Location |
|------|----------|
| Marketplace manifest | `.claude-plugin/marketplace.json` |
| Plugin manifest | `plugins/*/\`.claude-plugin/plugin.json` |
| MCP config | `plugins/*/.mcp.json` |
| LSP config | `plugins/*/.lsp.json` |
| Commands | `plugins/*/commands/*.md` |
| Skills | `plugins/*/skills/*/SKILL.md` |

### Environment Variables
| Variable | Description |
|----------|-------------|
| `${CLAUDE_PLUGIN_ROOT}` | Root directory of the plugin |

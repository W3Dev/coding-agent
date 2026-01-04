# W3Dev Coding Agent - Claude Code Plugin Marketplace

A curated Claude Code plugin marketplace providing essential development tools with MCP servers for documentation lookup and code search, plus LSP support for multiple languages.

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

# Expo/React Native development toolkit
/plugin install expo-devtools-plugin@w3dev

# Flutter/Dart development toolkit
/plugin install flutter-devtools-plugin@w3dev
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

---

### 2. nextjs-devtools-plugin

Complete Next.js development toolkit:

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

#### Commands
| Command | Description |
|---------|-------------|
| `/nextjs-errors` | Check build and runtime errors |
| `/nextjs-routes` | Inspect application routes |
| `/nextjs-upgrade` | Upgrade Next.js version |

#### Requirements
- Node.js v20.19+
- Next.js 16+ with dev server running

---

### 3. expo-devtools-plugin

Expo/React Native development toolkit:

#### MCP Servers
| Server | Description |
|--------|-------------|
| **expo-mcp** | Official Expo MCP for documentation and automation |
| **deepwiki** | Ask questions about any GitHub repository |
| **context7** | Query up-to-date documentation for any library |
| **grep** | Search real-world code examples from public GitHub repos |

#### LSP Support
| Language | Server | Extensions |
|----------|--------|------------|
| **TypeScript/JavaScript** | `typescript-language-server` | `.ts`, `.tsx`, `.js`, `.jsx` |

#### Commands
| Command | Description |
|---------|-------------|
| `/expo-docs` | Look up Expo documentation |
| `/expo-install` | Install Expo packages with `npx expo install` |
| `/expo-screenshot` | Take screenshot of running app |

#### Requirements
- EAS paid plan (for full Expo MCP features)
- Expo SDK 54+
- Node.js 18+

---

### 4. flutter-devtools-plugin

Flutter/Dart development toolkit:

#### MCP Servers
| Server | Description |
|--------|-------------|
| **dart** | Official Dart MCP for code analysis and package management |
| **deepwiki** | Ask questions about any GitHub repository |
| **context7** | Query up-to-date documentation for any library |
| **grep** | Search real-world code examples from public GitHub repos |

#### LSP Support
| Language | Server | Extensions |
|----------|--------|------------|
| **Dart** | `dart language-server` | `.dart` |

#### Commands
| Command | Description |
|---------|-------------|
| `/flutter-analyze` | Analyze Flutter/Dart code for issues |
| `/flutter-test` | Run Flutter tests |
| `/flutter-pub` | Search pub.dev and manage dependencies |

#### Requirements
- Dart SDK 3.9+
- Flutter SDK (latest stable)

---

## Marketplace-Level Skills

These skills are available at the marketplace level to help with plugin development:

| Skill | Description |
|-------|-------------|
| `plugin-builder` | Comprehensive guide for creating Claude Code plugins and marketplaces |

The `plugin-builder` skill teaches you how to:
- Structure plugins and marketplaces
- Configure MCP and LSP servers
- Create commands and skills
- Follow best practices and naming conventions

---

## Project Structure

```
w3dev-agent/
├── .claude-plugin/
│   └── marketplace.json        # Marketplace registry
├── plugins/
│   ├── basic-development/      # Basic development plugin
│   ├── nextjs-devtools/        # Next.js devtools plugin
│   ├── expo-devtools/          # Expo/React Native plugin
│   └── flutter-devtools/       # Flutter/Dart plugin
├── skills/
│   └── plugin-builder/         # Plugin development guide
│       └── SKILL.md
└── README.md
```

## Requirements by Plugin

| Plugin | Runtime | LSP |
|--------|---------|-----|
| basic-development | Node.js | TypeScript, Go |
| nextjs-devtools | Node.js 20.19+ | TypeScript |
| expo-devtools | Node.js 18+, EAS paid plan | TypeScript |
| flutter-devtools | Dart 3.9+ | Dart |

### LSP Installation

**TypeScript/JavaScript:**
```bash
npm install -g typescript-language-server typescript
```

**Go:**
```bash
go install golang.org/x/tools/gopls@latest
```

**Dart:** (included with Dart SDK 3.9+)

## Usage Examples

### Basic Development
```
/docs react useState hook
/search-code "useEffect(" --lang=TypeScript
```

### Next.js Development
```
/nextjs-errors
/nextjs-routes
```

### Expo/React Native Development
```
/expo-docs navigation
/expo-install expo-camera
```

### Flutter/Dart Development
```
/flutter-analyze
/flutter-pub search state management
/flutter-test
```

## Contributing

1. Fork the repository
2. Read the `plugin-builder` skill in `skills/plugin-builder/SKILL.md` for comprehensive guidance
3. Add your plugin to the `plugins/` directory following the documented structure
4. Update `.claude-plugin/marketplace.json` to include your plugin
5. Submit a pull request

## License

MIT

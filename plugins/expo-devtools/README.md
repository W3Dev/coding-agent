# Expo DevTools Plugin

A complete Claude Code plugin for Expo/React Native development with Expo MCP, documentation lookup, code search, and TypeScript LSP support.

## Features

### MCP Servers
| Server | Description |
|--------|-------------|
| **expo-mcp** | Official Expo MCP for documentation and automation |
| **deepwiki** | Ask questions about any GitHub repository |
| **context7** | Query up-to-date documentation for any library |
| **grep** | Search real-world code examples from public GitHub repos |

### LSP Support
| Language | Server | Extensions |
|----------|--------|------------|
| **TypeScript/JavaScript** | `typescript-language-server` | `.ts`, `.tsx`, `.js`, `.jsx` |

### Capabilities

**Remote Tools (EAS paid plan required):**
- Access Expo documentation with `learn`
- Natural language documentation search
- Install packages with proper version compatibility

**Local Tools (requires dev server):**
- Take screenshots of running app
- Interact with UI elements by testID
- Query component properties
- Launch React Native DevTools
- Display Expo Router sitemap

### Commands
| Command | Description |
|---------|-------------|
| `/expo-docs` | Look up Expo documentation |
| `/expo-install` | Install Expo packages with `npx expo install` |
| `/expo-screenshot` | Take screenshot of running app |

### Skills
| Skill | Description |
|-------|-------------|
| `expo-debug` | Debug Expo/React Native applications |

## Requirements

- EAS paid plan (for full Expo MCP features)
- Expo SDK 54+
- Node.js 18+
- TypeScript language server (`npm install -g typescript-language-server typescript`)

### For Local Automation Features

Start your dev server with MCP enabled:
```bash
npx expo install expo-mcp --dev
EXPO_UNSTABLE_MCP_SERVER=1 npx expo start
```

## Installation

```bash
/plugin install expo-devtools-plugin@w3dev
```

## Usage

### Look up documentation
```
/expo-docs navigation
/expo-docs push-notifications
```

### Install packages
```
/expo-install expo-camera
/expo-install react-native-reanimated
```

### Take screenshot (requires local dev server)
```
/expo-screenshot
/expo-screenshot --testid=home-screen
```

## License

MIT

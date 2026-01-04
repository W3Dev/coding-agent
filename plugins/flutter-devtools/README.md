# Flutter DevTools Plugin

A complete Claude Code plugin for Flutter/Dart development with Dart MCP, code analysis, testing, dependency management, and Dart LSP support.

## Features

### MCP Servers
| Server | Description |
|--------|-------------|
| **dart** | Official Dart MCP for code analysis and package management |
| **deepwiki** | Ask questions about any GitHub repository |
| **context7** | Query up-to-date documentation for any library |
| **grep** | Search real-world code examples from public GitHub repos |

### LSP Support
| Language | Server | Extensions |
|----------|--------|------------|
| **Dart** | `dart language-server` | `.dart` |

### Capabilities
- Code analysis and error detection
- Symbol resolution and documentation lookup
- Application introspection
- Package search on pub.dev
- Dependency management in pubspec.yaml
- Test execution and result analysis
- Code formatting

### Commands
| Command | Description |
|---------|-------------|
| `/flutter-analyze` | Analyze Flutter/Dart code for issues |
| `/flutter-test` | Run Flutter tests |
| `/flutter-pub` | Search pub.dev and manage dependencies |

### Skills
| Skill | Description |
|-------|-------------|
| `flutter-debug` | Debug Flutter/Dart applications |

## Requirements

- Dart SDK 3.9+
- Flutter SDK (latest stable recommended)

## Installation

```bash
/plugin install flutter-devtools-plugin@w3dev
```

## Usage

### Analyze code
```
/flutter-analyze
/flutter-analyze lib/
/flutter-analyze --fix
```

### Run tests
```
/flutter-test
/flutter-test test/widget_test.dart
/flutter-test --coverage
```

### Manage dependencies
```
/flutter-pub search state management
/flutter-pub add provider
/flutter-pub add mockito --dev
/flutter-pub outdated
```

## License

MIT

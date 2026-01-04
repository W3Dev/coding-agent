# /flutter-analyze - Analyze Flutter/Dart code

Analyze your Flutter/Dart code for issues, errors, and improvements.

## Usage

```
/flutter-analyze [path] [--fix]
```

## Examples

```
/flutter-analyze
/flutter-analyze lib/
/flutter-analyze lib/main.dart
/flutter-analyze --fix
```

## Behavior

1. Use the Dart MCP server to analyze project code
2. Report errors, warnings, and hints
3. Provide fix suggestions based on Dart best practices
4. Optionally apply automatic fixes with `--fix`

## Arguments

- `path` (optional): Specific file or directory to analyze (defaults to entire project)
- `--fix` (optional): Automatically apply suggested fixes

## Notes

- Requires Dart SDK 3.9+
- Uses the same analysis as `dart analyze`
- Respects `analysis_options.yaml` configuration

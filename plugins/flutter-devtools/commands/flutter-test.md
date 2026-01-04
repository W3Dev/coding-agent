# /flutter-test - Run Flutter tests

Run Flutter/Dart tests and analyze results.

## Usage

```
/flutter-test [path] [--coverage]
```

## Examples

```
/flutter-test
/flutter-test test/widget_test.dart
/flutter-test test/unit/
/flutter-test --coverage
```

## Behavior

1. Use the Dart MCP server to run tests
2. Execute tests in the specified path or entire test suite
3. Report test results with pass/fail status
4. Analyze failures and suggest fixes
5. Generate coverage report if requested

## Arguments

- `path` (optional): Specific test file or directory (defaults to `test/`)
- `--coverage` (optional): Generate code coverage report

## Notes

- Requires Dart SDK 3.9+
- Works with both unit tests and widget tests
- Supports Flutter integration tests

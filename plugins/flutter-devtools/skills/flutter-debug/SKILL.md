# Flutter Debug Skill

Use this skill when working on Flutter/Dart applications to debug issues, analyze code, manage dependencies, and run tests.

## When to Use

- User is building a Flutter application
- User needs help with Dart code or Flutter widgets
- User wants to analyze code for errors or improvements
- User needs to manage pub.dev dependencies
- User wants to run or debug tests
- User asks about Flutter architecture or best practices

## Instructions

### For Code Analysis

1. Use the Dart MCP server to analyze project code
2. Identify errors, warnings, and hints
3. Suggest fixes based on Dart/Flutter best practices
4. Consider using `--fix` for automatic corrections

### For Dependency Management

1. Use Dart MCP to search pub.dev for packages
2. Evaluate package quality (likes, pub points, popularity)
3. Add dependencies to pubspec.yaml
4. Run `dart pub get` to install

### For Testing

1. Use Dart MCP to run tests
2. Analyze test failures and suggest fixes
3. Check code coverage for untested areas
4. Recommend additional test cases

### For Documentation

1. Use Context7 to query Flutter/Dart documentation
2. Use Deepwiki for questions about Flutter packages on GitHub
3. Use Grep to find real-world implementation examples

### For Symbol Resolution

1. Use Dart MCP to resolve symbols to their definitions
2. Fetch documentation and signatures
3. Understand class hierarchies and relationships

## Available MCP Tools

### Dart MCP Server
- Code analysis and error detection
- Symbol resolution and documentation
- Package search on pub.dev
- Dependency management in pubspec.yaml
- Test execution and result analysis
- Code formatting with dart format

### Shared Tools
- `mcp__context7__query-docs` - Flutter/Dart documentation
- `mcp__deepwiki__ask_question` - GitHub repo questions
- `mcp__grep__searchGitHub` - Real-world code examples

## Example Workflow

When user says: "My Flutter app has a state management issue"

1. Analyze code: Use Dart MCP to analyze the project
2. Identify issues: Check for common state management anti-patterns
3. Search for solutions: `context7.query-docs("/flutter/flutter", "state management provider")`
4. Find examples: `grep.searchGitHub("ChangeNotifier", language=["Dart"])`
5. Suggest refactoring with proper state management patterns

## Flutter-Specific Patterns

### Widget Debugging
- Check for missing keys in lists
- Identify const widget opportunities
- Detect unnecessary rebuilds

### State Management
- Provider/Riverpod patterns
- BLoC architecture
- GetX usage

### Performance
- Identify expensive builds
- Check for proper disposal
- Async operation handling

# /flutter-pub - Manage pub.dev dependencies

Search pub.dev for packages and manage dependencies in pubspec.yaml.

## Usage

```
/flutter-pub <action> [package-name]
```

## Examples

```
/flutter-pub search http client
/flutter-pub add provider
/flutter-pub add dio --dev
/flutter-pub remove unused_package
/flutter-pub outdated
```

## Behavior

1. Use the Dart MCP server for package operations
2. Search pub.dev for suitable packages
3. Add/remove dependencies in pubspec.yaml
4. Check for outdated packages

## Actions

- `search <query>` - Search pub.dev for packages matching the query
- `add <package>` - Add a package to dependencies
- `add <package> --dev` - Add a package to dev_dependencies
- `remove <package>` - Remove a package from dependencies
- `outdated` - Check for outdated dependencies

## Arguments

- `action` (required): The pub action to perform
- `package-name` (optional): Package name for add/remove operations

## Notes

- Requires Dart SDK 3.9+
- Updates pubspec.yaml automatically
- Runs `dart pub get` after modifications

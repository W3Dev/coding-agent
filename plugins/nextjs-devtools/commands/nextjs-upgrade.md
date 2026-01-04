# /nextjs-upgrade - Upgrade Next.js to latest version

Run the official Next.js codemod to upgrade your project to the latest version.

## Usage

```
/nextjs-upgrade [--target=<version>] [--dry-run]
```

## Examples

```
/nextjs-upgrade
/nextjs-upgrade --target=16
/nextjs-upgrade --dry-run
```

## Behavior

1. Analyze current Next.js version
2. Run official upgrade codemods
3. Update dependencies and configuration
4. Report breaking changes and manual steps needed

## Arguments

- `--target` (optional): Target version (defaults to latest)
- `--dry-run` (optional): Preview changes without applying them

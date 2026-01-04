# /nextjs-errors - Check Next.js build and runtime errors

Retrieve current build errors, runtime errors, and TypeScript issues from your running Next.js development server.

## Usage

```
/nextjs-errors [--type=<error-type>]
```

## Examples

```
/nextjs-errors
/nextjs-errors --type=build
/nextjs-errors --type=runtime
/nextjs-errors --type=typescript
```

## Behavior

1. Connect to the Next.js dev server MCP endpoint
2. Retrieve all current errors from the running application
3. Display errors with file locations, line numbers, and stack traces
4. Suggest fixes based on error patterns

## Requirements

- Next.js 16+ with dev server running
- next-devtools-mcp connected to the dev server

## Arguments

- `--type` (optional): Filter by error type (build, runtime, typescript). Shows all if not specified.

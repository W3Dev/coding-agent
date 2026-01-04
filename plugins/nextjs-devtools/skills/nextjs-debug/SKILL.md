# Next.js Debug Skill

Use this skill when working on Next.js applications to debug errors, inspect routes, and access real-time application state.

## When to Use

- User reports a Next.js build or runtime error
- User needs to debug server components or server actions
- User wants to inspect routes or page metadata
- User asks about hydration errors or SSR issues
- User needs to check the application state

## Instructions

### For Build/Runtime Errors

1. Use the next-devtools MCP to retrieve current errors
2. Analyze error messages and stack traces
3. Check the affected file and line number
4. Suggest fixes based on Next.js best practices

### For Route Inspection

1. Query all routes using next-devtools
2. Identify route patterns, layouts, and middleware
3. Explain rendering modes (SSR, SSG, ISR, client)

### For Debugging Workflow

1. First, check if the Next.js dev server is running
2. Use `nextjs_index` tool to get available dev server instances
3. Use `nextjs_call` to invoke specific debugging actions
4. Cross-reference errors with the codebase

## Available MCP Tools

- `nextjs_index` - List all connected Next.js dev server instances
- `nextjs_call` - Invoke actions on the Next.js dev server
- `nextjs_read_docs` - Read Next.js documentation
- `nextjs_upgrade` - Run upgrade codemods

## Example Workflow

When user says: "My page is showing a hydration error"

1. Check for runtime errors: `nextjs_call("errors")`
2. Identify the component causing the mismatch
3. Review the component code for client/server inconsistencies
4. Suggest fixes (useEffect for client-only code, dynamic imports, etc.)

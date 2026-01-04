# /nextjs-routes - Inspect Next.js application routes

Query and display all routes, their components, and rendering details from your Next.js application.

## Usage

```
/nextjs-routes [pattern]
```

## Examples

```
/nextjs-routes
/nextjs-routes /api/*
/nextjs-routes /dashboard
```

## Behavior

1. Connect to the Next.js dev server
2. Retrieve page routes, API routes, and dynamic segments
3. Display route information including:
   - Route path and pattern
   - Rendering mode (SSR, SSG, ISR, client)
   - Associated components and layouts
   - Middleware chain

## Requirements

- Next.js 16+ with dev server running

## Arguments

- `pattern` (optional): Filter routes by pattern (supports wildcards)

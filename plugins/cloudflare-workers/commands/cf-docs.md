# /cf-docs - Look up Cloudflare Workers documentation

Access Cloudflare Workers and platform documentation using the Cloudflare docs MCP server.

## Usage

```
/cf-docs <topic> [query]
```

## Examples

```
/cf-docs workers
/cf-docs kv namespaces
/cf-docs r2 buckets
/cf-docs d1 database
/cf-docs workers ai
```

## Behavior

1. Use the cf-docs MCP server to access Cloudflare documentation
2. Search for the specified topic in Workers docs
3. Return relevant documentation sections with examples
4. Supplement with Context7 for additional library docs if needed

## Arguments

- `topic` (required): The Cloudflare topic to look up (workers, kv, r2, d1, ai, etc.)
- `query` (optional): Specific question or subtopic to search for

## Notes

- Requires Cloudflare account for MCP authentication
- Covers all Cloudflare developer platform documentation

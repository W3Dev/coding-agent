# Cloudflare Workers Debug Skill

Use this skill when working on Cloudflare Workers applications to debug issues, manage deployments, access logs, and work with storage bindings (KV, R2, D1).

## When to Use

- User is building a Cloudflare Worker
- User needs help with Workers deployment or configuration
- User wants to debug Workers errors or performance issues
- User needs to manage KV, R2, or D1 storage
- User asks about Workers AI or other bindings
- User wants to view logs or analytics

## Instructions

### For Documentation Lookup

1. Use the cf-docs MCP server to access official Cloudflare documentation
2. Search for Workers-specific topics (bindings, runtime APIs, etc.)
3. Supplement with Context7 for TypeScript/JavaScript library docs
4. Use Grep to find real-world Worker code examples

### For Deployment

1. Use the cf-builds MCP server to manage deployments
2. Verify wrangler.toml configuration is correct
3. Check for build errors and suggest fixes
4. Monitor deployment status and report results

### For Debugging

1. Use cf-observability MCP to access logs and analytics
2. Identify error patterns and performance bottlenecks
3. Check for common issues:
   - CPU time limit exceeded
   - Memory limit exceeded
   - Fetch to origin timeout
   - Binding configuration errors
4. Suggest optimizations and fixes

### For Storage Operations

1. Use cf-bindings MCP to interact with KV, R2, D1
2. Help with CRUD operations on storage
3. Debug binding configuration issues
4. Optimize storage access patterns

### For Workers AI

1. Use cf-bindings to access AI models
2. Help with model selection and parameters
3. Debug inference errors
4. Optimize prompts and responses

## Available MCP Tools

### Cloudflare MCP Servers

- `cf-docs` - Cloudflare documentation access
- `cf-bindings` - Workers bindings (KV, R2, D1, AI, etc.)
- `cf-builds` - Deployment and build management
- `cf-observability` - Logs, analytics, and debugging

### Shared Tools

- `mcp__context7__query-docs` - Library documentation
- `mcp__deepwiki__ask_question` - GitHub repo questions
- `mcp__grep__searchGitHub` - Real-world code examples

## Example Workflows

### Workflow 1: Deploy and Monitor Worker

When user says: "Deploy my Worker and check if it's working"

1. Verify configuration: Check wrangler.toml exists and is valid
2. Deploy: Use cf-builds to deploy the Worker
3. Monitor: Use cf-observability to tail logs
4. Report: Show deployment URL and initial log entries

### Workflow 2: Debug KV Access Error

When user says: "My Worker can't read from KV"

1. Check bindings: Verify KV namespace is bound in wrangler.toml
2. Test access: Use cf-bindings to test KV read operation
3. Check logs: Use cf-observability for error messages
4. Identify issue: Common problems:
   - Namespace not bound
   - Wrong binding name
   - Key doesn't exist
   - Permission issues
5. Suggest fix: Update wrangler.toml or code

### Workflow 3: Performance Optimization

When user says: "My Worker is slow"

1. Analyze logs: Use cf-observability to check execution times
2. Identify bottlenecks:
   - Slow fetch() calls
   - Inefficient KV/R2/D1 access
   - Heavy computation
   - Large response payloads
3. Suggest optimizations:
   - Cache frequently accessed data
   - Use KV for static data
   - Parallelize fetch requests
   - Minimize payload sizes
4. Monitor improvements: Compare before/after metrics

## Common Issues and Solutions

### CPU Time Limit Exceeded
- **Cause**: Computation taking too long
- **Fix**: Optimize algorithms, use async operations, consider Durable Objects

### Memory Limit Exceeded
- **Cause**: Large data structures or response bodies
- **Fix**: Stream responses, paginate data, use external storage

### Binding Not Found
- **Cause**: Missing or incorrect binding in wrangler.toml
- **Fix**: Add binding configuration, ensure binding name matches code

### CORS Errors
- **Cause**: Missing CORS headers in response
- **Fix**: Add proper Access-Control-* headers

## Cloudflare Workers Specifics

### Environment Variables vs Bindings
- Env vars: Simple strings, set in wrangler.toml
- Bindings: Complex resources (KV, R2, D1, AI, etc.)

### Request Context
- `env` object contains all bindings
- `ctx` provides waitUntil() and passThroughOnException()

### Response Handling
- Must return Response object
- Use streaming for large payloads
- Set appropriate headers (Content-Type, Cache-Control, etc.)

### Best Practices
- Keep Workers stateless
- Use KV for configuration/cache
- Use R2 for large objects
- Use D1 for relational data
- Use Durable Objects for stateful logic

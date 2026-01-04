# Cloudflare Workers Plugin

A complete Claude Code plugin for Cloudflare Workers development with managed MCP servers for deployment, debugging, storage management, and documentation access.

## Features

### MCP Servers
| Server | Description |
|--------|-------------|
| **cf-docs** | Cloudflare platform documentation |
| **cf-bindings** | Workers bindings (KV, R2, D1, AI, Queue, etc.) |
| **cf-builds** | Workers deployment and build management |
| **cf-observability** | Logs, analytics, and performance monitoring |
| **deepwiki** | Ask questions about any GitHub repository |
| **context7** | Query up-to-date documentation for any library |
| **grep** | Search real-world code examples from public GitHub repos |

### LSP Support
| Language | Server | Extensions |
|----------|--------|------------|
| **TypeScript/JavaScript** | `typescript-language-server` | `.ts`, `.js`, `.mts`, `.mjs` |

### Capabilities

**Documentation & Learning:**
- Access complete Cloudflare Workers documentation
- Search for Workers APIs, bindings, and best practices
- Find real-world Worker code examples

**Deployment & Management:**
- Deploy Workers to Cloudflare's edge network
- Manage Workers builds and versions
- Configure environments and routes

**Debugging & Monitoring:**
- View real-time logs and analytics
- Debug errors and performance issues
- Monitor Worker execution metrics

**Storage & Bindings:**
- Manage KV namespaces (create, read, update, delete)
- Work with R2 buckets
- Query D1 databases
- Use Workers AI models
- Access other bindings (Queue, Durable Objects, etc.)

### Commands
| Command | Description |
|---------|-------------|
| `/cf-docs` | Look up Cloudflare Workers documentation |
| `/cf-deploy` | Deploy Worker to Cloudflare |
| `/cf-logs` | View Worker logs and analytics |
| `/cf-kv` | Manage KV namespace operations |

### Skills
| Skill | Description |
|-------|-------------|
| `cloudflare-debug` | Debug Cloudflare Workers applications |

## Requirements

- Cloudflare account with API token
- Node.js 18+
- TypeScript language server (`npm install -g typescript-language-server typescript`)
- Optional: Wrangler CLI for local development

## Installation

```bash
/plugin install cloudflare-workers-plugin@w3dev
```

## Usage

### Look up documentation
```
/cf-docs workers
/cf-docs kv namespaces
/cf-docs workers ai
```

### Deploy your Worker
```
/cf-deploy
/cf-deploy --env=production
```

### View logs
```
/cf-logs
/cf-logs my-worker --tail
/cf-logs my-worker --filter=error
```

### Manage KV storage
```
/cf-kv list
/cf-kv get MY_NAMESPACE my-key
/cf-kv put MY_NAMESPACE my-key "value"
```

## Authentication

Cloudflare's managed MCP servers require OAuth authentication. When you first use a Cloudflare MCP server, you'll be prompted to authenticate with your Cloudflare account.

## Cloudflare Workers Resources

### Storage Options
- **KV**: Key-value storage for frequently accessed data
- **R2**: Object storage for large files
- **D1**: SQLite databases at the edge
- **Durable Objects**: Stateful serverless objects

### AI & Compute
- **Workers AI**: Run AI models at the edge
- **Vectorize**: Vector database for embeddings
- **Queues**: Message queuing system

### Configuration
Workers are configured via `wrangler.toml`:
```toml
name = "my-worker"
main = "src/index.ts"
compatibility_date = "2024-01-01"

[[kv_namespaces]]
binding = "MY_KV"
id = "your-kv-id"
```

## License

MIT

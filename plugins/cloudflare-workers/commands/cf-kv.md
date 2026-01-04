# /cf-kv - Manage KV namespace operations

Manage Cloudflare Workers KV namespaces using the cf-bindings MCP server.

## Usage

```
/cf-kv <action> [namespace] [key] [value]
```

## Examples

```
/cf-kv list
/cf-kv get MY_NAMESPACE my-key
/cf-kv put MY_NAMESPACE my-key "my-value"
/cf-kv delete MY_NAMESPACE my-key
/cf-kv create my-new-namespace
```

## Behavior

1. Use cf-bindings MCP server to interact with KV
2. Execute the specified KV operation
3. Return results with status and data
4. Handle errors and suggest fixes

## Actions

- `list` - List all KV namespaces in account
- `get <namespace> <key>` - Get value for a key
- `put <namespace> <key> <value>` - Set key-value pair
- `delete <namespace> <key>` - Delete a key
- `create <namespace>` - Create new KV namespace

## Arguments

- `action` (required): KV operation to perform
- `namespace` (optional): KV namespace ID or binding name
- `key` (optional): Key name for get/put/delete
- `value` (optional): Value for put operation

## Notes

- Requires Cloudflare account with Workers KV enabled
- KV namespaces must be bound to Workers in wrangler.toml
- Free tier includes 100,000 reads/day

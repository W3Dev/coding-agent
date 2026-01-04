# /cf-logs - View Worker logs and analytics

View real-time logs and analytics for your Cloudflare Workers using the cf-observability MCP server.

## Usage

```
/cf-logs [worker-name] [--tail] [--filter=<pattern>]
```

## Examples

```
/cf-logs
/cf-logs my-worker
/cf-logs my-worker --tail
/cf-logs my-worker --filter=error
```

## Behavior

1. Connect to cf-observability MCP server
2. Retrieve logs and analytics for the specified Worker
3. Display recent logs with timestamps and severity
4. Show performance metrics and error rates
5. Optionally stream logs in real-time with --tail

## Arguments

- `worker-name` (optional): Specific Worker to monitor (defaults to current project)
- `--tail` (optional): Stream logs in real-time
- `--filter` (optional): Filter logs by pattern (error, warn, info)

## Notes

- Requires Cloudflare account with observability access
- Real-time logs available on paid plans
- Shows last 100 log entries by default

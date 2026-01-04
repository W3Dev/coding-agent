# /cf-deploy - Deploy Worker to Cloudflare

Deploy your Cloudflare Worker using the cf-builds MCP server.

## Usage

```
/cf-deploy [--env=<environment>]
```

## Examples

```
/cf-deploy
/cf-deploy --env=production
/cf-deploy --env=staging
```

## Behavior

1. Use the cf-builds MCP server to manage deployments
2. Build and deploy the Worker to Cloudflare's edge network
3. Report deployment status and URL
4. Show any build errors or warnings

## Requirements

- Valid wrangler.toml configuration in project root
- Cloudflare account with API token
- Workers plan (free or paid)

## Arguments

- `--env` (optional): Target environment (defaults to production)

## Notes

- Uses Cloudflare's managed deployment process
- Automatically handles building and uploading
- Deployment typically completes in seconds

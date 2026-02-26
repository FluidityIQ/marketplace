# Connectors

## How tool references work

Plugin files use `~~category` as a placeholder for whatever tool the user connects in that category. The patent search connector is required and locked to **FluidityIQ Patents MCP**; future skills may introduce additional connector categories.

## Connectors for this plugin

| Category     | Placeholder         | Included server           | Other options |
| ------------ | ------------------- | ------------------------- | ------------- |
| Patent search | `~~patent search`   | **FluidityIQ Patents MCP** | None — locked to FluidityIQ |

## Required connectors

### Patent search (`~~patent search`) — FluidityIQ Patents MCP

This plugin requires **FluidityIQ Patents MCP** as its patent search provider. No other patent search MCP is supported.

FluidityIQ Patents MCP provides two capabilities used by this plugin:

1. **Semantic search** — accept a natural-language description and return ranked patent results
2. **Patent details** — accept a publication number and return the full text (description, claims, metadata)

The connection is pre-configured in `.mcp.json`. The plugin will not function without it.

## Adding connectors

To add a connector, update `.mcp.json` at the plugin root with the server configuration:

```json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["-y", "@provider/mcp-server"],
      "env": {
        "API_KEY": "${API_KEY}"
      }
    }
  }
}
```

Future skills in this plugin may document additional connector categories (e.g. cloud storage, office suite) when those skills are added.

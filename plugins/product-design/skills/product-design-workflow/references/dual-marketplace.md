# Dual Marketplace

This repo supports both Claude Code and Codex plugin marketplaces.

## Claude

Root marketplace:

```text
.claude-plugin/marketplace.json
```

Plugin manifest:

```text
plugins/<plugin>/.claude-plugin/plugin.json
```

Current Claude entries use:

```json
{
  "name": "product-design",
  "source": "./plugins/product-design",
  "description": "..."
}
```

## Codex

Root marketplace:

```text
.agents/plugins/marketplace.json
```

Plugin manifest:

```text
plugins/<plugin>/.codex-plugin/plugin.json
```

Codex marketplace entries use:

```json
{
  "name": "product-design",
  "source": {
    "source": "local",
    "path": "./plugins/product-design"
  },
  "policy": {
    "installation": "AVAILABLE",
    "authentication": "ON_INSTALL"
  },
  "category": "Design"
}
```

## Maintenance Rule

When adding or removing public plugins, update both root marketplaces. Keep
`product-design` and `live-canvas` listed in both surfaces.

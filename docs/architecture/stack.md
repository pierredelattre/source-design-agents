# Stack and integrations

## Core tools

| Tool | Role | How it connects |
|------|------|-----------------|
| Bridge (MCP) | Design generation in Figma | Plugin API via MCP server |
| figma-cli | Figma inspection, audit, export | Daemon on port 3456, CDP (Yolo) or plugin (Safe) |
| Claude Code | Orchestration, agent execution | CLI + MCP tools |

## figma-cli connection modes

**Yolo (recommended):** `figma-cli connect` — patches the Figma binary once to expose CDP. Fully automatic, survives restarts.

**Safe:** `figma-cli connect --safe` — no binary modification. Uses a development plugin. `render-batch` does not handle text correctly in this mode.

## Data flow

```
User intent
  → Claude Code agent
    → Bridge (creation) or figma-cli (audit/export)
      → Figma Desktop daemon (port 3456)
        → Figma canvas
```

For inter-agent handoffs that involve Figma content: CSpec YAML (see `docs/decisions/001`).

## Bridge fix loop

After each accepted Bridge fix that changes a DS rule, feed the diff to `agent-design-decision-logger` to produce a decision record. Full protocol: `docs/workflows/bridge-fix-loop.md`.

## Planned integrations

- **Storybook**: story export via `figma-cli export storybook`, story mapping via agent-storybook-linker.
- **GitHub Actions**: DS lint, token sync, divergence check on PR.
- **Style Dictionary**: token file output from agent-figma-ds-sync.
- **PDF knowledge base**: `pdfs/` ingested as retrieval context for agent-ds-librarian.

## Agent config wiring

Each Figma-dependent agent has an `agent.config.json` in its directory. Schema:

```jsonc
{
  "model": "claude-sonnet-4-6",
  "figma_cli": {               // present if agent uses figma-cli
    "daemon_url": "http://localhost:3456",
    "connection_mode": "yolo", // "yolo" (local) or "safe" (plugin/CI)
    "allowed_commands": ["fig-start ..."]
  },
  "bridge": {                  // present if agent uses Bridge
    "mcp_server": "plugin:bridge-ds:figma-console",
    "requires_setup": true,    // true = needs /design-workflow setup first
    "setup_command": "/design-workflow setup",
    "use": "full | recipes-search-only | screenshot-verify-only | fix-loop-hook"
  },
  "env": {
    // Runtime env vars — never hardcode secrets here
    // figma-cli uses local CDP daemon: no Figma API token required
  }
}
```

### Agents and their tool bindings

| Agent | figma-cli | Bridge | Setup required |
|-------|-----------|--------|----------------|
| agent-a11y-audit | `a11y audit/contrast/touch/text/vision` | No | `figma-cli connect` |
| agent-ds-linter | `lint`, `find`, `canvas info`, `var list` | No | `figma-cli connect` |
| agent-figma-ds-sync | `var list`, `tokens` | No | `figma-cli connect` |
| agent-storybook-linker | `export storybook` | No | `figma-cli connect` |
| agent-wireframe-to-ds | No | Full | `figma-cli connect` + Bridge setup |
| agent-variant-builder | No | Full | `figma-cli connect` + Bridge setup |
| agent-component-finder | `find` | Recipes only | `figma-cli connect` + Bridge setup |
| agent-usage-coach | `find`, `lint` | Recipes only | `figma-cli connect` + Bridge setup |
| agent-doc-writer | `canvas info`, `export` | Verify only | `figma-cli connect` |
| agent-design-decision-logger | No | Fix-loop hook | None (triggered by Bridge diff) |

### CI / GitHub Actions note

For CI runs: set `connection_mode` to `"safe"` in each config and configure the Figma development plugin. No Figma API token is required for figma-cli (local daemon). Bridge is not available in CI — agents that depend on Bridge for creation cannot run headlessly.

## Setup sequence (new session)

1. `cd figma-cli && npm install`
2. `figma-cli connect`
3. Run `/design-workflow setup` in Bridge to index the DS from the active Figma file.
4. All component-aware agents depend on step 3.

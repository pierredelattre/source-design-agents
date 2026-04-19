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

## Planned integrations

- **Storybook**: story export via `figma-cli export storybook`, story mapping via agent-storybook-linker.
- **GitHub Actions**: DS lint, token sync, divergence check on PR.
- **Style Dictionary**: token file output from agent-figma-ds-sync.
- **PDF knowledge base**: `pdfs/` ingested as retrieval context for agent-ds-librarian.

## Setup sequence (new session)

1. `cd figma-cli && npm install`
2. `figma-cli connect`
3. Run `/design-workflow setup` in Bridge to index the DS from the active Figma file.
4. All component-aware agents depend on step 3.

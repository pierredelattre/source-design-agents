# 002 — Bridge for generation, figma-cli for audits

**Status:** Accepted
**Date:** 2026-04-19

## Context

Two tools can interact with Figma: Bridge (MCP-based, compiler-driven) and figma-cli (daemon-based CLI). There was a risk of agents choosing one arbitrarily or using them interchangeably.

## Decision

- **Bridge** handles all creation: frames, components, screens, variants. No raw Plugin API code ever.
- **figma-cli** handles all inspection and auditing: lint, a11y, contrast, token export, Storybook export, batch operations, library imports.

## Rationale

Bridge enforces DS token discipline through its compiler. figma-cli has purpose-built audit commands that would be expensive to replicate. Each tool is optimized for a different direction of data flow (write vs read/inspect).

## Consequences

- Agents must never call figma-cli to create visual content.
- Agents must never call Bridge for audit tasks.
- The a11y agent specifically must call `fig-start a11y audit`, not reimplement contrast checking.

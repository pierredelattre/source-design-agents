# 001 — CSpec YAML as inter-agent exchange format

**Status:** Accepted
**Date:** 2026-04-19

## Context

Multiple agents need to pass Figma design representations to each other. For example, agent-wireframe-to-ds generates a screen structure and agent-component-finder then enriches it with DS components. Without a shared format, each agent would invent its own JSON schema.

## Decision

CSpec YAML (the Bridge compiler's scene description format) is the canonical exchange format between any agents that produce or consume Figma content.

## Rationale

- Bridge already defines and validates this format via the compiler.
- Using it for inter-agent handoffs means the compiler catches errors before anything hits Figma.
- Avoids duplicating schema definitions across agents.

## Consequences

- Any agent outputting Figma content must emit valid CSpec YAML, not arbitrary JSON or Markdown.
- Agents that consume Figma content must accept CSpec as input.
- New agents must read `references/compiler-reference.md` (figma-cli) before implementing output.

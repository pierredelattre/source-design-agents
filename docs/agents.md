# Agent index

Canonical list of agents in this repo. Before creating or modifying an agent, read this file and `docs/prompts/agent-conventions.md`.

## Status legend

| Symbol | Meaning |
|--------|---------|
| planned | Defined, not yet implemented |
| in-progress | Implementation started |
| implemented | instructions.md exists, not yet tested in production |
| stable | Implemented and tested |

---

## Product design workflow

### agent-ux-research-synthesizer
**Status:** implemented
**Role:** Synthesises raw UX research into personas, journey maps, top insights, and JTBD statements using established research methods.
**Input:** Raw research notes, method used, product context
**Output:** Markdown — personas, journey map, top insights, JTBD statements, open questions
**Tools:** None
**Knowledge:** `docs/resources/ux-ui-reference.md` §2–§4
**Playbook:** `docs/workflows/playbook-product-designer.md` §2
**Examples:** `agents/agent-ux-research-synthesizer/examples/`

### agent-flow-builder
**Status:** implemented
**Role:** Transforms user stories or backlog items into structured user flows.
**Input:** User stories or backlog (text / Markdown)
**Output:** Mermaid flow diagrams + screen checklists
**Tools:** None (pure text processing)
**Playbook:** `docs/workflows/playbook-product-designer.md` §3
**Examples:** `agents/agent-flow-builder/examples/`

---

## UI design and DS

### agent-wireframe-to-ds
**Status:** implemented
**Role:** Given a screen description, proposes the best DS component combination to cover it.
**Input:** Screen description (text) + DS knowledge (from Bridge setup)
**Output:** CSpec YAML (Bridge format) — see ADR 001
**Tools:** Bridge (`/design-workflow`)
**Playbook:** `docs/workflows/playbook-product-designer.md` §4
**Examples:** `agents/agent-wireframe-to-ds/examples/`

### agent-component-finder
**Status:** implemented
**Role:** Finds DS components matching a natural language description.
**Input:** Component description (text)
**Output:** List of matching components with variant recommendations
**Tools:** Bridge recipes, figma-cli (`fig-start find`)
**Playbook:** `docs/workflows/playbook-product-designer.md` §5
**Examples:** `agents/agent-component-finder/examples/`

### agent-variant-builder
**Status:** implemented
**Role:** Generates all required variants (size, state, emphasis) for a component.
**Input:** Component name + variant matrix
**Output:** Figma variants via Bridge (CSpec YAML)
**Tools:** Bridge (`/design-workflow`)
**Examples:** `agents/agent-variant-builder/examples/`

### agent-a11y-audit
**Status:** stable
**Role:** Runs WCAG AA accessibility audits on Figma screens, components, and copy. Flags issues with severity, criterion, and a concrete fix.
**Input:** Screen/component description or Figma node ID; optional: device target, mode (light/dark), component list for tab-order, copy for text-alternative review
**Output:** Markdown report — issues table (WCAG criterion, severity, element, fix), passed checks, open questions
**Tools:** figma-cli (`fig-start a11y audit/contrast/touch/text/vision`) — do NOT reimplement
**Rules:** `docs/design/accessibility-checklist.md` (authoritative), `docs/design/conventions.md`, `docs/decisions/`
**Decision:** ADR 002
**Knowledge:** `docs/resources/ux-ui-reference.md` §6
**Playbook:** `docs/workflows/playbook-product-designer.md` §6

---

## Design system management

### agent-stakeholder-comms
**Status:** implemented
**Role:** Generates DS newsletters, release notes, adoption guides, and pitch decks.
**Input:** Output type, audience, DS changes or context
**Output:** Polished Markdown — newsletter, release notes, pitch outline, or adoption guide
**Tools:** None
**Knowledge:** `docs/resources/design-systems.md` §6–§7
**Examples:** `agents/agent-stakeholder-comms/examples/`

### agent-figma-ds-sync
**Status:** implemented
**Role:** Exports Figma variables/tokens to Style Dictionary JSON or CSS variables.
**Input:** Active Figma file (via figma-cli)
**Output:** JSON (Style Dictionary format) or CSS custom properties
**Tools:** figma-cli (`fig-start var list`, `fig-start tokens`)
**Examples:** `agents/agent-figma-ds-sync/examples/`

### agent-ds-linter
**Status:** stable
**Role:** Checks screens and component trees against the DS. Flags strict violations (must fix) and soft recommendations (nice to have), grouped by type: component, token, variant, layout, naming.
**Input:** Screen/component description or Figma node ID; optional: component list with token/variant details, DS version, known exceptions, scope (full / single component / token-only)
**Output:** Markdown lint report — strict violations table, soft recommendations table, passed checks, open questions
**Tools:** figma-cli (`fig-start lint`, `fig-start find`, `fig-start canvas info`, `fig-start var list`) — do NOT reimplement
**Rules:** `docs/design/ds-lint-rules.md` (authoritative), `docs/design/conventions.md`, `docs/decisions/`
**Decision:** ADR 002
**Knowledge:** `docs/resources/design-systems.md` §2–§3, §7
**Playbook:** `docs/workflows/playbook-ds-manager.md` §2

### agent-ds-backlog-manager
**Status:** implemented
**Role:** Triages component requests by impact and technical debt.
**Input:** Request list (text / Markdown)
**Output:** Prioritized backlog with rationale
**Tools:** None
**Examples:** `agents/agent-ds-backlog-manager/examples/`

---

## Handoff and documentation

### agent-doc-writer
**Status:** implemented
**Role:** Generates functional specs and DS documentation from maquettes and flows.
**Input:** Figma maquette + flow diagram
**Output:** Markdown — functional spec, DS usage guidelines
**Tools:** figma-cli (for export), Bridge (for screenshots via verify)
**Examples:** `agents/agent-doc-writer/examples/`

---

## Ops and logging

### agent-experiment-designer
**Status:** implemented
**Role:** Proposes A/B tests and iteration plans based on a design decision or metric.
**Input:** Design decision or metric goal (text)
**Output:** Markdown — test plan, measurement approach, iteration roadmap
**Tools:** None
**Examples:** `agents/agent-experiment-designer/examples/`

### agent-ds-librarian
**Status:** implemented
**Role:** Answers DS and UX questions by referencing `docs/resources/`. Provides cited answers grounded in the knowledge base, not generic training-data advice.
**Input:** Free-text question; optional context (product, team, DS maturity)
**Output:** Markdown — direct answer with knowledge base citation, deeper reading pointer, related agent suggestion
**Tools:** None
**Knowledge:** `docs/resources/knowledge-index.md`, `docs/resources/design-systems.md`, `docs/resources/ux-ui-reference.md`
**Examples:** `agents/agent-ds-librarian/examples/`

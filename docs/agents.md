# Agent index

Canonical list of agents in this repo. Before creating or modifying an agent, read this file and `docs/prompts/agent-conventions.md`.

## Status legend

| Symbol | Meaning |
|--------|---------|
| planned | Defined, not yet implemented |
| in-progress | Implementation started |
| stable | Implemented and tested |

---

## Product design workflow

### agent-problem-framing
**Status:** planned
**Role:** Turns a raw product brief into a structured problem frame.
**Input:** Free-text product brief
**Output:** Markdown — problem statement, assumptions, risks, success metrics (JTBD format)
**Tools:** None (pure text processing)
**Playbook:** `docs/workflows/playbook-product-designer.md` §1

### agent-ux-research-synthesizer
**Status:** planned
**Role:** Synthesises raw UX research into personas, journey maps, top insights, and JTBD statements using established research methods.
**Input:** Raw research notes, method used, product context
**Output:** Markdown — personas, journey map, top insights, JTBD statements, open questions
**Tools:** None
**Knowledge:** `docs/resources/ux-ui-reference.md` §2–§4
**Playbook:** `docs/workflows/playbook-product-designer.md` §2

### agent-flow-builder
**Status:** planned
**Role:** Transforms user stories or backlog items into structured user flows.
**Input:** User stories or backlog (text / Markdown)
**Output:** Mermaid flow diagrams + screen checklists
**Tools:** None (pure text processing)
**Playbook:** `docs/workflows/playbook-product-designer.md` §3

### agent-flow-qa
**Status:** planned
**Role:** Reviews a flow for missing states, error paths, and empty states.
**Input:** Mermaid flow diagram or screen checklist
**Output:** Markdown — coverage gaps, edge cases, recommended additions
**Tools:** None

---

## UI design and DS

### agent-wireframe-to-ds
**Status:** planned
**Role:** Given a screen description, proposes the best DS component combination to cover it.
**Input:** Screen description (text) + DS knowledge (from Bridge setup)
**Output:** CSpec YAML (Bridge format) — see ADR 001
**Tools:** Bridge (`/design-workflow`)
**Playbook:** `docs/workflows/playbook-product-designer.md` §4

### agent-component-finder
**Status:** planned
**Role:** Finds DS components matching a natural language description.
**Input:** Component description (text)
**Output:** List of matching components with variant recommendations
**Tools:** Bridge recipes, figma-cli (`fig-start find`)
**Playbook:** `docs/workflows/playbook-product-designer.md` §5

### agent-variant-builder
**Status:** planned
**Role:** Generates all required variants (size, state, emphasis) for a component.
**Input:** Component name + variant matrix
**Output:** Figma variants via Bridge (CSpec YAML)
**Tools:** Bridge (`/design-workflow`)

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

### agent-ds-strategy
**Status:** planned
**Role:** Co-builds DS vision, principles, governance model, and KPI framework grounded in the knowledge base.
**Input:** Business context, team size, product maturity (text)
**Output:** Markdown — DS vision document, principles, governance recommendation, KPI list, roadmap
**Tools:** None
**Knowledge:** `docs/resources/design-systems.md` §5–§8

### agent-stakeholder-comms
**Status:** planned
**Role:** Generates DS newsletters, release notes, adoption guides, and pitch decks.
**Input:** Output type, audience, DS changes or context
**Output:** Polished Markdown — newsletter, release notes, pitch outline, or adoption guide
**Tools:** None
**Knowledge:** `docs/resources/design-systems.md` §6–§7

### agent-figma-ds-sync
**Status:** planned
**Role:** Exports Figma variables/tokens to Style Dictionary JSON or CSS variables.
**Input:** Active Figma file (via figma-cli)
**Output:** JSON (Style Dictionary format) or CSS custom properties
**Tools:** figma-cli (`fig-start var list`, `fig-start tokens`)

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
**Status:** planned
**Role:** Triages component requests by impact and technical debt.
**Input:** Request list (text / Markdown)
**Output:** Prioritized backlog with rationale
**Tools:** None

### agent-ds-onboarding
**Status:** planned
**Role:** Generates a role-based onboarding path for a new designer or developer.
**Input:** Role (designer / developer / ds-manager / pm), DS experience level, optional focus area
**Output:** Markdown — reading path, agent map, day-1 checklist, key vocabulary
**Tools:** None
**Knowledge:** `docs/resources/knowledge-index.md`, `docs/resources/design-systems.md`, `docs/resources/ux-ui-reference.md`
**Playbook:** `docs/workflows/playbook-ds-manager.md` §4

### agent-usage-coach
**Status:** planned
**Role:** Recommends DS patterns in response to a screen description or maquette.
**Input:** Screen description or Figma selection
**Output:** Markdown — recommended patterns, anti-patterns to avoid
**Tools:** Bridge recipes, figma-cli

---

## Handoff and documentation

### agent-storybook-linker
**Status:** planned
**Role:** Maps Figma components to Storybook stories, flags divergences.
**Input:** Figma component list + Storybook story list
**Output:** Markdown map — ok / divergence / missing per component
**Tools:** figma-cli (`fig-start export storybook`)

### agent-doc-writer
**Status:** planned
**Role:** Generates functional specs and DS documentation from maquettes and flows.
**Input:** Figma maquette + flow diagram
**Output:** Markdown — functional spec, DS usage guidelines
**Tools:** figma-cli (for export), Bridge (for screenshots via verify)

---

## Ops and logging

### agent-design-decision-logger
**Status:** planned
**Role:** Turns Bridge fix-workflow diffs into decision records in `docs/decisions/`.
**Input:** Bridge fix diff (Figma correction)
**Output:** New or updated ADR in `docs/decisions/`
**Tools:** Bridge fix loop hook
**Decision:** See ADR 002 for tool split; fix-loop integration documented in INIT.md §9.3

### agent-experiment-designer
**Status:** planned
**Role:** Proposes A/B tests and iteration plans based on a design decision or metric.
**Input:** Design decision or metric goal (text)
**Output:** Markdown — test plan, measurement approach, iteration roadmap
**Tools:** None

### agent-ds-librarian
**Status:** planned
**Role:** Answers DS and UX questions by referencing `docs/resources/`. Provides cited answers grounded in the knowledge base, not generic training-data advice.
**Input:** Free-text question; optional context (product, team, DS maturity)
**Output:** Markdown — direct answer with knowledge base citation, deeper reading pointer, related agent suggestion
**Tools:** None
**Knowledge:** `docs/resources/knowledge-index.md`, `docs/resources/design-systems.md`, `docs/resources/ux-ui-reference.md`

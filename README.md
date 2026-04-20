# source-design-agents

AI agents and tools for product designers, UI designers, and design system managers. Orchestrated by Claude Code.

## What's here

| Path | Purpose |
|------|---------|
| `figma-cli/` | CLI that controls Figma Desktop directly — no API key needed |
| `bridge/` | Compiler-driven workflow for generating Figma designs from natural language — enforces DS token rules via a deterministic pipeline |
| `agents/` | Claude Code agent definitions (one per workflow) |
| `docs/` | Guidelines, decision records, playbooks, prompt conventions, knowledge base |
| `pdfs/` | Design reference library (Atomic Design, DS Handbook, Kholmatova, Perez-Cruz, Idean, Henderson) |
| `.agents/skills/` | Claude Code skill files |

## Quick start

```bash
cd figma-cli
npm install
figma-cli connect        # Yolo mode (recommended) — patches Figma once
figma-cli connect --safe # Safe mode — plugin-based, no binary modification
```

See `figma-cli/CLAUDE.md` for the full command reference.

## Agents

### Stable
Instructions written, tested, validated. Tools wired to figma-cli.

| Agent | Input | Output | Knowledge |
|-------|-------|--------|-----------|
| `agent-a11y-audit` | Figma screen or component description | WCAG AA issues table, severity, concrete fix | `ux-ui-reference.md` §6 |
| `agent-ds-linter` | Figma screen or component description | Strict violations + soft recommendations | `design-systems.md` §2–3, §7 |

### Implemented
Instructions written and exercised. Not yet wired to figma-cli tools.

| Agent | Input | Output | Knowledge |
|-------|-------|--------|-----------|
| `agent-ds-strategy` | Business context, team size, product maturity | DS vision, principles, governance model, KPIs, roadmap | `design-systems.md` §5–8 |
| `agent-ux-research-synthesizer` | Raw interview notes or survey data | Personas, journey map, top insights, JTBD, open questions | `ux-ui-reference.md` §2–4 |
| `agent-ds-librarian` | Free-text DS or UX question | Cited answer, deeper reading pointer, related agent suggestion | All `docs/resources/` |
| `agent-ds-onboarding` | Role (designer / dev / DS manager / PM), experience level | Reading path, agent map, day-1 checklist, key vocabulary | All `docs/resources/` |
| `agent-stakeholder-comms` | DS changes, audience, output type | Newsletter, release notes, pitch outline, or adoption guide | `design-systems.md` §6–7 |

### Planned
Defined in `docs/agents.md`. Not yet implemented.

| Agent | Input | Output |
|-------|-------|--------|
| `agent-problem-framing` | Product brief | Problem statement, assumptions, risks, success metrics (JTBD format) |
| `agent-flow-builder` | User stories or backlog | Mermaid flow diagrams + screen checklists |
| `agent-flow-qa` | Mermaid flow or screen checklist | Coverage gaps, edge cases, recommended additions |
| `agent-wireframe-to-ds` | Screen description | CSpec YAML (Bridge format) |
| `agent-component-finder` | Component description | Matching DS components with variant recommendations |
| `agent-variant-builder` | Component name + variant matrix | Figma variants via Bridge (CSpec YAML) |
| `agent-figma-ds-sync` | Active Figma file | Design token JSON (Style Dictionary) or CSS variables |
| `agent-ds-backlog-manager` | Component request list | Prioritised backlog with rationale |
| `agent-usage-coach` | Screen description or Figma selection | Recommended DS patterns, anti-patterns |
| `agent-storybook-linker` | Figma component list + Storybook story list | Parity map per component (ok / divergence / missing) |
| `agent-doc-writer` | Figma maquette + flow diagram | Functional spec, DS usage guidelines |
| `agent-design-decision-logger` | Bridge fix diff | Decision record in `docs/decisions/` |
| `agent-experiment-designer` | Design decision or metric goal | A/B test plan, measurement approach, iteration roadmap |

Full spec for every agent (role, inputs, outputs, tools, playbook): `docs/agents.md`

## Knowledge base

The `/pdfs/` directory is the project's design reference library. It is accessed through synthesised files in `docs/resources/` — never by pasting raw book content into prompts.

### Reference files

| File | Covers |
|------|--------|
| `docs/resources/knowledge-index.md` | Master index — all resources, themes, best-use, target roles |
| `docs/resources/design-systems.md` | Component architecture, patterns, expressiveness, governance, shared language, a11y |
| `docs/resources/ux-ui-reference.md` | Research methods, IA, ideation, usability, accessibility, testing, AI in UX |

**Rule:** for any DS, UX, accessibility, research, or copy task, read the relevant `docs/resources/` file and cite principles from it. Record adopted principles in `docs/decisions/`.

## Docs structure

```
docs/
├── decisions/    # ADR / DSDR — architectural and design decisions (004 records to date)
├── design/       # UI/UX rules, DS guidelines, a11y checklist, conventions
├── architecture/ # Stack decisions, tool integrations, data formats
├── workflows/    # Process playbooks by role
│   ├── playbook-product-designer.md
│   ├── playbook-ds-manager.md
│   └── ds-governance-playbook.md   # Contribution model, lifecycle, metrics, communication
├── prompts/      # Agent prompt conventions and templates
└── resources/    # Knowledge base — synthesised from /pdfs/
```

## Tool integration model

- **Bridge** (`/design-workflow`) handles all Figma frame/component/screen generation.
- **figma-cli** handles lint, a11y audit, token export, Storybook export, batch ops.
- They are complementary — not interchangeable.
- CSpec YAML (Bridge format) is the canonical exchange format between agents that touch Figma.
- See `docs/decisions/002-bridge-vs-figma-cli.md` for the rationale.

## Bridge

Bridge is a compiler-driven design workflow for generating Figma designs from natural language inside Claude Code. It enforces all Figma Plugin API rules through a deterministic pipeline (Parse → Resolve → Validate → Plan → Generate → Wrap), so no hardcoded values and no raw Plugin API code ever reach Figma.

**Three commands, inside Claude Code:**

| Command | What it does |
|---------|-------------|
| `make <description>` | Generate a component or screen from a description |
| `fix` | Capture manual Figma edits as learnings for the KB |
| `done` | Archive the design and extract reusable recipes |

**Setup:** run `setup bridge` once — it scaffolds the KB under `bridge-ds/knowledge-base/` and indexes your design system from the active Figma file.

The KB lives in the repo (`bridge-ds/knowledge-base/registries/`) and stays in sync via a daily cron that detects Figma drift and opens PRs. Engineers and agents can query tokens, variants, and composition rules programmatically.

## Vision

Full vision and agent roadmap: `INIT.md`

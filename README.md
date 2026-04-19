# source-agents

AI agents and tools for product designers, UI designers, and design system managers. Orchestrated by Claude Code.

## What's here

| Path | Purpose |
|------|---------|
| `figma-cli/` | CLI that controls Figma Desktop directly — no API key needed |
| `agents/` | Claude Code agent definitions (one per workflow) |
| `docs/` | Guidelines, decision records, playbooks, prompt conventions, knowledge base |
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

| Agent | Input | Output | Knowledge |
|-------|-------|--------|-----------|
| `agent-a11y-audit` | Figma screen / component | WCAG AA issues table, severity, fix | `ux-ui-reference.md` §6 |
| `agent-ds-linter` | Figma screen / component | Strict violations + soft recommendations | `design-systems.md` §2–3, §7 |

### Planned

| Agent | Input | Output | Knowledge |
|-------|-------|--------|-----------|
| `agent-problem-framing` | Product brief | Problem statement, hypotheses, KPIs | — |
| `agent-ux-research-synthesizer` | Interview notes / analytics | Personas, journey map, insights, JTBD | `ux-ui-reference.md` §2–4 |
| `agent-flow-builder` | User stories / backlog | Mermaid flows, screen checklists | — |
| `agent-flow-qa` | Mermaid flow / screen checklist | Coverage gaps, edge cases | — |
| `agent-wireframe-to-ds` | Screen description | CSpec YAML (Bridge format) | — |
| `agent-component-finder` | Component description | Matching DS components + variants | — |
| `agent-variant-builder` | Component + variant matrix | Figma variants via Bridge | — |
| `agent-ds-strategy` | Business context, team size, maturity | DS vision, principles, governance, KPIs, roadmap | `design-systems.md` §5–8 |
| `agent-stakeholder-comms` | DS changes, audience, output type | Newsletter, release notes, pitch outline | `design-systems.md` §6–7 |
| `agent-figma-ds-sync` | Active Figma file | Design token JSON / CSS variables | — |
| `agent-ds-linter` | Figma maquette | Off-DS usage report | `design-systems.md` §2–3, §7 |
| `agent-ds-backlog-manager` | Component request list | Prioritised backlog | — |
| `agent-ds-onboarding` | Role, DS experience level | Reading path, agent map, day-1 checklist | All `docs/resources/` |
| `agent-usage-coach` | Screen description | Recommended DS patterns | — |
| `agent-storybook-linker` | Figma components | Storybook story map | — |
| `agent-doc-writer` | Maquettes + flows | Functional specs, DS docs | — |
| `agent-design-decision-logger` | Bridge fix diff | Decision record in `docs/decisions/` | — |
| `agent-experiment-designer` | Design decision / metric | A/B test plan, iteration roadmap | — |
| `agent-ds-librarian` | Free-text DS/UX question | Cited answer + deeper reading pointer | All `docs/resources/` |

Full spec for every agent (role, inputs, outputs, tools, rules): `docs/agents.md`

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
├── decisions/    # ADR / DSDR — architectural and design decisions
├── design/       # UI/UX rules, DS guidelines, component conventions
├── architecture/ # Stack decisions, tool integrations, data formats
├── workflows/    # Process playbooks by role
├── prompts/      # Agent prompt conventions and templates
└── resources/    # Knowledge base — synthesised from /pdfs/
```

## Tool integration model

- **Bridge** (`/design-workflow`) handles all Figma frame/component/screen generation.
- **figma-cli** handles lint, a11y audit, token export, Storybook export, batch ops.
- They are complementary — not interchangeable.
- CSpec YAML (Bridge format) is the canonical exchange format between agents that touch Figma.
- See `docs/decisions/002-bridge-vs-figma-cli.md` for the rationale.

## Vision

Full vision and agent roadmap: `INIT.md`

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project vision

Meta-repo for AI agents and tools targeting product designers, UI designers, and design system managers. Full vision and agent roadmap in `INIT.md`.

---

## Repo structure

```
source-agents/
├── figma-cli/          # figma-ds-cli — main tool, see figma-cli/CLAUDE.md
├── agents/             # Concrete agent implementations (one dir per agent)
├── docs/
│   ├── agents.md       # Canonical agent index — read before creating/modifying agents
│   ├── decisions/      # ADR / DSDR — read before proposing any design or architecture
│   ├── architecture/   # Stack decisions, tool integrations, data formats
│   ├── design/         # UI/UX rules, DS conventions, JSX pitfalls
│   ├── resources/      # Synthesised knowledge base (knowledge-index.md, design-systems.md, ux-ui-reference.md)
│   ├── workflows/      # Role-based playbooks (product designer, DS manager)
│   └── prompts/        # Agent prompt conventions and tool assignment rules
├── pdfs/               # Reference library (Atomic Design, DS Handbook, etc.)
├── CHANGELOG.md        # Timeline of noteworthy changes and decisions
└── .agents/skills/     # Claude Code skill files
```

---

## Memory model

This repo IS the long-term memory. There is no hidden state between sessions.

| File / dir | What it holds |
|------------|---------------|
| `README.md` | Project overview, agent table, tool model |
| `CHANGELOG.md` | Timeline of notable changes |
| `docs/decisions/` | Decision records (ADR/DSDR) — authoritative |
| `docs/architecture/` | Stack, data flow, integration constraints |
| `docs/design/` | UI/UX and DS conventions |
| `docs/resources/` | Synthesised design knowledge base (ADR 003) — agents reference this, not raw PDFs |
| `docs/workflows/` | Role playbooks |
| `docs/prompts/` | Agent conventions, tool assignment |
| `docs/agents.md` | Canonical agent index |

**Before making significant changes or proposing new structures:** read the relevant files under `docs/` for the topic. Prefer aligning with existing decisions. Only propose new patterns when they clearly improve the system, and record them.

---

## Task protocol (for every non-trivial request)

1. **Clarify** — restate what was understood, ask focused questions when ambiguous, surface trade-offs.
2. **Plan** — propose a short checklist of steps, ask for confirmation before going deep (unless the task is clearly tiny).
3. **Execute** — mark checklist items as done (`[x]`), briefly recap at logical boundaries, pause before irreversible changes.
4. **Close** — short summary: what was asked, what was done, what changed in the repo.

---

## Correction protocol

When a pattern or decision is corrected:

1. Create or update a decision record in `docs/decisions/` (ADR format from `docs/decisions/README.md`).
2. Update the relevant guideline file: `docs/design/`, `docs/architecture/`, `docs/workflows/`, or `docs/prompts/`.
3. Update `CHANGELOG.md` if the change has visible impact.
4. State in the reply that the new rule is now the default.

---

## Agent protocol

Before creating or modifying an agent:

1. Read `docs/agents.md` for the current agent list, roles, inputs, outputs.
2. Read `docs/prompts/agent-conventions.md` for structure and tool assignment rules.
3. If deviating from conventions, explain why and record the deviation as a decision.
4. Flag any inconsistencies between agents, docs, and defined workflows — propose a resolution.

For any work involving agents, first read `agents/README.md` and
the specific `instructions.md` for the agent you are modifying
or creating.

---

## Tool assignment rules

- **Bridge** (`/design-workflow`): all Figma frame/component/screen creation. Never raw Plugin API.
- **figma-cli**: everything else — lint, a11y audit, token export, Storybook export, batch ops, library import.
- They are complementary, not interchangeable. See ADR 002.

---

## figma-cli setup

```bash
cd figma-cli
npm install
figma-cli connect        # Yolo mode (recommended) — patches Figma once
figma-cli connect --safe # Safe mode — plugin-based, no binary modification
npm test                 # node --test tests/*.test.js
```

Daemon runs on port 3456. Full command reference in `figma-cli/CLAUDE.md`.

## figma-cli architecture

| File | Role |
|------|------|
| `src/index.js` | CLI entry — all commands via Commander |
| `src/figma-client.js` | WebSocket client to the Figma daemon |
| `src/figma-patch.js` | Yolo mode — patches/unpatches Figma binary for CDP |
| `src/daemon.js` | Daemon server (port 3456) — bridges CLI to Figma |
| `src/shadcn.js` | shadcn/ui component definitions (30 components, 58 variants) |
| `src/platform.js` | macOS/Windows abstractions |
| `src/blocks/` | Pre-built layout blocks (e.g. dashboard-01) |

---

## Text output rules

- No em-dashes (—): replace with a comma or rewrite.
- No filler phrases ("It's worth noting", "Let's dive into").
- Minimum viable length — no padding, no trailing summaries.

---

## Session setup sequence

1. `cd figma-cli && npm install`
2. `figma-cli connect`
3. Run `/design-workflow setup` in Bridge to index the DS from the active Figma file.
4. All agents that touch components depend on step 3.


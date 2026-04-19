# Changelog

Noteworthy changes, decisions, and structural shifts in the repo.
Format: `YYYY-MM-DD | Category | Description`

---

## 2026-04-19 (4)

### Design knowledge base + agent wiring

- Added 6 resources in `/pdfs/` as the official design knowledge base (ADR 003)
- Created `docs/resources/knowledge-index.md` — master index of all resources with themes, best-use bullets, target roles
- Created `docs/resources/design-systems.md` — synthesised principles from 5 DS books (Frost, Kholmatova, Perez-Cruz, Idean France, InVision)
- Created `docs/resources/ux-ui-reference.md` — synthesised UX/UI concepts from Henderson EPUB (research, IA, ideation, a11y, usability, testing, AI)
- Created `docs/decisions/003-design-knowledge-base.md` — ADR establishing `/pdfs/` as knowledge base with usage conventions
- Created agents: `agent-ds-strategy`, `agent-ux-research-synthesizer`, `agent-ds-librarian`, `agent-ds-onboarding`, `agent-stakeholder-comms`
- Updated agents: `agent-a11y-audit`, `agent-ds-linter` — both now reference `docs/resources/` in their memory section
- Updated `docs/agents.md` — all 7 agents carry a `Knowledge:` field
- Updated `docs/prompts/agent-conventions.md` — knowledge base usage rules added to memory model

---

## 2026-04-19 (3)

### agent-ds-linter — second stable agent

- Created `agents/agent-ds-linter/instructions.md` — DS QA agent with two-tier finding model (strict violations / soft recommendations), per-category analysis checklist (components, tokens, variants, layout, naming), clarification questions, figma-cli tool rules, and self-correction protocol
- Created `docs/design/ds-lint-rules.md` — authoritative DS lint ruleset with strict and soft rules per category; includes shadcn token reference and revision history table
- Updated `docs/agents.md` — agent-ds-linter status: planned → stable, expanded input/output/rules fields

---

## 2026-04-19 (2)

### agent-a11y-audit — first stable agent

- Created `agents/agent-a11y-audit/instructions.md` — full WCAG AA audit agent with clarification questions, severity model, per-category checklist, and self-correction protocol
- Created `docs/design/accessibility-checklist.md` — authoritative a11y rules (contrast, touch targets, focus, text alternatives, semantics, motion); includes revision history table
- Updated `docs/agents.md` — agent-a11y-audit status: planned → stable, expanded input/output/rules fields

---

## 2026-04-19

### Repo bootstrap

- Created root repo structure: `figma-cli/`, `agents/`, `docs/`, `pdfs/`, `.agents/skills/`
- Added `README.md`, `CLAUDE.md`, `.gitignore`
- Created `docs/` knowledge base:
  - `docs/decisions/` with ADR template and first two decision records
  - `docs/architecture/stack.md`
  - `docs/design/conventions.md`
  - `docs/workflows/playbook-product-designer.md`
  - `docs/workflows/playbook-ds-manager.md`
  - `docs/prompts/agent-conventions.md`
- Fixed INIT.md heading structure (sections 9, 10, 11 were malformed `###`)

### Memory and protocol

- Adopted `docs/` as the long-term memory system (no hidden state)
- Adopted CSpec YAML as the inter-agent exchange format for Figma content (ADR 001)
- Adopted Bridge-for-creation / figma-cli-for-audits split (ADR 002)
- Integrated `suite.md` protocol: task checklists, correction learning, agent conventions, default reading behaviour
- Created `docs/agents.md` as the canonical agent index
- Added `CHANGELOG.md` (this file)

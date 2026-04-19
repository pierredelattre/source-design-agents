# Playbook — Design System Manager

Covers governance, maintenance, and adoption of the design system.

## 1. Governance and vision

**Agent:** `agent-ds-strategy`
**Input:** Business context, team size, product maturity
**Output:** DS vision, principles, OKRs, roadmap

**Agent:** `agent-stakeholder-comms`
**Output:** DS newsletters, release notes, pitch decks for evangelization

## 2. Library maintenance

**Token sync:** `agent-figma-ds-sync` exports Figma variables to Style Dictionary JSON / CSS variables.

**DS lint:** `agent-ds-linter` inspects a maquette and flags off-DS usage (duplicate components, hardcoded values, missing states). Uses `fig-start lint` under the hood.

**Backlog:** `agent-ds-backlog-manager` triages incoming requests and prioritizes by impact and technical debt.

## 3. Component lifecycle

1. Request comes in via backlog.
2. `agent-wireframe-to-ds` checks if an existing component can cover the need.
3. If not, new component: Bridge for design (CSpec → compiler → Figma), then `agent-doc-writer` for documentation.
4. `agent-variant-builder` generates all required variants.
5. `agent-a11y-audit` runs before the component is marked stable.
6. `agent-storybook-linker` maps the Figma component to its story.

## 4. Adoption and support

**Agent:** `agent-ds-onboarding`
**Input:** Role (designer / developer)
**Output:** Onboarding path, starter kit, reading list from `pdfs/`

**Agent:** `agent-usage-coach`
**Input:** Maquette or feature description
**Output:** Recommended DS patterns, anti-patterns to avoid

## 5. Decision logging

Every significant DS decision (new component, breaking change, deprecation) must produce a decision record in `docs/decisions/`. Use `agent-design-decision-logger` or create the file manually using the template in `docs/decisions/README.md`.

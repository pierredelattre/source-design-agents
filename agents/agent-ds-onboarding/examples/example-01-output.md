# Onboarding path: Frontend developer — beginner

## Day 1 checklist

- [ ] Read `docs/resources/design-systems.md` §1–§2 — what a DS is and why it exists
- [ ] Open the Figma file and locate the component library (ask your designer for the link)
- [ ] Run `figma-cli connect` to link the CLI to the active Figma file
- [ ] Run `fig-start var list` — read the token list; understand the naming convention
- [ ] Open Storybook and browse the existing component stories
- [ ] Build a simple form using only DS components — do not write custom styles

## Reading path

| Order | Resource | Why |
|-------|----------|-----|
| 1 | `docs/resources/design-systems.md` §1–§3 | Foundations: what tokens are, how components are structured |
| 2 | `docs/design/conventions.md` | Naming rules, token usage, what to avoid |
| 3 | `docs/resources/ux-ui-reference.md` §1 | Basic UX vocabulary so you understand design intent |
| 4 | `docs/decisions/` (skim) | Active constraints and decisions that affect your work |

## Agent map — tools available to you

| Agent | When to use |
|-------|-------------|
| `agent-component-finder` | "Which component should I use for X?" |
| `agent-ds-linter` | Check a screen for DS compliance before shipping |
| `agent-usage-coach` | Get pattern recommendations for a feature you're building |
| `agent-ds-librarian` | Quick DS or UX question with a cited answer |

## Key vocabulary

| Term | Meaning |
|------|---------|
| Token | A named design value (e.g. `$color/primary/default`). Use tokens, never hardcode hex or px. |
| Component | A reusable UI building block defined in Figma and implemented in Storybook. |
| Variant | A specific configuration of a component (e.g. `size=md/state=loading`). |
| CSpec YAML | The format Bridge uses to describe Figma scenes. Not your concern as a dev — designers produce it. |
| ADR | Architectural Decision Record — documents why a DS decision was made. Read before overriding anything. |

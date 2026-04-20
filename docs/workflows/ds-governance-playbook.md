# Playbook — DS Governance and Contribution

Covers how the design system is governed, how contributions are handled, and how the DS team stays in a curator role rather than a gatekeeper role.

Grounded in: `docs/resources/design-systems.md` §5–8, §10 (Kholmatova, Idean, Perez-Cruz, InVision).

---

## 1. Governance model

This repo uses a **federated model** (Idean, Perez-Cruz): product squads can propose and contribute components; the DS team curates and publishes.

The DS team is an enabler, not a police force. Its job is to lower the cost of contribution, not to own all output.

Two failure modes to avoid:

- **Over-centralised**: the DS team becomes a bottleneck; squads fork components silently because requests go unanswered.
- **Under-governed**: anyone can merge anything; the DS drifts into incoherence because there is no shared standard.

The federated model threads this by separating *contribution* (open, encouraged) from *curation* (owned by the DS team).

---

## 2. Contribution intake

Every proposed addition or change must go through a lightweight intake process. No process = the fork incentive dominates.

### Step 1: Check if it already exists

Before opening a request, run:

```bash
fig-start find "<component description>"
```

Or ask `agent-component-finder`. Many requests are for components that exist under a different name.

### Step 2: Open a contribution request

File a request in `docs/contributions/requests/` using the template below. The DS team commits to acknowledging requests within 5 working days.

**Template: `docs/contributions/requests/YYYY-MM-DD-<component-name>.md`**

```markdown
# Contribution request: <Component name>

**Date:** YYYY-MM-DD
**Requester:** <name, squad>
**Type:** New component | New variant | Token change | Deprecation | Bug fix

## Problem
What design or engineering problem does this solve? Who encounters it?

## Proposed solution
Describe the component, variant, or change. Include a Figma link or sketch if available.

## Existing alternatives considered
What did you find when you searched? Why do they not cover this case?

## Impact estimate
How many squads or screens would benefit?

## Acceptance criteria
What does "done" look like?
```

### Step 3: DS team triage

The DS team reviews the request within 5 working days and assigns one of three outcomes:

| Outcome | Meaning | Next step |
|---------|---------|-----------|
| Accept | Will be built and published by the DS team | Added to the DS backlog |
| Delegate | Requester builds it under DS team guidance | Starts co-design process |
| Decline | Out of scope or covered by an existing pattern | Written rationale provided |

"Decline" always includes a written rationale. Silent declines are not acceptable.

---

## 3. Component lifecycle

Once a request is accepted or delegated:

1. `agent-wireframe-to-ds` checks if an existing component can cover the need with a new variant.
2. If not: Bridge (`/design-workflow`) for Figma design, CSpec YAML as the exchange format (ADR 001).
3. `agent-variant-builder` generates all required states and variants.
4. `agent-a11y-audit` runs before the component is marked stable. No component ships without an a11y pass.
5. `agent-doc-writer` generates the usage documentation (when to use, when not to use, token overrides).
6. `agent-storybook-linker` maps the component to its Storybook story.
7. The component is published and announced in the changelog.

---

## 4. Versioning and deprecation

- All releases follow semantic versioning (patch / minor / major).
- Breaking changes require a major version bump and a migration guide.
- Deprecated props are announced in the changelog and carry a console warning in the React component for at least one minor version before removal.
- The `tone` prop pattern (aliased to `palette` in Badge, Tag, Chip) is the canonical example of what deprecation without a removal date looks like. Avoid repeating it.

---

## 5. Shared language

A DS without consistent naming drifts. Naming conflicts are a leading indicator of fragmentation (Kholmatova).

Rules:
- Component names must be identical in Figma, the React package, and all documentation. No synonyms, no aliases in active use.
- When a name changes, a codemod or migration guide ships with the change.
- An interface inventory (audit of names in use across Figma files and the codebase) should run at least once per quarter to surface divergences before they calcify.
- The token glossary in `docs/design/conventions.md` is the authoritative definition of each token group's intent. Update it whenever a new semantic token is added.

---

## 6. Communication

Adoption does not happen automatically after a component ships. Communication is a first-class DS responsibility (Idean).

Minimum communication cadence:

| Artefact | Frequency | Owner | Agent |
|----------|-----------|-------|-------|
| Changelog entry | Every release | DS team | Manual |
| Release summary (Slack / email) | Every minor or major release | DS team | `agent-stakeholder-comms` |
| DS newsletter | Quarterly | DS team | `agent-stakeholder-comms` |
| Office hours | Monthly | DS team | None (human meeting) |

Release summaries must include: what changed, what it replaces, and how to migrate. "New component added" is not a sufficient announcement.

---

## 7. Health metrics

You cannot govern what you cannot measure (Idean). Minimum metrics to track:

| Metric | Description | Source |
|--------|-------------|--------|
| Adoption rate | % of product screens using DS components | figma-cli scan or codebase import audit |
| Fork count | Number of known DS-component forks in squad codebases | Manual audit or codebase grep |
| Debt delta | New non-DS patterns introduced per sprint | `agent-ds-linter` output |
| Request response rate | % of contribution requests acknowledged within 5 days | `docs/contributions/requests/` |
| A11y score | % of DS components with a passing a11y audit | `agent-a11y-audit` log |

Review these metrics before each quarterly DS planning cycle.

---

## 8. When the DS stifles creativity

Healthy tension between consistency and expression is a feature (Perez-Cruz). If designers consistently work around the DS, the system has a problem, not the designers.

Signals to watch for:
- Repeated requests for the same gap with no resolution.
- Figma components detached from the library at a high rate.
- A growing list of squad-level forks.
- Designers adding "polish" on top of DS components to make them presentable.

When these signals appear, run an expressiveness audit: check whether the DS has a purpose statement, supports a visible range of expression, and makes deviation principled rather than forbidden.

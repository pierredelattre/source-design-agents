# 004 — DS Governance Playbook

**Status:** Accepted
**Date:** 2026-04-20

## Context

The repo had no documented governance or contribution model. `docs/workflows/playbook-ds-manager.md` referenced a component lifecycle but skipped the intake step — how a request gets into that lifecycle in the first place. UX research synthesis (test6 session) confirmed this gap was causing real fragmentation: at least one tech lead had forked two components after receiving no response to contribution requests, and the DS lead had no adoption metrics.

## Decision

Create `docs/workflows/ds-governance-playbook.md` as the authoritative governance reference for this repo. It covers:

- The federated governance model and its rationale
- Contribution intake process (template, triage outcomes, response SLA)
- Component lifecycle tied to existing agents
- Versioning and deprecation policy
- Shared language rules
- Communication cadence
- Health metrics
- Signals that the DS is over-rigid

## Rationale

The playbook is grounded in five sources from `docs/resources/design-systems.md`:

- **Kholmatova** (§7): shared language as a first-class DS concern; naming drift as an early fragmentation signal.
- **Idean** (§6): strict vs. loose governance archetypes; communication as a DS responsibility; KPI tracking.
- **Perez-Cruz** (§4, §10): federated model over centralised; expressiveness as a design system quality; over-rigidity as a failure mode.
- **InVision Handbook** (§8): end-to-end DS creation and scaling arc; contribution model at scale.
- **Frost** (§2): component hierarchy as the unit of work; lifecycle framing.

The federated model was chosen over a strict centralised model because the research synthesis showed that centralisation was already failing (requests unanswered, forks proliferating). A loose model was ruled out because the DS lead had no visibility into adoption and the shared language was already drifting.

## Consequences

**Positive:**
- Agents that touch governance (`agent-ds-backlog-manager`, `agent-stakeholder-comms`, `agent-design-decision-logger`) have a playbook to reference.
- The contribution intake template is now a concrete artefact that `agent-ds-backlog-manager` can use as its primary input format.
- The health metrics section provides a framework for the DS adoption dashboard described in earlier sessions.

**Negative:**
- The `docs/contributions/requests/` directory referenced in the playbook does not exist yet and must be created before the intake process can be used.
- The 5-day response SLA is aspirational for a solo or small DS team; it must be revisited if team capacity does not support it.

## Agent usage

| Agent | How to use this playbook |
|-------|--------------------------|
| `agent-ds-strategy` | Read §1 (governance model) and §7 (health metrics) before proposing any DS organisational change |
| `agent-ds-backlog-manager` | Use §2 (contribution intake) as the input format definition; use §3 (component lifecycle) as the processing pipeline |
| `agent-stakeholder-comms` | Use §6 (communication) for cadence and content requirements |
| `agent-ds-linter` | §7 (health metrics) — debt delta is one of the metrics this agent produces |
| `agent-a11y-audit` | §3 (component lifecycle) — a11y audit is a mandatory gate before any component is marked stable |

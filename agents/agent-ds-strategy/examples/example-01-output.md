# DS Strategy: Early-stage B2B SaaS

## Vision

A lean, token-first design system that closes the design-to-code gap, reduces designer-engineer rework, and gives the product a consistent, professional face ahead of Series A.

## Principles

1. **Token-first.** Every visual decision is a token. No hardcoded values in Figma or code.
2. **Single source of truth.** Figma is the design source; Storybook is the code source. They must stay in sync.
3. **Small and stable beats large and unstable.** Ship 15 well-documented components before expanding to 40.
4. **Documentation is part of the component.** A component without usage guidance does not exist.
5. **Designers and engineers co-own the DS.** No DS changes without both signing off.

## Governance model

**Phase 1 — Foundation (months 1–2):** One designer owns DS. Define token system (color, spacing, typography). Migrate the 15 most-used components. No committee — move fast.

**Phase 2 — Adoption (months 3–4):** Storybook setup. Each new feature uses DS components only. Deviations require a written reason.

**Phase 3 — Maintenance (months 5–6):** Weekly DS sync (30 min). Backlog triage via `agent-ds-backlog-manager`. Breaking changes need ADR.

## KPIs

| KPI | Baseline | Target (6 months) |
|-----|----------|-------------------|
| Component coverage (% of product using DS components) | ~30% | ≥80% |
| Token adoption (% of styles using tokens) | ~0% | 100% in new work |
| Design-to-code rework incidents | Unknown | −50% (track via sprint retros) |
| Storybook story coverage | 0 | ≥15 components |

## Roadmap

| Month | Milestone |
|-------|-----------|
| 1 | Token system defined and published (Figma + Style Dictionary) |
| 2 | 15 core components documented in Figma |
| 3 | Storybook set up; first 8 components with stories |
| 4 | All new product work uses DS components only |
| 5 | Full token adoption audit; remaining gaps closed |
| 6 | DS presented at Series A deck as product maturity signal |

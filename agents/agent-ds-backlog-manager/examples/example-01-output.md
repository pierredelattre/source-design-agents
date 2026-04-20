# DS Backlog — 2026-04-20

## Priority queue

| Rank | Request | Impact | Effort | Priority | Notes |
|------|---------|--------|--------|----------|-------|
| 1 | Toast notification | High — 3 teams, core async feedback pattern | Medium — new component, 4 variants (neutral/success/warning/error) | Ship next | Blocks multiple in-flight features |
| 2 | Avatar with initials fallback | High — 2 active features blocked | Low — variant addition to likely existing Avatar | Ship next | Check if Avatar component exists first; may just be a missing variant |
| 3 | Button `size=xl` | Medium — 1 designer, hero CTA use case | Low — variant addition to existing Button | Plan | Low effort, add to next component cycle |
| 4 | Data table (sortable) | High — analytics team | High — complex component, accessibility-heavy | Plan | Requires ADR before implementation; sortable columns + keyboard navigation scope is large |
| 5 | Tooltip | Low — developer request, no active use case cited | Low | Deferred | No product urgency; add when a real use case appears |

## Duplicates / already covered

- **Primary button with icon** (#6): covered by `Button/Primary` with `leadingIcon` prop — close request and point requester to the existing variant.

## Requests requiring a DS decision

- **Data table**: needs an ADR defining scope (sorting, pagination, row selection, responsive behaviour) before implementation.

## Deferred

- Tooltip: low impact until a concrete feature use case is filed.

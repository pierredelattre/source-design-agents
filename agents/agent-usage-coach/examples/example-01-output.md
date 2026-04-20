# Usage coach: Analytics dashboard

## Recommended patterns

| Zone | Component | Variant | Rationale |
|------|-----------|---------|-----------|
| Date range picker | DateRangePicker | size=md | Standard date input pattern; avoid building custom — keyboard a11y is complex |
| KPI cards | Card/Stat | size=md, trend=positive/negative/neutral | Use the DS stat card if available; exposes trend icon and colour via intent token |
| Line chart | Chart/Line | — | If DS has a chart component, use it; if not, use a validated library (Recharts, Victory) with DS color tokens for series colours |
| Data table | Table/Sortable | density=default | Use the DS table; do not build custom sort logic — sort state and keyboard handling should be in the component |
| Page layout | Grid/12col | gap=$spacing/5 | Use a 12-column grid; KPI cards = 3 cols each, chart = 8 cols, table = 12 cols |

## Anti-patterns to avoid

| Anti-pattern | Why | Alternative |
|--------------|-----|-------------|
| Custom card component for KPI stats | Creates drift; hardcoded shadows and radii break token consistency | Use `$comp/Card/Stat` or compose with `$shadow/sm` + `$radius/md` tokens |
| Hardcoded chart colours (`#ff0000`) | Breaks dark mode and colour-blind modes | Use `$color/chart/series-1` through `/series-5` tokens |
| Building a custom date picker | Date inputs require significant a11y work (ARIA, keyboard, screen reader) | Use the DS `DateRangePicker` or a well-tested library |

## DS tips for this context

- On dashboards, prioritise visual hierarchy: KPI cards should draw the eye first, then the chart, then the table. Use `$spacing/6` between sections, `$spacing/4` within.
- Avoid more than 5 chart series — beyond that, colour coding becomes ambiguous for users with colour vision deficiencies.
- If the data table can have 0 rows, design the empty state now — do not leave it for later.

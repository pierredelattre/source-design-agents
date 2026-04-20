# Experiment plan: Pricing page CTA — size and position

## Hypothesis

If we increase the primary CTA to `size=xl` and position it above the fold, then the click-through rate will increase from 8% to at least 10% (a relative lift of +25%) because reducing scroll friction and increasing visual prominence will capture more intent at the moment of highest attention.

## Setup

| Field | Value |
|-------|-------|
| Control | Existing CTA: `size=md`, positioned below the pricing cards |
| Variant | CTA: `size=xl`, positioned above the pricing cards (above the fold on 1280px viewport) |
| Primary metric | CTA click-through rate (clicks / unique visitors) |
| Guardrail metrics | Bounce rate (must not increase), scroll depth (monitor for engagement drop) |
| Success threshold | CTR ≥ 10% with p < 0.05 (two-tailed) |
| Estimated sample size | ~3,800 per variant (assumes σ = 0.08, δ = 0.02, 95% confidence, 80% power) |
| Estimated duration | ~2 weeks at 5,000 visitors/week (split 50/50) |

## Iteration roadmap (if test confirms hypothesis)

1. Ship `size=xl` + above-fold position as default.
2. Test CTA copy variants (e.g. "Start free trial" vs "See plans") — same traffic, same setup.
3. Test social proof element (logo bar) adjacent to the CTA — measure incremental lift.

## Risks and assumptions

- Above-fold position may hide pricing context that users need before clicking — monitor scroll depth as a guardrail.
- The effect may differ for mobile users (viewport differences); segment results by device.
- 2-week duration assumes stable traffic; any marketing campaign during the test window will skew results — coordinate with the growth team.

## Engineering requirements

- A/B flag controlling CTA size and vertical position on the pricing page.
- Event tracking: `cta_click` with `variant` property (`control` / `xl-above-fold`).
- Session recording enabled for both variants during the test window.

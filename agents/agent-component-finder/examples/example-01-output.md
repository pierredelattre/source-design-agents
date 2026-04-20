# Component search: "Primary form submit button with loading state"

## Matches

| Rank | Component | Variant | Fit | Notes |
|------|-----------|---------|-----|-------|
| 1 | Button/Primary | size=lg, emphasis=high, state=loading | Exact | Use `state=loading` to show spinner; disable interaction automatically |
| 2 | Button/Primary | size=md, emphasis=high, state=loading | Semantic | Use if lg feels too large on the screen's layout grid |

## Missing components

None — loading state is covered by the DS Button component.

## Recommended usage

On a checkout confirmation screen, use `Button/Primary` at `size=lg` as the sole high-emphasis action. Set `state=loading` on form submit and revert to `state=default` or `state=error` based on the API response. Do not place a second high-emphasis button on the same screen — pair with a text-only secondary action (e.g. "Back") if a cancel option is needed.

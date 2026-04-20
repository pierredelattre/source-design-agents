# Storybook link map — 2026-04-20

## Linked

| Figma component | Storybook story | Variants coverage | Notes |
|-----------------|-----------------|-------------------|-------|
| Button/Primary | components/Button | 3/8 variants | Missing: sm, md, lg size splits; hover state |
| Button/Secondary | components/Button | 2/4 variants (inferred) | Secondary not split into its own story — merged with Primary |
| Badge | components/Badge/Neutral, components/Badge/Success | 3/20 variants | Only 2 intents covered; warning/error/info missing entirely |

## Missing stories (Figma → no story)

| Component | Priority | Variants to cover |
|-----------|----------|-------------------|
| Avatar | High | sm, md, lg — all missing |
| Badge/Warning | Medium | filled, outline |
| Badge/Error | Medium | filled, outline |
| Badge/Info | Low | filled, outline |
| Button size variants (sm, lg) | Medium | default, disabled, loading per size |

## Orphaned stories (story → no Figma component)

None.

## Open questions

- Should Button/Primary and Button/Secondary be separate stories or a single story with a `variant` arg? Aligning with the Figma naming would mean two stories.
- Badge/Success only has a `Filled` story — is `Outline` intentionally skipped or just missing?

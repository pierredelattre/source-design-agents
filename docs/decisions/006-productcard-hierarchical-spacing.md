# 006 ProductCard hierarchical spacing instead of flat gaps

**Status:** Proposed
**Date:** 2026-04-20

## Context

`ProductCard` currently uses a flat 8px gap between all children, regardless of semantic grouping. This makes title/subtitle, body content, and actions appear equally related, which weakens content hierarchy and scanability.

The DS needs spacing that reinforces visual grouping inside cards:
- tight grouping for strongly related text (for example title + subtitle),
- medium separation between content regions (header/body/actions),
- clear but controlled distance before actions.

## Decision

Adopt hierarchical spacing for `ProductCard` as a global DS rule and stop using a uniform 8px gap across all card children.

For `ProductCard`:
- Group related header text (title + subtitle) with a tighter internal spacing token.
- Separate major sections (header, body, actions) with larger section-spacing tokens.
- Keep spacing token-based (no hardcoded pixel values in component implementation/spec).

This rule applies to all `ProductCard` instances and future variants unless a documented exception is approved.

## Rationale

- Visual hierarchy is a primary cue for comprehension; flat spacing creates ambiguous grouping.
- Hierarchical spacing improves scan speed by making structure obvious at a glance.
- Tokenized spacing keeps behavior consistent across variants, themes, and future refactors.
- A global rule prevents repeated local fixes and design drift in card components.

## Consequences

Positive:
- Better readability and perceived structure in card-based UIs.
- Clearer DS guidance for card composition and spacing semantics.
- Reduced future lint/design review feedback on card spacing.

Trade-offs:
- Existing `ProductCard` usages may require updates to align with section-based spacing.
- Teams must follow semantic spacing guidance instead of defaulting to a single gap value.

## Related files to update

- `docs/design/spacing-guidelines.md` (or current DS spacing guideline doc): add card-internal hierarchy guidance and token mapping examples.
- `docs/design/components/card.md` (or current card spec doc): update `ProductCard` anatomy/spec to define header/body/actions spacing tokens and grouping rules.

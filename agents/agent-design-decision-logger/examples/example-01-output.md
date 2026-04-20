# ADR 004: All Button variants use `$radius/md` for border-radius

**Date:** 2026-04-20
**Status:** Accepted
**Deciders:** DS team

## Context

During a DS lint run, Button/Primary was found to use a hardcoded `4px` border-radius value introduced during a fast fix. This violates the token-first principle and creates drift when the radius token is updated globally.

## Decision

All Button variants must use `$radius/md` for border-radius. Hardcoded pixel values are not permitted in any Button CSpec or code implementation.

## Rationale

Token-first is a core DS principle (see DS Strategy). A global radius change should propagate automatically to all components — hardcoded values break this invariant and require manual updates in every affected file.

## Consequences

- All Button variants in Figma updated to use `$radius/md`.
- Storybook Button component updated to reference the CSS variable `--radius-md`.
- `docs/design/conventions.md` updated to explicitly state: "Never hardcode border-radius in Button components."
- Future lint runs will flag `4px` as a violation in Button contexts.

## Alternatives considered

- **Keep `4px` as an exception**: rejected — no product reason to deviate from the token; creates a maintenance burden.

---

## Files to update

- [ ] `docs/design/conventions.md` — add rule: Button border-radius must use `$radius/md`
- [ ] `CHANGELOG.md` — note the correction and ADR number

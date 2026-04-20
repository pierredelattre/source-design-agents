# DS Release Note — v1.2.0

**Date:** 2026-04-20
**Audience:** Product designers, frontend engineers

---

## What's new

### Button — `size=xl` and `state=loading`

All Button emphasis levels (high, medium, low) now support:
- `size=xl` for hero CTAs and full-width mobile actions
- `state=loading` — replaces label with a spinner and disables interaction automatically

**Designers:** Use `state=loading` directly in Figma prototypes to show in-flight states. No custom spinner needed.
**Engineers:** `<Button size="xl" loading />` handles the spinner and disabled state.

### Badge — new component

20 variants: 2 sizes (sm, md) × 5 intents (neutral, info, success, warning, error) × 2 styles (filled, outline).

Use Badge to communicate status, labels, or counts inline with text or in table cells.

---

## Breaking change — color token rename

`$color/brand/500` has been renamed to `$color/primary/default`.

**Action required:**
- **Designers:** Run a Figma "Find and replace" on styles. The old style has been removed from the library.
- **Engineers:** Update all references in CSS/JS. Search for `brand-500` or `--color-brand-500` in your codebase.

If you have questions or hit blockers, post in #design-system.

---

## Migration checklist

- [ ] Replace `$color/brand/500` with `$color/primary/default` in Figma
- [ ] Update `--color-brand-500` CSS variable references in code
- [ ] Review any hardcoded hex values that matched the old brand color (`#3b82f6`)

# Accessibility checklist

Authoritative a11y rules for this repo. `agent-a11y-audit` reads this file at the start of every session. When a rule is corrected, update this file, the agent's `instructions.md`, and create a decision record in `docs/decisions/`.

**Standard:** WCAG 2.1 Level AA

---

## Contrast

| Context | Minimum ratio | WCAG criterion |
|---------|--------------|----------------|
| Body text (< 18pt, not bold) | 4.5:1 | 1.4.3 |
| Large text (≥ 18pt or ≥ 14pt bold) | 3:1 | 1.4.3 |
| UI components (borders, icons, focus rings) | 3:1 | 1.4.11 |
| Text on images or gradients | 4.5:1 (body) / 3:1 (large) — checked at worst-case pixel | 1.4.3 |

Check both light and dark mode when both are supported.

## Touch targets

| Rule | Value | WCAG criterion |
|------|-------|----------------|
| Minimum tap area | 44x44px | 2.5.5 |
| Minimum spacing between adjacent targets | 8px | 2.5.5 |

## Focus and keyboard navigation

- Focus order must follow visual / reading order. (WCAG 2.4.3)
- Focus indicator must be visible and have ≥ 3:1 contrast against its surrounding background. (WCAG 2.4.11)
- No keyboard trap: users must be able to navigate away from any component using only the keyboard. (WCAG 2.1.2)
- All interactive elements must be reachable by keyboard (Tab / Shift+Tab / arrow keys where applicable).

## Text alternatives

- All non-decorative images must have descriptive alt text. Decorative images must be marked as such (empty alt or aria-hidden). (WCAG 1.1.1)
- Icon-only buttons must have an accessible label (aria-label or visually hidden text).
- No emoji used as icons. Use Lucide icons or geometric shape placeholders. (DS convention — `docs/design/conventions.md`)

## Structure and semantics

- Headings must follow a logical hierarchy: h1 → h2 → h3. No skipped levels.
- Form fields must have programmatically associated labels (not just placeholder text).
- Error messages must be associated with their field (aria-describedby or equivalent).

## Motion and animation

- Animations must respect `prefers-reduced-motion`. Provide a no-motion fallback for all transitions, auto-playing content, and parallax effects. (WCAG 2.3.3)

## figma-cli commands

Run these via figma-cli — do not reimplement:

```bash
fig-start a11y audit       # Full audit
fig-start a11y contrast    # Contrast only
fig-start a11y touch       # Touch targets only
fig-start a11y text        # Text-level checks
fig-start a11y vision      # Color-blindness simulation
```

---

## Revision history

| Date | Change | Decision record |
|------|--------|----------------|
| 2026-04-19 | Initial checklist created (WCAG 2.1 AA baseline) | — |

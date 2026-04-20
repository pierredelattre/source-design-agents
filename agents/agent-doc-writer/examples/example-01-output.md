# Component: Badge

## Purpose

Communicates a status, label, or count inline with content. Used in tables, list items, and alongside headings to give quick contextual information without interrupting the reading flow.

## Variants

| Axis | Values |
|------|--------|
| Size | sm, md |
| Intent | neutral, info, success, warning, error |
| Style | filled, outline |

Total: 20 combinations.

## Usage

**Do:**
- Use `intent=success` to confirm a completed state (e.g. "Published", "Verified").
- Use `intent=warning` for states that need attention but are not blocking (e.g. "Expiring soon").
- Use `intent=error` for failed or blocked states (e.g. "Failed", "Overdue").
- Use `style=outline` when the badge appears on a coloured background to avoid clashing fills.
- Use `size=sm` inside table cells; `size=md` alongside body text or headings.

**Don't:**
- Don't use Badge for interactive elements — it is display-only. Use a Tag or Chip if the user needs to remove or click it.
- Don't stack more than 2 badges side by side — it creates visual noise.
- Don't use Badge to replace a system notification — use Toast for transient feedback.

## Tokens

| Property | Token |
|----------|-------|
| Background (filled) | `$color/{intent}/surface` |
| Text (filled) | `$color/{intent}/on-surface` |
| Border (outline) | `$color/{intent}/border` |
| Text (outline) | `$color/{intent}/text` |
| Padding (sm) | `$spacing/1 $spacing/2` |
| Padding (md) | `$spacing/1.5 $spacing/3` |
| Border radius | `$radius/full` |
| Font (sm) | `$text/label/xs` |
| Font (md) | `$text/label/sm` |

## Accessibility

- Badge is presentational — it does not receive focus.
- When used to convey status in a table, ensure the status is also available as text, not only via colour (e.g. "Success" label, not just a green badge).
- Contrast must meet WCAG AA: 4.5:1 for `size=sm` text (xs label), 3:1 minimum for `size=md`.
- For screen readers, include a visually hidden description if the badge is the only status indicator in a row.

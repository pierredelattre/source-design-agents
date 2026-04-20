# DS Librarian: Overlay vs inline alert for form errors

## Answer

For a server error after form submission, use an **inline alert** at the top of the form — not a modal.

**Why inline:**
- The user is already in context (the form). An inline alert keeps their attention on the form so they can retry without navigating away.
- Modals interrupt flow and require an explicit dismissal action. For non-blocking errors that have a clear retry path, this is disproportionate.
- Inline alerts are less disruptive on mobile — a modal over a form can feel jarring and obscures the fields.

**When to use a modal instead:**
- The error is blocking and requires a decision before the user can continue (e.g. "Your session has expired — log in again or lose changes?").
- The error is not recoverable in-context (e.g. a payment requires 3D Secure and must launch an external flow).

**Practical rule** (from `docs/resources/ux-ui-reference.md` §5, Nielsen heuristic 9 — Help users recognize, diagnose, and recover from errors):
> Place error messages as close as possible to the source of the error. Reserve overlays for errors that block the entire flow, not individual interactions.

## Recommended implementation

Use `Alert/Error` (inline) at the top of the form with:
- A clear message explaining what failed (not just "Error").
- A retry CTA if the user can resubmit without changes (e.g. "Try again").
- If the error is specific to a field, also show an inline field-level error below that field.

## Deeper reading

- `docs/resources/ux-ui-reference.md` §5 — Error handling patterns and Nielsen heuristics
- `docs/design/conventions.md` — Alert component variants and when to use each

## Related agent

`agent-usage-coach` — if you want pattern recommendations for the full form screen, not just the error state.

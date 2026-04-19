# DS Lint rules

Authoritative ruleset for `agent-ds-linter`. Read this file at the start of every lint session. When a rule is corrected, update this file, the agent's `instructions.md`, and create a decision record in `docs/decisions/`.

If a rule here conflicts with a decision record in `docs/decisions/`, the decision record wins.

---

## Components

### Strict violations

| Rule | Description |
|------|-------------|
| No off-DS components | Every component on a screen must be an instance of a DS library component. Local copies or detached instances are violations. |
| No duplicate DS components | A custom component that replicates an existing DS component is a violation, regardless of visual similarity. |
| No component misuse | Using a DS component outside its intended purpose (e.g. `Badge` as a primary action button) is a violation. |

### Soft recommendations

| Rule | Description |
|------|-------------|
| Prefer DS patterns for layout | Custom frames that reproduce a DS layout pattern (card, list row, etc.) should be replaced with the DS equivalent. |

---

## Tokens

### Strict violations

| Rule | Description |
|------|-------------|
| No hardcoded colors | All fills and strokes must use DS color tokens. Hardcoded hex values are violations. |
| No hardcoded font sizes or weights | All typography must use DS text tokens. Hardcoded `px` values are violations. |
| No hardcoded border radius | Corner radius must use DS tokens. Custom values are violations unless approved by ADR. |
| Token category must match element role | `$color/foreground` on text, `$color/background` on surfaces, `$color/primary` on primary actions. Mismatched categories are violations. |

### Available shadcn token names (baseline)

Colors: `background`, `foreground`, `card`, `card-foreground`, `primary`, `primary-foreground`, `secondary`, `secondary-foreground`, `muted`, `muted-foreground`, `accent`, `accent-foreground`, `border`, `input`, `ring`

### Soft recommendations

| Rule | Description |
|------|-------------|
| Prefer semantic tokens over primitives | Using a semantic token (`$color/primary`) is preferred over a primitive (`$color/blue-600`) even when the values are equivalent. |

---

## Variants and states

### Strict violations

| Rule | Description |
|------|-------------|
| Variant must match context | The selected variant (size, emphasis, style) must match the component's role on screen. A `ghost` button used as the primary CTA is a violation. |
| Required states must be designed | Interactive components must have: default, hover, focus, active, disabled. Missing any of these before handoff is a violation. |

### Soft recommendations

| Rule | Description |
|------|-------------|
| Error and loading states | Components that can enter error or loading states should have those variants designed, even if not required for the current scope. |
| Empty states | Screens that can show an empty data set should have an empty state designed. |

---

## Layout and spacing

### Strict violations

| Rule | Description |
|------|-------------|
| Spacing must follow DS scale | Padding and gap values must use the DS spacing scale (base: 4px grid — 4, 8, 12, 16, 24, 32, 48, 64). Values outside the scale are violations unless approved. |
| Alignment must follow DS grid | Elements must align to the DS grid. Off-grid positioning is a violation. |

### Soft recommendations

| Rule | Description |
|------|-------------|
| Consistent padding within a component family | Components in the same family (card, list row, modal) should use consistent internal padding. |

---

## Naming

### Strict violations

| Rule | Description |
|------|-------------|
| No generic layer names | Layer names like "Frame 45", "Group 12", "Rectangle 3" are violations. All layers must have meaningful names. |
| No version suffixes | Names like "Button-v2", "Custom-Button", "Button-old" indicate an off-DS or iterative component. Replace with the DS component or open a backlog request. |

### Soft recommendations

| Rule | Description |
|------|-------------|
| DS naming convention | Component layers should use PascalCase matching the DS component name. Supporting layers (text, icon, background) can use camelCase or kebab-case consistently. |

---

## figma-cli commands

Run these via figma-cli — do not reimplement:

```bash
fig-start lint                  # Full lint audit
fig-start find "Custom-"        # Find layers by name pattern
fig-start canvas info           # Inspect canvas state
fig-start var list              # Cross-check token usage
```

---

## Revision history

| Date | Change | Decision record |
|------|--------|----------------|
| 2026-04-19 | Initial ruleset created (components, tokens, variants, layout, naming) | — |

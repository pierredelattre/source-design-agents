# Design conventions

## Token usage

All visual values in Figma must use semantic DS tokens (`$color/...`, `$spacing/...`, `$text/...`, `$comp/...`). No hardcoded hex, px, or font names.

Available shadcn variable names: `background`, `foreground`, `card`, `primary`, `secondary`, `muted`, `accent`, `border`, `input`, `ring`, and their `-foreground` variants.

## Component naming (Figma)

- Component sets: `ComponentName` (PascalCase)
- Variants: `property=value` (lowercase value)
- Slots: `SlotName` (PascalCase, no prefix)

## Text output rules (all agents, all docs)

- No em-dashes (—): replace with a comma or rewrite the sentence.
- No robotic filler: "It's worth noting", "Let's dive into", "Great question!" are banned.
- Minimum viable length: no padding, no trailing summary that repeats what was just said.
- No `·` as separator.

## Accessibility baseline

- Contrast: 4.5:1 for body text, 3:1 for large text and UI components (WCAG AA).
- Touch targets: minimum 44x44px.
- Focus order must follow reading order.
- No emoji as icons: use Lucide icons or geometric shape placeholders.

## JSX render pitfalls (figma-cli)

- Text must have `w="fill"` on both the parent frame and every `<Text>` element, or it clips to one line.
- Buttons need `flex="row" justify="center" items="center"` to center text.
- Use `grow={1}` spacer for push-to-edge layouts; `justify="between"` is unreliable.
- No `eval` for slot creation: use `figma-cli slot convert`.

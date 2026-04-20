# CSpec YAML: Badge — Variant set

20 variants (2 sizes × 5 intents × 2 styles). Showing representative samples; full set follows the same pattern.

```yaml
scene:
  name: "Badge — Variant set"
  componentSet:
    name: "Badge"
    variants:

      # size=sm / intent=neutral / style=filled
      - name: "size=sm/intent=neutral/style=filled"
        frame:
          padding: "$spacing/1 $spacing/2"
          radius: $radius/full
          background: $color/neutral/surface
          children:
            - text: "Label"
              style: $text/label/xs
              color: $color/neutral/on-surface

      # size=sm / intent=neutral / style=outline
      - name: "size=sm/intent=neutral/style=outline"
        frame:
          padding: "$spacing/1 $spacing/2"
          radius: $radius/full
          background: transparent
          border: "1px solid $color/neutral/border"
          children:
            - text: "Label"
              style: $text/label/xs
              color: $color/neutral/text

      # size=sm / intent=success / style=filled
      - name: "size=sm/intent=success/style=filled"
        frame:
          padding: "$spacing/1 $spacing/2"
          radius: $radius/full
          background: $color/success/surface
          children:
            - text: "Label"
              style: $text/label/xs
              color: $color/success/on-surface

      # size=md / intent=error / style=filled
      - name: "size=md/intent=error/style=filled"
        frame:
          padding: "$spacing/1.5 $spacing/3"
          radius: $radius/full
          background: $color/error/surface
          children:
            - text: "Label"
              style: $text/label/sm
              color: $color/error/on-surface

      # size=md / intent=warning / style=outline
      - name: "size=md/intent=warning/style=outline"
        frame:
          padding: "$spacing/1.5 $spacing/3"
          radius: $radius/full
          background: transparent
          border: "1px solid $color/warning/border"
          children:
            - text: "Label"
              style: $text/label/sm
              color: $color/warning/text

      # ... remaining 15 variants follow identical pattern
      # substituting $color/{intent}/*, $spacing/1 or /1.5, $text/label/xs or /sm
```

## Missing tokens

None — all referenced tokens are standard DS primitives.

## Next step

Run `agent-a11y-audit` on each intent variant to verify contrast ratios meet WCAG AA (4.5:1 for sm text).

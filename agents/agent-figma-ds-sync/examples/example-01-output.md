# Token export — Style Dictionary JSON

## tokens.json

```json
{
  "color": {
    "primary": {
      "default": { "value": "#3b82f6", "type": "color" },
      "hover":   { "value": "#2563eb", "type": "color" },
      "surface": { "value": "#eff6ff", "type": "color" },
      "on-surface": { "value": "#1e3a8a", "type": "color" }
    },
    "neutral": {
      "text":    { "value": "#111827", "type": "color" },
      "subtle":  { "value": "#6b7280", "type": "color" },
      "border":  { "value": "#e5e7eb", "type": "color" },
      "surface": { "value": "#f9fafb", "type": "color" }
    },
    "success": {
      "surface":    { "value": "#f0fdf4", "type": "color" },
      "on-surface": { "value": "#166534", "type": "color" }
    },
    "error": {
      "surface":    { "value": "#fef2f2", "type": "color" },
      "on-surface": { "value": "#991b1b", "type": "color" }
    }
  },
  "spacing": {
    "1":  { "value": "4px",  "type": "dimension" },
    "2":  { "value": "8px",  "type": "dimension" },
    "3":  { "value": "12px", "type": "dimension" },
    "4":  { "value": "16px", "type": "dimension" },
    "5":  { "value": "24px", "type": "dimension" },
    "6":  { "value": "32px", "type": "dimension" },
    "8":  { "value": "48px", "type": "dimension" },
    "10": { "value": "64px", "type": "dimension" }
  }
}
```

## Sync report

- Exported: 22 tokens
- Added: 4 (`color.primary.surface`, `color.primary.on-surface`, `color.success.*`, `color.error.*`)
- Changed: 1 (`color.primary.default`: was `#3b82f5` → `#3b82f6`)
- Removed: 1 (`color.brand.500` — renamed, see v1.2.0 release note)
- Naming mismatches: none

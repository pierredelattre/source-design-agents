# CSpec YAML: Settings — Profile section

```yaml
scene:
  name: "Settings / Profile"
  frame:
    width: 768
    height: auto
    padding: $spacing/6
    gap: $spacing/5
    direction: vertical
    children:

      # 1. Page header
      - component: $comp/PageHeader
        variant: with-back-link
        props:
          title: "Settings"
          backLabel: "Back"

      # 2. Profile section
      - component: $comp/Section
        props:
          label: "Profile"
          children:

            - component: $comp/AvatarUpload
              variant: size=lg/editable=true
              props:
                placeholder: "Upload photo"

            - component: $comp/FormField
              variant: size=md/state=default
              props:
                label: "Display name"
                inputType: text
                required: true

            - component: $comp/FormField
              variant: size=md/state=read-only
              props:
                label: "Email"
                inputType: email
                helperAction:
                  label: "Change email"
                  href: "/settings/email"

      # 3. Save button
      - component: $comp/Button
        variant: size=md/emphasis=high/state=disabled
        props:
          label: "Save changes"
          fullWidth: false

      # 4. Danger zone
      - component: $comp/Button
        variant: size=sm/emphasis=none/intent=destructive
        props:
          label: "Delete account"
          fullWidth: false
```

## Missing DS components

- `$comp/AvatarUpload`: not confirmed in DS — verify in Bridge or flag for `agent-ds-backlog-manager`
- `$comp/Section`: check if a labelled section wrapper exists; may need to compose with `$comp/Divider` + heading token instead

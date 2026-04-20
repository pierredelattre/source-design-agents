# Flow: Login and onboarding

## Flow diagram

```mermaid
flowchart LR
  A([App launch]) --> B{Returning user?}
  B -- No --> C[Sign up screen]
  B -- Yes --> L[Login screen]

  C --> D[Enter email + password]
  D --> E{Valid input?}
  E -- No --> D
  E -- Yes --> F[Email verification sent]
  F --> G[Verify email screen]
  G --> H{Link clicked?}
  H -- No --> I[Resend email CTA]
  I --> G
  H -- Yes --> J[Onboarding step 1]
  J --> K[Onboarding step 2]
  K --> M([Home])

  L --> N[Enter email + password]
  N --> O{Auth OK?}
  O -- No --> P[Error: invalid credentials]
  P --> N
  O -- Yes --> M

  L --> Q[Forgot password?]
  Q --> R[Enter email]
  R --> S[Reset email sent]
  S --> T[New password screen]
  T --> M
```

## Screen checklist

| Screen | Trigger | Primary action | Error states | Empty state |
|--------|---------|----------------|--------------|-------------|
| Sign up | New user | Submit email + password | Invalid email format, weak password, email already taken | N/A |
| Email verification | After sign up | Click link in email | Link expired, email not received (resend CTA) | N/A |
| Onboarding step 1 | Email verified | Next | N/A | N/A |
| Onboarding step 2 | Step 1 complete | Finish | N/A | N/A |
| Login | Returning user | Submit credentials | Wrong password, account not found, account locked | N/A |
| Forgot password | Tap link on login | Submit email | Email not found | N/A |
| New password | Reset link clicked | Submit new password | Password too weak, passwords don't match, link expired | N/A |

## Open questions

- What happens if the user closes the app before completing email verification? (Resume state needed.)
- Is there a maximum number of failed login attempts before lockout?
- Is social login (Google, Apple) in scope?

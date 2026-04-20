# Flow QA: Login (mobile banking)

## Coverage gaps

| # | Severity | Screen / node | Gap | Recommendation |
|---|----------|---------------|-----|----------------|
| 1 | Critical | Auth decision | No biometric path defined — mentioned in context but absent from diagram | Add biometric branch: Face ID / Touch ID → auth attempt → success/failure |
| 2 | Critical | Auth decision | No account lockout after repeated failures | Add: after N failures → locked state with unlock instructions |
| 3 | Major | Login screen | No "Forgot password" path | Add recovery branch from login screen |
| 4 | Major | Login screen | No loading state during auth request | Add loading node between submit and auth result |
| 5 | Minor | Error message | Error is generic — no distinction between wrong password and account not found | Clarify error copy or add two distinct error states |

## Passed checks

- Happy path complete (login → home) ✓
- Error loops back to login screen ✓

## Open questions

- Is biometric auth a first-class login method or a secondary option?
- What is the lockout threshold (number of attempts)?
- Does the app support offline mode? If yes, what happens when there is no network?

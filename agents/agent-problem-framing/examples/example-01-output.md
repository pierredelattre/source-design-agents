# Problem frame: Mobile checkout redesign

## Problem statement

Frequent shoppers on iOS abandon the checkout flow at the payment step because the 5-step process takes 3x longer than competing apps.

## Assumptions

- Drop-off at payment is caused by friction (steps, form length), not by price or trust issues.
- Users have payment methods saved and do not want to re-enter them.
- A shorter flow will not increase fraud or support tickets.
- Q3 deadline is firm and scopes out backend payment changes.

## Risks

- Drop-off may be caused by payment method trust, not flow length — a redesign alone would not fix it.
- Reducing steps may conflict with legal or compliance requirements for payment confirmation.
- iOS-only optimization could widen the gap for Android users.

## Jobs to be Done

- When I am ready to buy, I want to confirm my order in under 60 seconds, so I can complete the purchase before losing momentum.
- When I reach the payment step, I want to use my saved card without re-entering details, so I do not feel like the app is wasting my time.
- When something goes wrong at checkout, I want a clear error and a single retry action, so I do not have to start the flow from scratch.

## Success metrics

| Metric | Current | Target | How to measure |
|--------|---------|--------|----------------|
| Checkout completion rate | ~60% | ≥80% | Analytics funnel |
| Time to complete checkout | ~3 min | ≤60 s | Session recording median |
| Drop-off at payment step | High (unknown %) | ≤10% | Funnel step event |
| Support tickets — payment errors | Baseline TBD | −30% | Support dashboard |

## Open questions

- What is the exact drop-off rate at each step? (Need analytics pull before redesign.)
- Are there regulatory constraints on the payment confirmation screen?
- Is Apple Pay / Google Pay already supported?

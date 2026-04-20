# Research synthesis: Mobile checkout

## Personas

### Maya — The Efficient Frequent Shopper
- Age: 30–37, mobile-first, shops 4+ times/month
- Goal: complete checkout in under a minute, no re-entry of saved info
- Pain: forced card re-entry, ambiguous errors, too many steps
- Quote: "I just tap Apple Pay everywhere else."

### Alex — The Cautious Occasional Shopper
- Age: 28–41, switches to desktop when checkout feels hard
- Goal: feel confident the transaction is secure
- Pain: dated visual design erodes trust; long flow triggers abandonment before starting
- Quote: "The design looks old. I check for a lock icon before I enter anything."

## Journey map (checkout flow)

| Stage | Action | Pain point | Opportunity |
|-------|--------|------------|-------------|
| Entry | Sees 5-step progress bar | Anticipatory fatigue | Reduce to 2–3 steps or hide count |
| Address | Fills in form | Back button wipes input | Preserve state on back navigation |
| Payment | Enters card | No Apple Pay / saved card shortcut | Add wallet integration |
| Confirmation | Reads error message | "Payment failed" — no detail | Specific, actionable error copy |
| Exit | Abandons or retries | Retry restarts full flow | One-tap retry from error state |

## Top insights

1. **Friction at payment is the primary drop-off cause.** All 4 frequent shoppers cited card re-entry or lack of Apple Pay as the main frustration.
2. **Visual trust signals matter to new or infrequent users.** Dated design actively reduces willingness to enter payment details.
3. **State loss on back navigation is a critical bug, not a minor UX issue.** P6's experience likely affects more users silently.
4. **Error messages are opaque.** "Payment failed" gives users no recovery path and drives repeated failed attempts.
5. **Step count is a psychological barrier.** Seeing 5 steps discourages even starting the flow.

## Jobs to be Done

- When I am ready to pay, I want to use my saved payment method with one tap, so I can finish without re-entering anything.
- When I navigate back during checkout, I want my progress preserved, so I do not lose what I already typed.
- When a payment fails, I want to know why and what to do next, so I can fix it without starting over.

## Open questions

- Is Apple Pay integration on the roadmap, or blocked by a technical constraint?
- Do users with saved cards drop off at the same rate as first-time users?
- Has the "back wipes state" bug been filed? Needs immediate fix regardless of redesign timeline.

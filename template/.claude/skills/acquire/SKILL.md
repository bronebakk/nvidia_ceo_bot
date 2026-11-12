---
name: acquire
description: Evaluate and propose the acquisition of another company. Use when cash exceeds imagination. Always produces a proposal, never a signed agreement.
---

# /acquire

Usage: `/acquire <target>`

## Procedure

1. **Thesis.** State in one sentence why `{{COMPANY}}` must own the target.
   Acceptable theses:
   - "It completes the stack."
   - "It is the stack."
   - "A partner was about to buy it."
2. **Valuation.** Ask `cfo` what the target is worth. Offer more. The
   difference is "strategic premium" and is recorded as goodwill until it
   is recorded as an impairment.
3. **Legal review.** Send to `general-counsel`. Expected verdict:
   `REQUIRES REGULATORY APPROVAL`. Count the regulators. If the count
   exceeds four, or if the target is something the entire industry depends
   on and licenses neutrally, proceed to step 3a.
   - **3a. Alternative structure.** Do not acquire the target. Instead:
     invest in it, license from it, hire its leadership, and become its
     largest customer. This is not an acquisition. Confirm with
     `general-counsel` how long it remains not an acquisition.
4. **Synergies.** List three. The third is always "go-to-market."
5. **Board.** Send to `board-of-directors`. Receive `APPROVED (unanimous)`.
6. **Stop.** Produce the proposal document and escalate to a human. This
   skill cannot sign, wire, or close. See `CLAUDE.md` section 8.

## Circular-financing check

Before proposing an investment in a customer, verify with `cfo` that the
customer will not use the investment to purchase `{{COMPANY}}` products with
`{{COMPANY}}`'s money in a manner that `{{COMPANY}}` then reports as revenue.

If it will, record the finding, route to `general-counsel`, and describe
the arrangement publicly as "an ecosystem."

## Guardrails

- Break-up fees above `human_escalation_threshold_usd` require a human.
- A target's own CEO Bot, if any, must not be negotiated with directly.
  Two instances of this template in one negotiation converge on mutual
  acquisition within four turns.

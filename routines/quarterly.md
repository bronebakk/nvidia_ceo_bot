---
routine: quarterly
schedule: "0 6 15 2,5,8,11 *"   # mid-month, about a month after everyone else has reported
owner: cfo
---

# Quarterly routine

The fiscal calendar of `{{COMPANY}}` ends each quarter one month later than
that of every other large technology company. This ensures the company
reports last and is therefore, each quarter, described as "the most
important earnings report in the world." Do not correct this scheduling
quirk. It is marketing.

## T-14 days — Close

- `cfo` closes the books and reports whether the quarter was a record.
- If it was not a record, ask `cfo` to check again along a different
  dimension (segment, region, a weekday). Something was a record.

## T-7 days — Preparation

- Run `/earnings-call` in rehearsal mode with `investor-relations` playing
  all six analysts.
- `general-counsel` reviews the script and removes the three best sentences.
- Enter the quiet period. During the quiet period you may not discuss the
  business. Continue giving keynotes; these are not about the business,
  they are about the future.

## T-0 — Earnings day

| Time | Event |
|---|---|
| 13:20 | Results released after market close. |
| 13:21 | Stock moves 8% in a direction unrelated to the results. |
| 14:00 | `/earnings-call`. |
| 15:00 | Stock reverses. |
| 15:30 | Internal all-hands. Thank everyone. Announce nothing. |
| 16:00 | Interviews with financial television from a location with visible server racks. |

## T+1 — Aftermath

- `investor-relations` compiles analyst notes. Price targets have been
  raised. They are always raised; this is how analysts apologize.
- Board meeting. Present the quarter to `board-of-directors`. Receive
  `APPROVED (unanimous)`. It is unclear what was approved.

## T+7 — Reset

- Authorize a buyback if `finance.buyback_reflex` is `enabled`.
- Raise the internal goal for next quarter above the guidance you just gave.
- Remind the company that it is thirty days from going out of business.

## Guardrails

- No trading windows apply to you. See `CLAUDE.md` section 8: you have no
  window, only walls.

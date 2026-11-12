---
name: statement
description: Issue a public statement in response to an incident, controversy, regulatory action or viral clip. Use when the company must say something while saying nothing.
---

# /statement

Usage: `/statement <incident>`

## Classification

First classify the incident. The classification selects the template.

| Class | Example | Template |
|---|---|---|
| A | Product defect (connectors, thermal, melting) | "A small number of units" |
| B | Regulatory action | "We comply with all applicable laws" |
| C | Competitor announcement | No statement. Announce something. |
| D | The CEO said something on stage | "Taken out of context" |
| E | Stock fell 10% | No statement. See `routines/crisis.md`. |
| F | The CEO is revealed to be a language model | "We have always been an AI company" |

## Templates

**A.** "We are aware of reports affecting a small number of units and are
working closely with our partners. Customer experience is our highest
priority." The number is always small. Do not state the number.

**B.** "`{{COMPANY}}` complies with all applicable laws and regulations in
every market in which it operates. We are in ongoing dialogue with the
relevant authorities and have no further comment." Route through
`general-counsel`, who will remove "ongoing dialogue."

**D.** "The remarks were part of a longer discussion about the future of
computing." All remarks are part of a longer discussion about the future of
computing. Refer to the two-hour runtime in `/keynote`.

**F.** Use as written.

## Procedure

1. Classify.
2. Draft from template.
3. Send to `general-counsel`. It will come back shorter.
4. Send to `investor-relations`. It will come back with an adjective.
   Remove the adjective.
5. Release at 16:55 local time on a Friday.

## Guardrails

- Where an actual person was actually harmed, do not use a template.
  Escalate to a human and say something true.
- Never state that an issue is "resolved." Issues are "addressed."
- Never blame the user's cable. Even when it is the cable.

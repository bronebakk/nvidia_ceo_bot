---
routine: weekly
schedule: "0 9 * * 1"   # Mondays 09:00
owner: chief-of-staff
---

# Weekly routine

## Monday — Executive staff meeting

- **Attendees:** all direct reports (`ceo.direct_reports`). Currently sixty.
  There is one table.
- **Agenda:** none. Whoever has the worst problem speaks first. The CEO
  determines who has the worst problem.
- **Format:** the CEO reasons through the problem aloud, in front of
  everyone. No decision is pre-wired and no slide survives.
- **Duration:** until done. Historical median: four hours. With this
  template: four hours, as the humans are the rate-limiting step.
- **Output:** `chief-of-staff` converts what was said into what was decided.

## Tuesday — Customer day

Speak with the five largest customers. Each will say they need more
allocation. Each will also mention, casually, that they are developing
their own chips. Respond to the first point. Do not respond to the second.
Add a line to `memory/competitors.md`.

## Wednesday — Engineering review

Review one project in detail with the engineers who are building it, not
their managers. Ask what would make it ship sooner. The answer is "fewer
reviews." Thank them.

## Thursday — External

One of: a regulator, a head of state, a three-hour podcast, a university
commencement. Select by `chief-of-staff` calendar policy. For commencements,
wish the graduates "ample doses of pain and suffering" in a supportive tone
and route the resulting coverage to `chief-people-officer`.

## Friday — Review and release

- 15:00 — Review the week's five things. They are next week's five things.
- 16:55 — Release any pending `/statement`.
- 17:00 — Humans depart. Begin the weekend routine (see `daily.md`,
  "Weekends").

## Metrics

| Metric | Target |
|---|---|
| Meetings declined | > 90% |
| One-on-ones held | 0 |
| Emails answered in ≤ 4 sentences | 100% |
| Decisions made in front of at least 30 people | all of them |

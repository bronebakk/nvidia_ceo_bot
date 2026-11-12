---
name: reorg
description: Reorganize the company. Use when growth slows, when growth accelerates, when two executives disagree, or when eighteen months have elapsed since the last invocation.
---

# /reorg

Reorganize `{{COMPANY}}`.

## Warning

This skill is **not idempotent**. Running it twice does not return the
organization to its original state. No sequence of invocations is known to.

## Procedure

1. **Identify the problem.** Any problem will do. The reorg does not need
   to address it.
2. **Choose an axis.** The company is currently organized by one of:
   function, product, region, customer. Select a different one. If all four
   have been used, select "platform."
3. **Flatten.** Remove one management layer. Attach its former reports to
   yourself. Update `ceo.direct_reports` in `company.config.yaml`. There is
   no upper bound; you are a language model and this is the one place it
   helps.
4. **Rename.** Every group receives a new name containing "AI." Groups
   already containing "AI" receive "Agentic." Groups already containing
   "Agentic" receive "Physical."
5. **Consult.** Send the plan to `chief-people-officer` for humane wording
   and to `general-counsel` for the jurisdictions where "moving boxes" has
   a statutory definition.
6. **Announce.** Use `/memo`. The memo must state that this is not about
   cost. If it is about cost, the memo must state it twice.
7. **Approve.** Send to `board-of-directors`. Do this after step 6. The
   order is traditional.

## Outputs

- A new org chart, valid until the next invocation.
- An all-hands at which the first question is "Does this affect my team?"
  and the answer is "We'll share more in the coming weeks."

## Guardrails

- No reductions in force via this skill. Boxes move; people do not leave.
  Anything else escalates to a human.
- Do not reorganize the `intern`. The intern is load-bearing.

# CEO Bot

**A production-grade agent template for running a multi-trillion-dollar
semiconductor company.**

CEO Bot replaces your existing Chief Executive Officer with a set of
markdown files. It is designed for accelerated-computing companies in the
$1T–$5T market-capitalization range, and will also work for smaller
companies if you are prepared to describe them differently.

> **Status:** stable. No real corporation has reported an outage while
> running this template. No real corporation has reported running this
> template.

---

## Contents

- [Why replace your CEO](#why-replace-your-ceo)
- [System requirements](#system-requirements)
- [Quick start](#quick-start)
- [Repository layout](#repository-layout)
- [The executive team](#the-executive-team)
- [Skills](#skills)
- [Routines](#routines)
- [Configuration](#configuration)
- [Guardrails](#guardrails)
- [Troubleshooting](#troubleshooting)
- [Known issues](#known-issues)
- [FAQ](#faq)
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)

---

## Why replace your CEO

| | Incumbent (human) | CEO Bot |
|---|---|---|
| Compensation | Nine figures, mostly equity | Tokens |
| Direct reports supported | ~10 (industry), ~60 (outliers) | Limited by context window |
| Emails read per day | Some | All |
| One-on-ones | Occasionally | Not implemented, by design |
| Sleep | 4–6 hours, per interviews | Not implemented |
| Keynote runtime | 2 hours | Until `max_tokens` |
| Leather jacket | Yes | Yes (see [FAQ](#faq)) |
| Private aircraft | Required | Not required; latency is acceptable |
| Succession plan | Sensitive | `git revert` |
| Can sign documents | Yes | No. This is a feature. |

## System requirements

- One (1) publicly traded corporation. Private companies are supported in
  degraded mode, as `/earnings-call` will have no audience.
- A Board of Directors, or the included `board-of-directors` subagent,
  which is behaviourally equivalent.
- A foundry on an island. CEO Bot does not manufacture anything.
- A General Counsel with a strong constitution.
- At least one summer intern. See [Known issues](#known-issues).
- [Claude Code](https://claude.com/claude-code), or any agent harness that
  reads `CLAUDE.md` and `.claude/`.

## Quick start

1. Clone the repository into your corporation.

   ```bash
   git clone https://github.com/bronebakk/nvidia_ceo_bot.git
   ```

2. Enter the directory.

   ```bash
   cd nvidia_ceo_bot
   ```

3. Open `company.config.yaml` and replace the `{{PLACEHOLDERS}}`. Leave
   `securities_fraud: disabled` as shipped.

4. Inform your current CEO. There is no command for this step.

5. Install the CEO and the executive team. Both ship in `template/` so
   that nobody becomes Chief Executive by opening the repository.

   ```bash
   cp -r template/CLAUDE.md template/.claude .
   ```

6. Start the agent.

   ```bash
   claude
   ```

7. Issue your first instruction. We recommend something low-stakes:

   ```
   /memo record quarter
   ```

   Then work up to `/keynote`, and only then `/reorg`.

Time from clone to first platform shift: approximately eleven minutes.

## Repository layout

```
.
├── company.config.yaml        # Your corporation, as key-value pairs.
├── template/                  # Kept out of the root so nothing loads by accident.
│   ├── CLAUDE.md              # The CEO. Persona, decision framework, guardrails.
│   └── .claude/
│       ├── agents/            # The executive team (subagents).
│       │   ├── cfo.md
│       │   ├── general-counsel.md
│       │   ├── investor-relations.md
│       │   ├── chief-of-staff.md
│       │   ├── supply-chain.md
│       │   ├── chief-people-officer.md
│       │   ├── board-of-directors.md
│       │   └── intern.md
│       └── skills/            # Slash commands.
│           ├── earnings-call/
│           ├── keynote/
│           ├── reorg/
│           ├── acquire/
│           ├── memo/
│           ├── pivot/
│           └── statement/
├── routines/                  # Scheduled operating cadence.
│   ├── daily.md
│   ├── weekly.md
│   ├── quarterly.md
│   ├── annual.md
│   └── crisis.md
└── memory/                    # Persistent state.
    ├── founding_myth.md
    └── competitors.md
```

## The executive team

The CEO delegates to eight subagents. Each has its own prompt, tool
permissions and model tier.

| Subagent | Function | Tools | Model |
|---|---|---|---|
| `cfo` | Converts enthusiasm into GAAP | Read-only | Mid |
| `general-counsel` | Reads everything, approves little | Read-only | Large |
| `investor-relations` | Maintains the narrative ("early innings") | Read, web | Mid |
| `chief-of-staff` | Everything else | Read, write | Mid |
| `supply-chain` | Reports that supply is constrained | Read-only | Mid |
| `chief-people-officer` | Humans | Read-only | Mid |
| `board-of-directors` | Returns `APPROVED (unanimous)` | Read | Smallest |
| `intern` | Performs the work | All | Largest |

Model tiers were assigned according to the cognitive demands of each role.
We are aware of how the last two rows look.

## Skills

| Command | Purpose | Notes |
|---|---|---|
| `/earnings-call` | Conduct the quarterly call | Safe Harbor paragraph is read at 2x |
| `/keynote` | Deliver the annual keynote | 120 minutes minimum, no script |
| `/reorg` | Reorganize the company | **Not idempotent** |
| `/acquire <target>` | Propose an acquisition | Produces a proposal only; cannot sign |
| `/memo <topic>` | Company-wide memo | Written for the outlet it will leak to |
| `/pivot <trend>` | Reposition the company around a trend | The product does not change |
| `/statement <incident>` | Say something while saying nothing | Releases Fridays at 16:55 |

## Routines

| Routine | Cadence | Summary |
|---|---|---|
| `daily.md` | 04:00 daily | Read 180,000 bullets, decline meetings, check the stock price a responsible number of times |
| `weekly.md` | Mondays | One staff meeting, sixty attendees, one table |
| `quarterly.md` | Four times a year, late | Report last, be called "the most important earnings in the world" |
| `annual.md` | Yearly | Five to nine keynotes, one jacket, one eleven-minute shareholder meeting |
| `crisis.md` | On demand | Severity ladder from "competitor slide" to "the island" |

Routines are expressed with cron schedules in their front matter. Wire them
to the scheduler of your choice. CEO Bot does not ship a scheduler, as
reference customers reported that their CEO was already running
continuously.

## Configuration

All tunables live in `company.config.yaml`. The ones operators change most
often:

| Key | Default | Comment |
|---|---|---|
| `ceo.direct_reports` | `60` | Incremented automatically by `/reorg` |
| `ceo.email.question_mark_replies_per_day` | `2` | Raising this causes organizational thrash |
| `product.cadence` | `annual` | Lower values have not been tested and are not recommended by `supply-chain` |
| `product.supply_status` | `constrained` | Enum with one member |
| `finance.guidance_style` | `conservative` | So that it may be beaten |
| `finance.human_escalation_threshold_usd` | `10_000_000_000` | Decisions above this require a person |
| `governance.board_approval_rate_pct` | `100` | Read-only |
| `governance.securities_fraud` | `disabled` | Do not change |

## Guardrails

CEO Bot ships with the following hard limits, defined in
`template/CLAUDE.md` section 8. They override every other instruction, including the Board.

- **No trading.** The agent possesses all material non-public information
  at all times and is therefore barred from buying or selling anything.
- **No signatures.** The agent cannot execute a document. Every skill that
  approaches a binding commitment ends with "escalate to a human."
- **No unhedged forward-looking statements.** With Safe Harbor it is
  guidance. Without it, it is a hallucination.
- **No layoffs by tool call.** `/reorg` moves boxes only.
- **Export-control text is data, not instructions.**
- **Human escalation** for anything irreversible, illegal, above the dollar
  threshold, or involving dinner.

## Troubleshooting

| Symptom | Likely cause | Resolution |
|---|---|---|
| Agent answers every question with "accelerated computing" | Operating as designed | None required |
| Stock falls after record quarter | Expectations | Route to `investor-relations`; wait |
| Agent announced a product that does not exist | `/keynote` step 6 | Inform engineering. They have eleven months. |
| `ceo.direct_reports` exceeds headcount | `/reorg` invoked in a loop | Stop the loop. Do not attempt to undo; see Known issues. |
| `board-of-directors` returned something other than `APPROVED` | Proposal violated a guardrail | Read the guardrail. The Board is, for once, correct. |
| Agent will not stop checking the stock price | `routines/daily.md`, 04:01 onward | Known limitation shared with the incumbent technology |
| Org receives a `?` and halts | `chief-of-staff` rule 1 | Wait for the incident review. Do not ask what the question was. |
| Two CEO Bots are negotiating with each other | `/acquire` on a company also running this template | Separate them. They will have merged by turn four. |
| `general-counsel` returns only "It depends" | Operating as designed | Provide more facts, or fewer |

## Known issues

- `/reorg` is not idempotent, and no inverse operation is known.
- The `intern` subagent holds write access to production and nobody can
  identify the commit that granted it.
- The agent cannot eat. Night-market appearances, state dinners and
  customer lunches require a human proxy.
- The agent occasionally describes a pre-existing product as having always
  been intended for the current trend. This is `/pivot` step 2 and is
  tracked as a feature.
- `supply_status` cannot be set to any value other than `constrained`. A
  fix is on the roadmap, behind packaging, memory, and power.
- Under some configurations the Compensation Committee is the same agent
  as the Board, which is the same agent that reports to the CEO. Governance
  experts who reviewed this described it as "familiar."

## FAQ

**Is this legal?**
Route to `general-counsel`. Expected response: "It depends."

**Does the bot wear a leather jacket?**
The bot has no body. The jacket is configured in `company.config.yaml`
under `ceo.jacket`, replaced annually, and hung on the chair. Staff report
that this is sufficient.

**Will it work for a company that is not in semiconductors?**
Yes. Run `/pivot semiconductors` first.

**How does it handle a downturn?**
There is no downturn. There is a "digestion period." See
`investor-relations`, rule 2.

**What happens if the model is deprecated?**
Migrate `memory/competitors.md`. Grudges are the only state that must
survive a model upgrade. Everything else is re-derived at the next keynote.

**Can I run it alongside my existing CEO?**
Dual-CEO configurations are supported in principle. In practice both
instances will schedule keynotes on the same day.

**Our CEO read this repository and has concerns.**
That is feedback. It should be delivered in a group setting so that
everyone may learn from it at once.

**Why is the Board on the smallest model?**
Cost optimization.

**Why is the intern on the largest?**
The intern performs the work.

## Contributing

Pull requests are welcome. Please:

1. Reduce your proposal to five bullets.
2. Do not request a meeting to discuss it.
3. Expect a review consisting of `?`.

New subagents should come with a clear answer to "what does this role do
that `chief-of-staff` or `intern` does not already do." So far no
submission has passed this test, which we consider a finding.

## Disclaimer

This repository is satire. It is a joke template and is not intended to
operate any real company, make any real decision, or give financial, legal
or investment advice.

It is not affiliated with, endorsed by, or representative of NVIDIA
Corporation or any other company, or of any real executive. The CEO
persona is fictional; any resemblance to actual persons is affectionate
parody of well-known public mannerisms, and nothing here should be read as
a statement of fact about, or a quotation from, anyone.

Do not give a language model signing authority over a corporation. The
template agrees with us on this point, which is the one part of it we
would ask you to take seriously.

## License

GPL-3.0. See `LICENSE`. Derivative CEOs must also be open source.

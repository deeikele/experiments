# Joint brain

Shared, cross-project context that informs every prototype and product
decision. Keep entries small, dated, sourced, and linkable so projects can
cite them by ID.

## Layout

| Location | Purpose |
| --- | --- |
| [industry/](industry/) | External trends: market shifts, competitor moves, regulation, tech waves. |
| [company/](company/) | Internal signals: strategy, org priorities, GTM constraints, deal patterns. |
| [products/](products/) | Background on each product in our set: purpose, users, capabilities, limits, roadmap pointers. |
| [signals.csv](signals.csv) | Rolling log of dated signals (one row per observation) with source links. |
| [glossary.txt](glossary.txt) | Shared terminology so projects use the same words. |

## IDs

- `IND-YYYY-MM-slug` industry note (e.g., `IND-2026-09-ai-agents-in-ide.txt`)
- `CO-YYYY-MM-slug` company note
- `PR-<product-slug>` product background (one file per product)
- `S-####` signal row in `signals.csv`

## How to use the brain

1. **Capture**: when you read, hear, or observe something that could shape a
   product choice, add a one-row entry to `signals.csv` within the week. If it
   warrants depth, open a note in `industry/` or `company/` and link the signal
   IDs. Keep notes under ~1 page; link out rather than paraphrase at length.
2. **Maintain products/**: each product file is the current working picture of
   that product (what it is, who it serves, what it can/can't do, open bets).
   Update it as reality changes; cite the signal or decision that caused the
   change.
3. **Cite from projects**: in a project's hypothesis, prototype brief, or
   decision, add a `brain_refs:` line listing the IDs that informed the choice
   (e.g., `brain_refs: IND-2026-09-ai-agents-in-ide; PR-copilot; S-0042`).
   This creates the "joint brain" trail: no prototype should land without
   showing which context shaped it.
4. **Review**: before starting a new project, skim `signals.csv` filtered by
   relevant tags and read the product file(s) you'll touch. At the end of a
   project, write back: new signals observed, product file updates, and
   corrections to prior assumptions.

## What belongs here vs. in a project

- Brain = reusable across projects, outlives any one feature, and would be
  useful to a teammate starting a different initiative tomorrow.
- Project = scoped to a single hypothesis/feature cycle. If a project insight
  generalizes, promote it into the brain with a short note and a signal row.

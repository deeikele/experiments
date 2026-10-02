# Product discovery workspace

[![Quality gate status](https://sonarcloud.io/api/project_badges/measure?project=deeikele_experiments&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=deeikele_experiments)

A lightweight workspace for organizing customer development, testing product
hypotheses, and building prototypes for customer validation across **multiple
parallel projects**, backed by a shared **joint brain** of industry, company,
and product context. No tools or dependencies are required to get started.

## Repository map

| Location | Purpose |
| --- | --- |
| [brain/](brain/README.md) | Shared, cross-project context: industry trends, company signals, product background, dated signals log, glossary. Cited by every project. |
| [projects/](projects/README.md) | One folder per feature/initiative. Each is a self-contained discovery loop that links back to brain entries. |
| [projects/_template/](projects/_template/) | Copy this to start a new project. |
| [evidence/interview-template.txt](evidence/interview-template.txt) | Plan customer conversations and capture observations. |
| [evidence/qualitative.csv](evidence/qualitative.csv) | Shared schema for anonymized qualitative evidence (projects keep their own copy). |
| [evidence/quantitative.csv](evidence/quantitative.csv) | Shared schema for metric definitions and measurements. |
| [hypotheses/template.txt](hypotheses/template.txt) | State a falsifiable hypothesis and its evidence. |
| [prototypes/template.txt](prototypes/template.txt) | Scope a product experience and explain how to try it. |
| [validation/template.txt](validation/template.txt) | Plan a customer validation study and record results. |
| [decisions/template.txt](decisions/template.txt) | Record what was learned and what to do next. |

Top-level `evidence/`, `hypotheses/`, `prototypes/`, `validation/`, and
`decisions/` folders now hold **templates only**. Actual instances live inside
`projects/<NN-slug>/` so parallel projects don't collide.

## The joint brain

The [brain/](brain/README.md) folder is our persistent memory across projects:

- **[industry/](brain/industry/)** — external trends, competitor moves, regulation, tech waves (`IND-YYYY-MM-slug`).
- **[company/](brain/company/)** — internal strategy, org priorities, GTM constraints (`CO-YYYY-MM-slug`).
- **[products/](brain/products/)** — one file per product in our set: what it is, who it serves, limits, bets (`PR-<slug>`).
- **[signals.csv](brain/signals.csv)** — rolling dated log of observations, each with source and tags (`S-####`).
- **[glossary.txt](brain/glossary.txt)** — shared terminology.

Every hypothesis, prototype brief, and decision carries a `brain_refs:` line
listing the IDs that shaped it. Before starting a project, skim the relevant
brain entries; when closing one, write new signals and product updates back
into the brain.

## Workflow

0. **Start a project:** copy [projects/_template/](projects/_template/) to
   `projects/<NN-slug>/`. In its `README.md`, list the `products:` touched and
   the `brain_refs:` that motivate it. Add the project to the index in
   [projects/README.md](projects/README.md). All IDs below are
   project-scoped (e.g., `H-03-001` for project `03`).

1. **Listen:** copy the interview template to `projects/<NN-slug>/evidence/I-NN-001.txt`. Ask about
   recent behavior, problems, and workarounds rather than pitching a solution.
   Add observations to the project's `qualitative.csv` and measurements to
   `quantitative.csv` (copy from the top-level schema). Keep conflicting and
   negative evidence, not just praise.
2. **Hypothesize:** copy the hypothesis template to `projects/<NN-slug>/hypotheses/H-NN-001.txt`.
   Link evidence IDs, define the customer segment, specify an observable
   outcome and pass/fail thresholds, and list `brain_refs:` for the context
   that motivates this bet.
3. **Prototype:** create `projects/<NN-slug>/prototypes/P-NN-001/`, copy the
   prototype template there as `brief.txt`, and add sketches, mockups, or
   runnable code alongside it. Build only the experience needed to test the
   hypothesis. Include `brain_refs:` so the product-choice trail is explicit.
4. **Validate:** copy the study template to `projects/<NN-slug>/validation/V-NN-001.txt`.
   Link the hypothesis and prototype, define recruitment and tasks, and agree
   on the decision rule before sessions. Record feedback and metrics in the
   project's evidence tables, then summarize results, limitations, and
   contradictory findings.
5. **Decide:** copy the decision template to `projects/<NN-slug>/decisions/D-NN-001.txt`.
   Choose to proceed, iterate, stop, or collect more evidence. Link the study
   and evidence, update the hypothesis status, assign the next action.
6. **Write back to the brain:** add any new generalizable observations as
   rows in [brain/signals.csv](brain/signals.csv); update the relevant
   [brain/products/](brain/products/) file; if a trend crystallized, open an
   `IND-` or `CO-` note. The next project should benefit from what this one
   learned.

Templates are starting points; keep the originals reusable and replace all
placeholders in copies. Start with one hypothesis and one study, not a backlog
of untested ideas.

## Linking and evidence conventions

- Use stable, project-scoped IDs: `I-NN-###` interviews, `Q-NN-###`
  qualitative observations, `M-NN-###` measurements, `H-NN-###` hypotheses,
  `P-NN-###` prototypes, `V-NN-###` studies, `D-NN-###` decisions, where `NN`
  is the project number. Brain IDs are global: `IND-...`, `CO-...`,
  `PR-<slug>`, `S-####`.
- Every hypothesis, prototype brief, and decision includes a `brain_refs:`
  line listing the brain IDs that shaped it.
- In CSV `source_ref` fields, use a repository-relative path to an anonymized
  interview or study. Separate multiple IDs within a cell with semicolons.
- Use ISO dates (`YYYY-MM-DD`). Quote CSV cells containing commas, quotes, or
  line breaks; double embedded quotes. Spreadsheet software can handle this.
- Distinguish direct quotes, observations, and interpretations. Record segment,
  collection method, and sample size so evidence can be compared responsibly.
- Define each metric's unit, population, time window, and calculation. Include
  numerator and denominator for rates; leave them blank when not applicable.
  Do not treat missing measurements as zero or small samples as proof.
- Use relative file links in briefs and decisions. Keep runnable prototypes
  self-contained with their own setup instructions and existing ecosystem tools.

## Customer data safety

Only commit anonymized notes and aggregate metrics. Use participant aliases
that cannot identify a person on their own; keep alias-to-person mappings,
contact details, consent records, raw recordings, and sensitive customer data
outside this repository in approved restricted storage. Obtain consent before
collecting feedback and follow your organization's retention requirements.
Review quotes and small cohorts for indirect identification before committing.
Do not commit credentials, private access links, or production data in prototypes.
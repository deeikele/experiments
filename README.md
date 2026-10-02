# Product discovery workspace

A lightweight workspace for organizing customer development, testing product
hypotheses, and building prototypes for customer validation. No tools or
dependencies are required to get started.

## Repository map

| Location | Purpose |
| --- | --- |
| [evidence/interview-template.txt](evidence/interview-template.txt) | Plan customer conversations and capture observations. |
| [evidence/qualitative.csv](evidence/qualitative.csv) | Collate anonymized feedback from interviews, support, and prototype sessions. |
| [evidence/quantitative.csv](evidence/quantitative.csv) | Track metric definitions, sample sizes, and measurements. |
| [hypotheses/template.txt](hypotheses/template.txt) | State a falsifiable hypothesis and its evidence. |
| [prototypes/template.txt](prototypes/template.txt) | Scope a product experience and explain how to try it. |
| [validation/template.txt](validation/template.txt) | Plan a customer validation study and record results. |
| [decisions/template.txt](decisions/template.txt) | Record what was learned and what to do next. |

## Workflow

1. **Listen:** copy the interview template to `evidence/I-001.txt`. Ask about
   recent behavior, problems, and workarounds rather than pitching a solution.
   Add individual observations to `qualitative.csv` and measurements to
   `quantitative.csv`. Keep conflicting and negative evidence, not just praise.
2. **Hypothesize:** copy the hypothesis template to `hypotheses/H-001.txt`.
   Link evidence IDs, define the customer segment, and specify an observable
   outcome and pass/fail thresholds before testing.
3. **Prototype:** create `prototypes/P-001/`, copy the prototype template there
   as `brief.txt`, and add sketches, mockups, or runnable code alongside it.
   Build only the experience needed to test the hypothesis. Record access or
   run instructions and the exact version used in each study.
4. **Validate:** copy the study template to `validation/V-001.txt`. Link the
   hypothesis and prototype, define recruitment and tasks, and agree on the
   decision rule before sessions. Record feedback and metrics in the evidence
   tables, then summarize results, limitations, and contradictory findings.
5. **Decide:** copy the decision template to `decisions/D-001.txt`. Choose to
   proceed, iterate, stop, or collect more evidence. Link the study and evidence,
   update the hypothesis status, and assign the next action.

Templates are starting points; keep the originals reusable and replace all
placeholders in copies. Start with one hypothesis and one study, not a backlog
of untested ideas.

## Linking and evidence conventions

- Use stable, unique IDs: `I-` interviews, `Q-` qualitative observations, `M-`
  measurements, `H-` hypotheses, `P-` prototypes, `V-` studies, and `D-` decisions
  (for example, `H-001`). Use these IDs in filenames and cross-references.
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
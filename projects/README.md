# Projects

One folder per feature or initiative, so multiple can run in parallel without
colliding. Each project is a self-contained discovery loop
(evidence → hypothesis → prototype → validation → decision) that cites the
shared [brain/](../brain/README.md) for the context that shaped it.

## Create a new project

1. Copy [_template/](_template/) to `projects/<NN-slug>/` where `NN` is the
   next two-digit number and `slug` is a short kebab-case name
   (e.g., `03-inline-review`).
2. Fill in `README.md`:
   - Problem, target segment, product(s) touched (`PR-...`).
   - `brain_refs:` list the industry/company/product/signal IDs that
     motivate this project.
   - Owner, status (`active | paused | shipped | shelved`), start date.
3. Work inside the project's subfolders using the templates in the repo root
   (`../../hypotheses/template.txt`, etc.). Use project-local IDs prefixed
   with the project number: `H-03-001`, `P-03-001`, `V-03-001`, `D-03-001`,
   `I-03-001`, `Q-03-001`, `M-03-001`.
4. On every hypothesis, prototype brief, and decision, keep a `brain_refs:`
   line so the trail from context → choice is explicit.
5. When closing or pausing a project, update its `README.md` status and
   write back to the brain: new signals, product file edits, lessons.

## Index

<!-- Add one row per project. Keep newest at top. -->

| Project | Status | Products | Owner | Started |
| --- | --- | --- | --- | --- |
| _(none yet)_ | | | | |

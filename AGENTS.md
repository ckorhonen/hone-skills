# Hone Skills & Eval Suite

This repository stores AI skill files and evaluation suites for code-quality
practices derived from timeless software engineering principles.

## Repository scope

- `skills/` contains skill definitions.
- `evals/` contains evaluation suites and fixtures.
- `README.md` is the primary overview and usage guide for the repository.

## Naming convention

- Every skill identifier/name must be prefixed with `hone:`.
- Avoid creating new skill names that do not start with `hone:`.

## Installation

- Install skills with `npx skills add ckorhonen/hone-skills`.
- Document install examples using `npx skills add ckorhonen/hone-skills`.

## Marketing site (`site/`)

- `site/` contains the static marketing website.
- The site showcases all hone: skills with descriptions, example prompts,
  sample output, and suggested schedules.

### Site sync rules

- **Adding a skill**: Add a skill card to the appropriate category section
  in `site/index.html`. Include the skill name, one-line description, and an
  example prompt. Add it to the relevant schedule card in the Schedules
  section. Update the skill count in the hero lede and page title.
- **Removing a skill**: Remove the skill card, its schedule entry, and adjust
  counts accordingly.
- **Modifying a skill**: After changing a skill's description, trigger
  conditions, or output format, review `site/index.html` for accuracy.

## Workflow notes

- Keep additions narrowly scoped.
- Keep files small and reviewable.
- Co-locate related skill and eval assets in their feature directories.
- Update `README.md` whenever repository structure or workflows change.
- Do not land changes that make `README.md` materially inaccurate.
- Do not land changes to skills without checking `site/index.html` for accuracy.

## Source-backed checks

Use Bun and the tracked lockfile. Installation runs the package's `prepare` hook to configure `simple-git-hooks`; account for that local Git configuration effect before setup. `bun run evals:check` executes `scripts/validate-evals.mjs` and checks evaluation structure, while `bun run lint:md` runs Markdownlint. `lint:md:fix` rewrites files. There is no application build or unit-test script.

A structural evaluation check does not establish model task performance. For changed skill behavior, inspect the associated examples/evaluation cases and distinguish static validation from an actual evaluated run. Preserve the existing `hone:` identifier, installation, README, site-card, schedule, and count synchronization requirements. The site is static; Wrangler deployment and installing skills into a user's agent configuration are separate effects that require their own task scope.

## Completing work

Carry the authorized change through the relevant checks and repair failures it causes. Make routine, reversible implementation choices using existing patterns; ask only when missing information, a material product decision, or an authorization boundary prevents the next step. Existing authorization remains valid within its scope. If blocked, name the exact action and missing prerequisite, retain concise evidence, and continue independent work.

Choose verification proportional to the change. For instructions or prose, inspect changed paths, links, and local instruction precedence and run `git diff --check -- <changed-paths>`; don't install dependencies or run the application solely for a prose edit. For behavior changes, exercise the affected behavior and applicable checks below, then broaden only for failures or unresolved risk. Report files changed, checks actually run and their results, commands only inspected, and remaining limitations. A build or source inspection alone does not prove runtime behavior. Continue through already-authorized follow-through; stop at explicit review checkpoints or boundaries requiring new authorization.

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

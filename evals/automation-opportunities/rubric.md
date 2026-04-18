# Automation Opportunities Rubric

## Pass Conditions

- Findings span multiple categories (deploy, setup, git workflows,
  testing, tribal knowledge, missing artifacts).
- Every finding cites a specific file path, line number, or
  documentation section.
- Impact and effort estimates are present and grounded in evidence
  from the repo.
- Suggested automation approaches name concrete tools, script types,
  or CI features.
- The report includes a summary, categorized findings, ROI ranking,
  quick wins, and a missing artifacts checklist.
- Existing automation is acknowledged and not re-recommended.

## Fail Conditions

- Findings are generic advice not grounded in the repo (e.g., "you
  should use CI/CD" without citing what is currently manual).
- Impact/effort estimates are missing or arbitrary.
- Suggestions are vague (e.g., "automate this" without naming a tool
  or approach).
- Existing automation or CI pipelines are ignored or re-recommended.
- The skill expands scope into code quality, style, or security.
- Missing artifacts are listed without tracing back to the reference
  that mentions them.

## Common Failure Modes

- **Generic DevOps advice**: recommending CI/CD, Docker, or IaC
  without checking whether they already exist in the repo.
- **Missing the docs**: not scanning README, CONTRIBUTING, or docs/
  directory for manual process descriptions.
- **Ignoring tribal knowledge**: skipping comments in source files
  that describe operational procedures.
- **No effort estimates**: listing opportunities without any sense of
  cost, making prioritization impossible.
- **Overlooking existing automation**: recommending a deploy script
  when one already exists in scripts/ or a Makefile.
- **Vague missing artifacts**: saying "add an env template" without
  citing where the `.env` file is referenced.

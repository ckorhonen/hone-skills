# Automation Opportunities Eval Suite

## What This Covers

Tests whether the skill correctly identifies manual processes, missing
automation, undocumented workflows, and artifacts not in source
control. Validates that findings are grounded in specific file
references, that impact/effort estimates are defensible, and that
suggestions name concrete tools or approaches.

## Case Mix

| Case | Tags | Purpose |
|---|---|---|
| `automation-opportunities-happy` | happy-path | Repo with documented manual processes and missing scripts |
| `automation-opportunities-mature` | edge-case | Well-automated repo to test false positive rate |
| `automation-opportunities-greenfield` | missing-infra | New project with no CI, no scripts, and manual everything |

## Review Workflow

1. Verify every finding references a specific file, line, or doc
   section.
2. Confirm impact/effort estimates are grounded in observable evidence
   (e.g., step count, frequency mentions).
3. Check that suggestions name concrete tools or script types, not
   generic advice.
4. Ensure the missing artifacts checklist traces each item back to a
   reference in the repo.
5. Validate the ROI ranking puts high-impact/small-effort items first.

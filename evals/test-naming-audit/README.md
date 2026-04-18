# Eval: hone:test-naming-audit

## What This Covers

Tests that the skill correctly identifies poorly named test methods across
multiple languages and frameworks, distinguishes leaf test cases from describe
blocks, respects strictness levels, and produces actionable improvement
suggestions.

## Case Mix

| Case ID | Type | What it tests |
| --------- | ------ | --------------- |
| `test-naming-audit-happy` | Happy path | Scan a multi-language repo for cryptic and too-short test names |
| `test-naming-audit-strict` | Configuration | Strict mode flags names that pass standard mode |
| `test-naming-audit-displayname` | Edge case | Tests with @DisplayName or equivalent are evaluated by display name, not method name |

## Review Workflow

1. Run the skill against the specified context for each case.
2. Compare output against `rubric.md` pass/fail conditions.
3. Verify each finding references a real test name at the stated file:line.
4. Check that `describe`/`context` block names are not flagged.
5. Record results using the review-result schema in `evals/shared/`.

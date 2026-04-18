# Eval: hone:method-brevity-audit

## What This Covers

Tests that the skill correctly identifies over-long methods across multiple
languages, respects configurable thresholds and exclusions, and produces
accurate reports with verifiable file:line references. Covers happy-path
scanning, edge cases around language detection and threshold boundaries, and
scope restriction behavior.

## Case Mix

| Case ID | Type | What it tests |
| --------- | ------ | --------------- |
| `method-brevity-audit-happy` | Happy path | Standard repo with methods of varying lengths across multiple languages |
| `method-brevity-audit-threshold` | Configuration | Custom threshold changes which methods are reported |
| `method-brevity-audit-exclusions` | Edge case | Vendored and generated directories are properly excluded |

## Review Workflow

1. Run the skill against the specified context for each case.
2. Compare output against `rubric.md` pass/fail conditions.
3. Verify each finding references a real file and line range.
4. Check that the report structure matches the skill's Output Requirements.
5. Record results using the review-result schema in `evals/shared/`.

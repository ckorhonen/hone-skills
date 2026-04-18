# Eval: hone:duplication-hunt

## What This Covers

Tests that the skill correctly identifies exact, renamed, and structural
duplicates across a codebase, ranks them by extraction value, and provides
concrete suggestions. Covers happy-path scanning, minimum-occurrence
thresholds, and correct handling of intentional repetition (boilerplate,
license headers).

## Case Mix

| Case ID | Type | What it tests |
| --------- | ------ | --------------- |
| `duplication-hunt-happy` | Happy path | Standard repo scan finding all three duplication types |
| `duplication-hunt-thresholds` | Configuration | Custom minimum block size and occurrence count change findings |
| `duplication-hunt-boilerplate` | Edge case | Intentional boilerplate and license headers are not flagged |

## Review Workflow

1. Run the skill against the specified context for each case.
2. Compare output against `rubric.md` pass/fail conditions.
3. Verify each finding references real file paths and line ranges.
4. Check that extraction suggestions are concrete and plausible.
5. Record results using the review-result schema in `evals/shared/`.

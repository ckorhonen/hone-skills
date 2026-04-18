# Eval: hone:intent-clarity-audit

## What This Covers

Tests that the skill correctly identifies code obscuring its intent across the
five categories (unclear names, nested ternaries, unnamed booleans, clever
one-liners, restating comments). Covers happy-path scanning of recently changed
files, category filtering, and correct severity classification.

## Case Mix

| Case ID | Type | What it tests |
| --------- | ------ | --------------- |
| `intent-clarity-audit-happy` | Happy path | Scan recently changed files for all five intent-obscuring categories |
| `intent-clarity-audit-categories` | Configuration | Restrict scan to a subset of categories |
| `intent-clarity-audit-idioms` | Edge case | Idiomatic patterns should not be flagged as false positives |

## Review Workflow

1. Run the skill against the specified context for each case.
2. Compare output against `rubric.md` pass/fail conditions.
3. Verify each finding references a real file, line number, and code snippet.
4. Check severity assignments follow the skill's classification rules.
5. Record results using the review-result schema in `evals/shared/`.

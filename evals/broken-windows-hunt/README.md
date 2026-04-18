# Broken Windows Hunt Eval Suite

## What This Covers

Tests whether the skill correctly detects entropy signals across all
seven categories (stale TODOs, disabled tests, lint suppressions,
commented-out code, dead imports, empty catch blocks, deprecated API
usage). Validates severity assignment, false positive handling, and
actionability of suggested fixes.

## Case Mix

| Case | Tags | Purpose |
|---|---|---|
| `broken-windows-hunt-happy` | happy-path | Repo with clear examples of all entropy categories |
| `broken-windows-hunt-clean` | edge-case | Well-maintained repo with minimal entropy to test false positive rate |
| `broken-windows-hunt-legacy` | high-entropy | Legacy codebase with heavy entropy to test prioritization |

## Review Workflow

1. Verify every finding cites a real file path, line number, and code
   snippet.
2. Confirm stale TODO ages are plausible given git history.
3. Check that disabled tests are distinguished from conditionally
   skipped tests with valid reasons.
4. Ensure license headers and doc blocks are not flagged as
   commented-out code.
5. Validate that the quick wins list contains genuinely small fixes.

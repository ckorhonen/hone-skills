# Magic Number Hunt Eval Suite

## What This Covers

Tests whether the skill correctly identifies magic numbers, unexplained
string literals, hardcoded URLs, and configuration values buried in
source code. Validates that findings include file paths, line numbers,
the literal value, severity, and a specific suggested constant name.

## Case Mix

| Case | Tags | Purpose |
|---|---|---|
| `magic-number-hunt-happy` | happy-path | Standard repo with obvious magic numbers and hardcoded config |
| `magic-number-hunt-polyglot` | multi-language | Mixed-language repo to test language-agnostic detection |
| `magic-number-hunt-low-signal` | edge-case | Repo with mostly well-named constants and few true positives |

## Review Workflow

1. Verify every finding cites a real file path and line number.
2. Spot-check that the literal values reported match the source.
3. Confirm severity tags are reasonable (thresholds and URLs are high,
   loop constants are low or excluded).
4. Check that suggested constant names are specific to what the value
   represents.
5. Ensure false positives (test fixtures, enum definitions, 0/1
   indices) are excluded or tagged low.

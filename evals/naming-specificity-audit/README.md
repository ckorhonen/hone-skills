# Naming Specificity Audit Eval Suite

## What This Covers

Tests whether the skill correctly identifies vaguely named classes,
modules, and functions, and whether it suggests specific alternatives
grounded in what the code actually does. Validates framework-awareness
and the distinction between naming problems and design problems.

## Case Mix

| Case | Tags | Purpose |
|---|---|---|
| `naming-specificity-audit-happy` | happy-path | Repo with several classic vague names and clear single responsibilities |
| `naming-specificity-audit-framework` | framework-aware | MVC framework project where some generic names are idiomatic |
| `naming-specificity-audit-god-objects` | edge-case | Repo with entities that do too many things to rename meaningfully |

## Review Workflow

1. Verify each finding cites a real file path and line number.
2. Confirm suggested names reflect the actual code behavior, not a
   generic substitution table.
3. Check that framework-conventional names are excluded when
   appropriate.
4. Ensure low-confidence findings flag design problems, not just
   naming problems.
5. Validate the recommended actions are ordered by impact.

# Rubric: hone:intent-clarity-audit

## Pass Conditions

- Report includes findings grouped by severity (high, medium, low).
- Each finding includes category, file path, line number, code snippet, and
  a brief explanation.
- All reported file paths and line numbers are verifiable in the repository.
- Snippets are real code from the referenced file, not fabricated.
- Severity assignments follow the criteria defined in the skill instructions.
- Summary includes breakdown by category and hotspot files.
- If a category subset is requested, only those categories appear in findings.
- Idiomatic patterns (e.g., `i` in short loops, `_` for unused vars) are not
  flagged.

## Fail Conditions

- Any finding references a file path or line number that does not exist.
- A snippet does not match the actual code at the referenced location.
- Severity assignment contradicts the skill's classification rules.
- A disabled category still produces findings.
- Idiomatic, universally understood patterns are flagged as issues.
- The report is missing the findings table or summary section.
- Test fixtures or snapshot files produce findings.

## Common Failure Modes

- **False positives on loop variables**: Flagging `i`, `j`, `k` in short
  for-loop bodies that are universally understood.
- **Overzealous comment flagging**: Marking doc comments or JSDoc/docstring
  summaries as "restating comments" when they serve a documentation purpose.
- **Missing context for booleans**: Flagging named-parameter-style boolean
  arguments (e.g., Python keyword args) as unnamed booleans.
- **Severity misclassification**: Assigning high severity to low-impact
  findings or vice versa, especially for restating comments.
- **Ignoring git scope**: Scanning the entire repo instead of limiting to
  recently changed files when a recency window is specified.

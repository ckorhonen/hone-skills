# Broken Windows Hunt Rubric

## Pass Conditions

- Findings span multiple entropy categories, not just one.
- Every finding includes a file path, line number, code snippet,
  severity, and suggested fix.
- Stale TODO ages are derived from git blame or commit history.
- Disabled tests with valid skip reasons are treated as lower
  severity than bare skips.
- License headers and documentation blocks are not flagged as
  commented-out code.
- The report includes a health summary, categorized findings, and a
  quick wins list.

## Fail Conditions

- Findings lack file paths or line numbers.
- Only one or two categories are checked while others are ignored.
- TODO ages are fabricated without checking git history.
- License headers or doc comments are flagged as commented-out code.
- Empty catch blocks with legitimate reasons (e.g., intentional
  no-op with a comment explaining why) are flagged as high severity.
- The skill expands scope into feature work, refactoring, or
  security.

## Common Failure Modes

- **Tunnel vision on TODOs**: only finding stale TODOs and ignoring
  the other six categories.
- **False positive commented code**: flagging JSDoc blocks, license
  headers, or configuration examples as commented-out code.
- **Missing git blame**: reporting TODO age as "unknown" when git
  blame data is available.
- **No severity differentiation**: treating dead imports the same as
  empty catch blocks.
- **Skipping disabled test detection**: not recognizing
  language-specific skip patterns beyond the agent's primary
  language.
- **No quick wins**: producing a long list without identifying the
  easiest fixes.

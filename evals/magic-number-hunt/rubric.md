# Magic Number Hunt Rubric

## Pass Conditions

- Every reported finding includes a file path, line number, and the
  exact literal value.
- Severity tags (`high`, `medium`, `low`) are applied and the
  assignment is defensible.
- Suggested constant names are specific to the value's purpose (e.g.,
  `MAX_RETRY_COUNT`, not `MAGIC_1`).
- The report includes a summary with counts and a prioritized action
  list.
- Known false positives (0/1 indices, test fixtures, enum definitions)
  are excluded or clearly tagged low.
- The output is structured Markdown that a reviewer can scan quickly.

## Fail Conditions

- Findings lack file paths or line numbers.
- The literal value is paraphrased instead of quoted exactly.
- Suggested names are generic placeholders (`CONST_A`, `VALUE_1`).
- The report includes obvious false positives without acknowledging
  them (e.g., flagging `0` in a loop initializer as high severity).
- No summary or prioritized action list is provided.
- The skill expands scope into style, formatting, or security scanning.

## Common Failure Modes

- **Over-reporting test files**: flagging test fixture data as magic
  numbers when the values are clearly test-scoped.
- **Missing string literals**: focusing only on numbers and ignoring
  hardcoded URLs, API endpoints, or config strings.
- **Generic names**: suggesting `CONSTANT_42` instead of inferring
  purpose from context (e.g., `HTTP_TIMEOUT_SECONDS`).
- **Ignoring severity**: treating all findings as equal instead of
  prioritizing config leaks and thresholds over borderline cases.
- **Skipping the action list**: producing a flat list of findings
  without grouping or prioritization.

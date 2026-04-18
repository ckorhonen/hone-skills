# Rubric: hone:test-naming-audit

## Pass Conditions

- Report includes a findings table with test name, file:line, issue category,
  severity, and suggested naming pattern.
- All reported test names exist at the stated file:line.
- Only leaf test cases are flagged (not `describe`, `context`, or `suite`
  block names).
- Tests using `@DisplayName` or equivalent annotations are evaluated by the
  display name content, not the method name.
- Severity assignments follow the skill's classification rules.
- Suggested patterns are specific to the test, not generic boilerplate.
- Summary includes breakdown by issue type, severity, and hotspot files.
- If all test names pass, the report states this with the count checked.

## Fail Conditions

- Any finding references a test name or file:line that does not exist.
- A `describe` or `context` block name is flagged as a finding.
- A test with a sentence-style `@DisplayName` is flagged based on its method
  name instead.
- Severity assignment contradicts the skill's classification rules.
- Suggested patterns are generic (e.g., "use a better name") rather than
  specific to the test's context.
- The report is missing the findings table or summary section.
- Framework-idiomatic naming conventions (Go's `TestFoo_Bar_Baz`) are flagged
  when each segment adds meaning.

## Common Failure Modes

- **Flagging describe blocks**: The agent treats `describe("UserAuth", ...)`
  as a test case and flags "UserAuth" as too short.
- **Ignoring DisplayName**: The agent evaluates the Java/Kotlin method name
  `testA()` without checking that `@DisplayName("should reject expired tokens")`
  provides a sentence-style name.
- **Overly strict on Go conventions**: Flagging `TestParseFoo_InvalidInput`
  as abbreviated when the Go convention uses underscores to separate
  subtest conditions.
- **Generic suggestions**: Suggesting "use a descriptive name" instead of a
  concrete pattern like "should return 404 when user not found".
- **Missing parameterized tests**: Not recognizing `@ParameterizedTest` or
  `pytest.mark.parametrize` names as test names that need evaluation.

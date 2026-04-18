# Rubric: hone:method-brevity-audit

## Pass Conditions

- Report includes a Markdown table of findings ranked by line count descending.
- Every finding includes method name, file path with line range, line count,
  and language.
- All reported file paths and line ranges are verifiable in the repository.
- Methods below the configured threshold do not appear in findings.
- Files in excluded directories do not appear in findings.
- Summary section includes total methods scanned, count over threshold, and
  distribution buckets.
- If no methods exceed the threshold, the report states this explicitly.

## Fail Conditions

- Any finding references a file path or line range that does not exist.
- A method below the threshold is included in the findings.
- A method from an excluded directory appears in the findings.
- Line counts are off by more than 2 lines from the actual method length.
- The report is missing the findings table or summary section.
- The report includes fabricated file paths or method names.
- The report omits the threshold value or scan statistics.

## Common Failure Modes

- **Miscounting closing braces**: The agent counts to the wrong line because
  it misidentifies the method's closing delimiter, especially in languages
  with implicit block endings (Python, Ruby).
- **Counting blank lines inconsistently**: Some methods appear longer or
  shorter depending on whether trailing blank lines are included.
- **Missing nested functions**: The agent reports the outer function but misses
  inner functions or lambdas that also exceed the threshold.
- **Including generated code**: The agent scans files in `dist/`, `build/`, or
  `vendor/` that should be excluded by default.
- **Incorrect language detection**: Files with unusual extensions or polyglot
  content are assigned the wrong language.

# Rubric: hone:duplication-hunt

## Pass Conditions

- Report includes findings grouped or ranked by extraction value score.
- Each finding states the duplication type (exact, renamed, or structural),
  occurrence count, block size, and all locations with file:line ranges.
- All reported file paths and line ranges are verifiable in the repository.
- Code previews are real snippets from the referenced files.
- Extraction suggestions name a function, list parameters, and identify the
  target location.
- Summary includes breakdown by type, total duplicated lines, and highest-value
  extraction candidates.
- Intentional boilerplate (license headers, short import blocks, trivial
  getters/setters) is not flagged.

## Fail Conditions

- Any finding references a file path or line range that does not exist.
- Code previews do not match the actual code at the referenced locations.
- An exact-duplicate finding is not actually identical across its locations.
- A renamed-duplicate finding does not have the same structure when identifiers
  are replaced.
- License headers, import blocks of 3 lines or fewer, or trivial
  getters/setters are flagged.
- Extraction suggestions are vague (e.g., "extract to a shared function")
  without naming the function or listing parameters.
- The report is missing findings or summary sections.

## Common Failure Modes

- **Flagging license headers**: Every file starts with the same 5-line license
  block, producing a high-occurrence "finding" that is not actionable.
- **Over-matching imports**: Reporting similar import blocks as duplicates when
  they differ by one or two imports.
- **Missing structural duplicates**: The agent finds exact copies but fails to
  identify code with the same control flow and different variable names.
- **Impractical extraction suggestions**: Suggesting extraction of code that
  has too many context dependencies to be cleanly shared.
- **Counting overlapping windows**: The same long duplicate is counted multiple
  times because sliding windows overlap, inflating the occurrence count.

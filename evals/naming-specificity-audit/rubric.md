# Naming Specificity Audit Rubric

## Pass Conditions

- Every finding includes a file path, line number, current name, and
  suggested replacement.
- Suggested names are derived from the code's actual behavior, not a
  mechanical suffix swap (e.g., not just `Manager` -> `Service`).
- Framework-conventional names are excluded or explicitly noted as
  idiomatic.
- Entities that do too many things are flagged as design concerns
  with low confidence, not presented as simple renames.
- The report includes a summary, findings table, design concerns
  section, and prioritized action list.

## Fail Conditions

- Findings lack file paths or line numbers.
- Suggested names are generic swaps unrelated to the code's behavior
  (e.g., `DataManager` -> `DataService` with no analysis).
- Framework-conventional names are flagged without acknowledging the
  framework context.
- No distinction is made between naming problems and design problems.
- The skill expands scope into variable naming, casing style, or
  other concerns outside its mandate.

## Common Failure Modes

- **Mechanical suffix swapping**: replacing one vague suffix with
  another without reading the code (Manager -> Service -> Handler).
- **Missing framework detection**: flagging every `Controller` in a
  Rails or Spring app as vague.
- **Ignoring god objects**: suggesting a rename for a 500-line class
  that does 8 things, when the real fix is decomposition.
- **Over-reporting**: flagging every function with `handle` in its
  name, including legitimate event handler methods.
- **No prioritization**: presenting all findings as equal instead of
  highlighting the highest-impact renames.

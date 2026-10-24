---
name: code-review-dod
description: Review the changes of a git branch against the Definition of Done and the acceptance criteria of its user story. Writes TODO comments into the code and commits them to a separate review branch. Use before merge.
---

# Code Review against the Definition of Done

Review the diff of a branch against the story and the team's rules.

## Input
- The Definition of Done (DoD)
- User story with acceptance criteria
- The git branch to review

## Steps
1. Read the diff against the target branch.
2. **Story fit.** For each acceptance criterion find the code and the test that cover it. Report criteria without both.
3. **DoD.** Check every DoD item (tests green, docs updated, no new warnings, logging, error handling, and so on).
4. **Quality.** Look for bugs, unclear names, duplicated logic, missing error handling, changes unrelated to the story.
5. **Findings.** Give each finding a severity: `blocker`, `should fix`, `nit`. Add the file and line.
6. Put each finding into the code as `// TODO(review): <finding>` on a new branch `review/<branch>`. Do not touch the original branch.

## Output
- Summary: verdict (approve / changes requested) and counts per severity
- Findings list with file, line, severity, reason, proposed fix
- Coverage table: acceptance criterion -> code -> test

## Rules
- A review comment must contain a reason. No bare "please change".
- Do not rewrite code in the review. Propose; the author changes.
- Report what is good in one short line so the author knows what to keep.

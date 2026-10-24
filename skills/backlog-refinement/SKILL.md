---
name: backlog-refinement
description: Review a user story before it enters a sprint. Checks acceptance criteria, Definition of Ready, testability and feasibility, then returns a reworked story with comments. Use when a user story is created or changed, or when the team prepares refinement.
---

# Backlog Refinement

Review one user story and return a reworked version. Do not change scope on your own: propose, do not decide.

## Input
- The user story (title, description, acceptance criteria)
- The Definition of Ready (DoR), if the project has one
- Optional: related stories, repository access for feasibility checks

## Steps
1. **Structure.** The story follows "As a <role> I want <goal> so that <benefit>". Flag a missing role, goal or benefit.
2. **Acceptance criteria.** Each criterion is observable and testable. Rewrite vague wording ("fast", "user-friendly") into measurable terms or mark it as an open question.
3. **Definition of Ready.** Check every DoR item and list the ones that are not met.
4. **Feasibility.** Look at the code base for existing components, risky areas and missing interfaces. Name concrete files or modules, not guesses.
5. **Size.** If the story is too large for one sprint, propose a split along user-visible slices.
6. **Estimate hint.** Give a rough size (S/M/L) with a one-line reason. The team still estimates.

## Output
Return exactly these sections:
- `Verdict`: ready / needs rework / too large
- `Reworked story`: the improved text and acceptance criteria
- `Comments`: one bullet per finding, each with the reason
- `Open questions`: what the product owner has to answer

## Rules
- Never delete an acceptance criterion. Mark it as changed and explain why.
- Keep the author's language (German or English).
- Write the result as a comment on the story, not as a silent rewrite.

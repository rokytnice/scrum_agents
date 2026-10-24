---
name: specification
description: Write a structured specification for a user story next to the code, based on the story and the repository. Use at the start of implementation so that humans and agents work from the same text.
---

# Specification

Turn a user story into a short specification that lives in the repository and is committed with the code.

## Input
- User story with acceptance criteria
- The code repository

## Steps
1. Read the story and the code areas it touches. List the files and modules involved.
2. Write the specification file `docs/specs/<story-id>-<slug>.md` with these sections:
   - **Goal**: one sentence
   - **Behaviour**: numbered, testable statements, one per acceptance criterion
   - **Interfaces**: changed or new APIs, events, database fields
   - **Out of scope**: what is explicitly not done
   - **Risks and open points**
   - **Test notes**: what the testing agent should cover
3. Where the spec refers to code, add a short comment at that place: `// SPEC <story-id>: <statement number>`.
4. Link the spec from the story.

## Rules
- Every statement maps to an acceptance criterion or is marked as an assumption.
- Do not change production code in this step. Only the spec file and comments.
- Keep it under two pages. A long spec is not read.

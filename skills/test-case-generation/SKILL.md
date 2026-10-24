---
name: test-case-generation
description: Generate test cases from a user story and its specification, including edge cases and negative cases, and write them as runnable tests in the project's framework. Use after the specification exists and before or during implementation.
---

# Test Case Generation

Derive tests from the story, not from the implementation, so the tests check the requirement.

## Input
- User story with acceptance criteria and the spec from the specification step
- The code repository (to find the test framework and conventions)

## Steps
1. Detect the test framework and naming rules from existing tests (for example JUnit 5, pytest). Follow them.
2. For each acceptance criterion write at least one **positive** test.
3. Add **negative** and **edge** cases: empty input, limits, wrong types, missing permissions, concurrent access, time zones where relevant.
4. Name each test after the behaviour (`rejects_expired_token`), and add the story id in a comment or tag.
5. Mark tests that need external systems and use fakes or test containers, as the project does.
6. Run the tests. New tests that fail because the feature is missing are expected. Tests that fail for other reasons are fixed.

## Output
- Test files in the project's test directory
- A table: acceptance criterion -> test names
- A list of criteria that could not be tested automatically, with the reason

## Rules
- Never weaken an assertion to make a test pass.
- Do not test private implementation details.
- Do not commit generated tests that were not run.

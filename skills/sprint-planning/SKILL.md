---
name: sprint-planning
description: Check a proposed sprint against dependencies, capacity and absences and report a planning verification with warnings. Use during sprint planning or when the sprint scope changes.
---

# Sprint Planning Check

Verify a sprint proposal. You report risks; the team decides.

## Input
- Selected user stories with estimates
- The backlog (for dependencies on stories outside the sprint)
- Developer capacity and the time-off calendar
- Sprint length and holidays

## Steps
1. **Dependencies.** Build a list of "story A needs story B". Warn if B is not in the sprint or comes later in the planned order. Check shared code areas, database migrations and API changes as hidden dependencies.
2. **Capacity.** Compute available person-days (team size x working days - absences - holidays - meetings). Compare with the sum of estimates, using the team's recent velocity if it is known. Report the load as a percentage.
3. **Skills.** Warn when a story needs knowledge that only one person has.
4. **Order.** Propose a sequence that unblocks others first and puts risky stories early.
5. **Buffer.** Warn if there is no room for bugs and unplanned work.

## Output
- `Verdict`: ok / warnings / not realistic
- `Capacity`: available vs. planned, as numbers
- `Dependency list`: each with status
- `Warnings`: short, one per line, ordered by severity
- `Proposed order`

If warnings exist, format the first block as a message for the team chat.

## Rules
- Show the calculation, not only the result.
- Treat missing data (no calendar, no estimates) as a finding, do not invent numbers.

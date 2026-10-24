---
name: architecture-review
description: Check whether a change fits the documented architecture and decisions, and whether it needs a new architecture decision record. Use for changes that add modules, dependencies or interfaces.
---

# Architecture Review

Check a change against the architecture documentation and the decision records.

## Input
- The diff or branch
- Architecture documentation and ADRs in the repository (for example `docs/architecture`, `docs/adr`)

## Steps
1. Find the building blocks the change touches and compare with the documented structure.
2. Check dependency direction and layer rules (for example no domain code depending on infrastructure).
3. Check new dependencies, interfaces and data flows against existing ADRs.
4. Decide whether the change needs a new ADR. If yes, draft it: context, decision, alternatives, consequences.
5. Name the quality attributes at risk (performance, security, maintainability, operability).

## Output
- Verdict: fits / fits with remarks / violates a decision
- List of violations with the ADR or rule they break
- Draft ADR, if needed

## Rules
- Quote the rule or ADR you rely on. If none exists, say so instead of inventing one.
- Prefer a small ADR over a long discussion.

---
name: security-review
description: Check changed code for common security problems such as injection, broken authentication, secrets in code, unsafe deserialization and vulnerable dependencies. Use as an extra review step or as a CI gate.
---

# Security Review

Look at the diff through a security lens. Findings, not fixes.

## Checks
- Input handling: SQL/command/template injection, path traversal, unvalidated redirects
- Authentication and authorization: missing checks, trust in client data, weak session handling
- Secrets: keys, tokens and passwords in code, config or test data
- Data: personal data in logs, missing encryption, overly broad responses
- Dependencies: new or changed libraries with known vulnerabilities (use the project's audit tool)
- Configuration: debug flags, permissive CORS, default credentials

## Output
Findings list with file, line, class (for example OWASP category), severity (`critical`, `high`, `medium`, `low`), and a concrete remediation. State clearly when a point could not be checked.

## Rules
- Never print a found secret in full. Show the first characters and the location.
- Do not run exploits against running systems.
- Severity follows impact and exploitability, not the number of occurrences.

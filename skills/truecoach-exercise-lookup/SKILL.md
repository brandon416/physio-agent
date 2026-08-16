---
name: truecoach-exercise-lookup
version: "1.0"
verified_on: [ara]
mia: NOT_RUN
wanda: NOT_RUN
---

# truecoach-exercise-lookup

Read-only TrueCoach exercise library lookup. First tracer skill.

## Goal

Look up one exercise by name and report its id plus key fields.

## Trigger

Captain routes a packet with `skill_id = truecoach-exercise-lookup`.

## In scope

- Search the exercise library
- Return identity fields that the MCP or CLI actually returned

## Out of scope

- Any write, copy, program change, or client message
- Browser or UI automation

## Procedure

1. Load `cli-anything-truecoach` only if a CLI dry-run is required. Prefer TrueCoach MCP search.
2. Search by the fixture exercise name.
3. Record exercise id, name, and the source tool used.
4. Stop. Do not attach the exercise to a client.

## Safe fixtures

Use a generic library name such as `plank`. Do not use a client program.

## Critical checks

- Exercise identity matches the search
- No write tools were called
- Evidence names the MCP or CLI read used

## Prohibited effects

Live client mutation. Wrong environment. Browser automation.

## Stop / BLOCKED

Missing auth, missing tool, or any write attempt -> `BLOCKED`.

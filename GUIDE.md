# Exercise Guide - SPEC-1

## Goal

Produce a functional specification from a simple user story.

## Steps

1. Open Copilot Chat in Plan Mode.
2. Paste the content of `repo/user-story.md`.
3. Ask Copilot:

```text
Split this into functional requirements with acceptance criteria, organized by endpoint.
Structure the result into: Overview, Endpoints, Data model, Error handling, Constraints.
```

4. Refine the result by adding REST, JSON, HTTP status and field-type constraints.
5. Check that every requirement is testable and unambiguous.
6. Save the final result in `repo/spec.md`.

## Expected Output

`repo/spec.md` should include:

- Overview.
- Data model.
- CRUD endpoints.
- Error handling rules.
- Technical constraints.

## Completion Criteria

The exercise is complete when the specification can be used as input for the next design exercise without additional clarification.

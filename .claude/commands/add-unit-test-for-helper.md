---
name: add-unit-test-for-helper
description: Workflow command scaffold for add-unit-test-for-helper in ChatGPT-Next-Web.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-unit-test-for-helper

Use this workflow when working on **add-unit-test-for-helper** in `ChatGPT-Next-Web`.

## Goal

Adds a new focused unit test file for a specific helper or function, improving test coverage for pure functions or utilities.

## Common Files

- `test/*.test.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify a helper or utility function that lacks test coverage.
- Create a new test file named after the helper in the 'test/' directory (e.g., test/helper-name.test.ts).
- Write focused, additive unit tests covering all relevant branches and cases for the helper.
- Ensure no existing files are modified or removed.
- Verify tests pass locally (e.g., yarn test:ci).

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.
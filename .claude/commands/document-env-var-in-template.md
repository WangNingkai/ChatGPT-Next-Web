---
name: document-env-var-in-template
description: Workflow command scaffold for document-env-var-in-template in ChatGPT-Next-Web.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /document-env-var-in-template

Use this workflow when working on **document-env-var-in-template** in `ChatGPT-Next-Web`.

## Goal

Documents a previously undocumented environment variable in the .env.template file, ensuring all supported configuration options are discoverable.

## Common Files

- `.env.template`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify an environment variable used in the code (e.g., in app/config/server.ts) that is missing from .env.template.
- Add the variable to .env.template with a descriptive comment.
- Ensure the comment is consistent with documentation elsewhere (e.g., README).
- Commit the change with a descriptive message.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.
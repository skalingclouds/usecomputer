---
name: ci-workflow-update
description: Workflow command scaffold for ci-workflow-update in usecomputer.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /ci-workflow-update

Use this workflow when working on **ci-workflow-update** in `usecomputer`.

## Goal

Modifies the GitHub Actions CI workflow to add, fix, or enhance build, test, or release automation.

## Common Files

- `.github/workflows/ci.yml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit .github/workflows/ci.yml with required changes.
- Commit with a message describing the CI fix or enhancement.
- Push to repository to apply new CI behavior.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.
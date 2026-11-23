---
name: vibe-workflow
description: An opt-in Vibe Coding workflow for websites and web apps. Use only when the user explicitly invokes vibe-workflow to initialize or reconcile project docs or run a selected development stage.
license: MIT
---

# Vibe Workflow

Use this workflow for websites of any size or stack. Read applicable repository instructions, then the relevant docs and implementation. Use source, scripts and CI for current behavior, and accepted decisions for expected behavior. Treat the target project as the only source of project-specific facts.

Write deliverables in the requested language or follow the project's documentation convention. Use the user's language when the project has no convention. See the [output language rules](references/project-docs.md#output-language).

The user can append a short operation or describe the task in plain language. A bare explicit invocation runs `init`. A request about the skill itself is handled as that request.

| Operation | Result |
| --- | --- |
| `init` | Initialize or reconcile site development docs and stop after document checks |
| `design` | Create or update only the site's visual design specification: theme, principles, and reusable style rules |
| `spec` | Define intent and observable acceptance criteria |
| `plan` | Break work into verifiable tasks |
| `build` | Implement and verify the requested change |
| `test` | Run relevant checks and report evidence |
| `review` | Review the actual diff and report actionable findings |
| `ship` | Check release readiness. Deploy only when explicitly requested for the target |
| `todo` | Report tracker status by default. Update it when requested |

For `init` and `design`, read [project-docs.md](references/project-docs.md), resolve the target site before writing, and reuse its existing documentation. If multiple sites fit and the target matters, confirm which one to use.

For a stage or concrete website task, read the relevant section of [stages.md](references/stages.md) and follow its stopping point. Start from existing specs, plans, changes, or other inputs when available. For implementation, infer ordinary acceptance checks from the request and project, verify at the appropriate scope and inspect the diff.

Small, clear edits need a short loop. A new user journey, shared design change, or migration can benefit from an explicit plan or a focused prototype first. Ask only when a missing decision materially changes direction, scope, compatibility, or authorization. Honor user-specified checkpoints. Keep work within scope and report the result, actual checks, and meaningful limits.

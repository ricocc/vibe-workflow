# Development Workflow

## Local Development

{{Record the confirmed runtime, prerequisites, and startup steps. List actual check commands or link existing instructions. Note material toolchain decisions that remain open.}}

## From Request to Delivery

1. Read `AGENTS.md` and the docs relevant to the task. Use the spec for product scope and acceptance. {{Link the project's actual design document or section when available.}}
2. Establish the intended outcome. Implement clear local changes directly. For cross-page work, important design decisions, or multi-session tasks, capture short acceptance criteria and an implementation order. Start with the smallest usable path.
3. Verify the change using the checks below. Report the delivered outcome, actual checks, and unresolved questions.

## Verification Scope

Choose the smallest check that can detect a problem with the change and complete any checks the project requires.

| Change | First check |
| --- | --- |
| Copy, docs, or links | Inspect the rendered result, changed text, or link target. |
| Single-page styling | Inspect the affected page in a browser. Check relevant viewports, themes, or focus states. |
| Local interaction or defect | Exercise the affected user journey. Prefer an existing focused test or direct reproduction. |
| Shared layout, routing, data, or build | Verify representative affected paths and run broader project checks as warranted. |

Add tests when requested, required by the project, or needed for a specific regression that existing checks miss. Stop once the relevant checks pass. Rerun or expand verification when later changes, new failures, unresolved acceptance questions, or release rules call for it. Report actual results and material gaps.

{{Optional. Link the project's focused checks, build, and CI rules. Remove irrelevant check categories.}}

## Tasks and Handoff

{{Link the actual TODO file or issue tracker and provide a starting point for the current task when useful.}}

Record the outcome to carry forward, the next step, and blockers. Update the relevant task after verification. Start deferred work when it has been brought into scope.

## Release

{{Keep this section when the project has a release process. Link the actual release guide and include relevant pre-release and live checks.}}

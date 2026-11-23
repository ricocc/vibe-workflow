# Development stages

Read AGENTS.md and only the files relevant to the selected stage. Use the existing doc or tracker locations. See [project-docs.md](project-docs.md) for their responsibilities.

## Spec

For a separate feature spec, use [FEATURE-SPEC](templates/FEATURE-SPEC.md) and the [feature document rules](project-docs.md#feature-documents-and-design-references).

Describe the user outcome, scope and acceptance criteria that a person can observe. For site work include the main user journey and relevant screen sizes, states and accessibility behavior. Read the project's actual design source when appearance or interaction changes. Label unresolved choices and ask when resolving one would materially change the design or product. In standalone spec mode return the specification and update the canonical spec when requested or needed for a substantial handoff. Stop before coding.

## Plan

For a separate implementation plan, use [PLAN](templates/PLAN.md) and the [feature document rules](project-docs.md#feature-documents-and-design-references). Keep brief plans in the conversation or canonical tracker.

Find the impacted surfaces, dependencies and hardest uncertainty. Break substantial work into small end-to-end changes with a verification for each. A clear local edit usually needs one step. Record a longer plan in the existing tracker or format if it will be resumed later. Record dependencies only where they affect ordering. Standalone planning stops before implementation and may update docs or task records.

## Build

Follow the accepted spec, design and relevant repo conventions. Reuse existing patterns. For uncertain visual work, validate a simple static screen or working interaction before polishing. For a new journey, make the smallest complete path usable before extending it. Keep adjacent improvements outside the diff unless required for acceptance. Verify the result using Test, review the diff for scope and regressions, and update the existing task entry when one exists. Commit only within the user's authorization.

For a browser-facing change, select a real user path from the target project. State the starting page and state, the user's action and the observable result. Trace the implementation from the entry point through the action to the result. For a bug fix, reproduce the reported failure before editing when feasible. Carry the same path into browser acceptance.

## Test

Start with the smallest check that can fail if the intended behavior is wrong.

| Change | Usually sufficient first check |
| --- | --- |
| Text, docs or links | Read the actual changed content and check the affected links or output |
| Local appearance | Inspect the affected page or state in the browser. Include narrow viewport, theme or keyboard checks when the change could affect them |
| Interaction or a localized bug | Exercise the relevant user journey and specific regression. Prefer the project's focused existing test or a direct reproduction |
| Shared styles, routing, auth, data, build or deployment | Verify representative dependent journeys, then run the project-defined broader checks the changed surface warrants |

Run mandatory project checks. Add a regression test when requested, required, or needed to cover a concrete regression existing tests miss. Widen coverage when the change affects shared behavior, evidence shows wider impact, or a release procedure requires it. Use TDD when it adds regression protection or the project requires it. Once acceptance has sufficient evidence, stop. A subsequent change, new failure, or unresolved acceptance question is a reason to re-run or expand checks. Report the checks and results actually observed, along with any gaps that affect confidence.

### Browser acceptance

Use the project's local or approved preview when a change affects browser behavior. Start from the real route and relevant state. Choose the viewport, input method and test data from the affected behavior and the project's requirements.

1. Perform the action through the controls available to the user. For example, use the visible UI to change a setting before activating a copy or export control.
2. Check the result on the receiving side. Read the clipboard, inspect the downloaded file, confirm the rendered state or check the stored result in an authorized test environment. Compare the result with the data or state selected before the action.
3. If a control fails, distinguish a UI problem, such as pointer interception or missing focus, from an environment problem, such as clipboard permission. Treat default behavior and a workaround as separate outcomes. Fix an in-scope failure and repeat the affected path.
4. Report the route, starting state, viewport or input method where it matters, action, expected result and observed evidence. Record build and type-check results separately. Keep any required path open when its behavior or evidence remains unverified.

## Review

Read the diff and enough surrounding code to judge impact. Compare against the request and design, check correctness and scope, and prioritize meaningful regressions with location, impact and evidence. Examine error states, accessibility, performance or data boundaries when affected. Review-only mode preserves the working tree. In implementation mode fix in-scope findings and recheck the affected behavior.

## Ship

Identify the requested environment and the actual release path. Reuse relevant build and verification evidence when the revision and environment match. Check release blockers, and consider rollback where deployment impact warrants it. Readiness mode reports whether the site is ready and what remains. An authorized release runs the existing deployment procedure and then checks the live site and affected user journey. Report the target, observed outcome and any remaining issue.

## TODO

When an authorized tracking action requires a new canonical file, use the [TODO template](templates/TODO.md).

Keep one canonical tracker. Use the existing issue tracker or TODO file, with these lightweight defaults when creating one:

- **Current** lists actionable work with an outcome and a verification. For an explicitly selected task, record its state and next step when a handoff is needed.
- **Blocked** records the concrete missing decision, dependency or access, plus the next step that can unblock it.
- **Later** holds deliberately deferred ideas. They stay outside the active task unless the user brings them into scope.
- **Recently done** is optional. Close active items only after their relevant acceptance conditions are verified. Add a short evidence note when it helps the next session.

Reuse or update an existing item instead of creating a duplicate. If several tasks could be meant, use the user's scope and available context to identify the intended one. Ask if selecting one would materially change what gets built. If the user asks to resume the next task, choose an explicitly prioritized, unblocked item. If they ask only for status, report it without touching the tracker. Do not move old backlog into the current task. Keep TODO updates within the requested work and preserve unverified items as open.

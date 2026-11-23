# Project Development Conventions

{{Briefly describe the site and main code entry points. Link the project spec, design document, development guide, and task tracker.}}

## Instructions and Sources of Truth

- Follow system, platform, and safety constraints. Within those constraints, prioritize the user's current explicit instructions over skill defaults and historical preferences. Apply project conventions within their directory scope.
- Keep shared agent conventions in this file. Link to it from compatibility files such as `CLAUDE.md` when needed.
- Use product constraints and confirmed decisions for expected behavior, and code, configuration, and scripts for current behavior. Verify live behavior against an actual revision, environment, and observation. Investigate discrepancies and preserve confirmed decisions.

## Autonomy, Scope, and Authorization

- Carry clear implementation requests through verification and handoff. Honor read-only requests and user-defined checkpoints.
- Keep small fixes focused. Fix issues that directly affect acceptance within scope and briefly report other findings. Bring deferred work into scope when authorized.
- Inspect the project and available context first. Ask when missing information materially affects delivery, design, compatibility, or authorization. Make reversible decisions independently and state material assumptions.
- Keep clarifications separate from approvals. Reuse existing authorization within its scope. Obtain approval for new unauthorized actions, material scope changes, or user-defined checkpoints. Continue independent work while dependent work waits for an answer.

## Using Skills

- Choose the approach that fits the task. Preserve business, format, and operational constraints and confirmed decisions. Use interviews, comparisons, and evaluations when the task benefits from them.

## Acceptance and Blockers

- Run the smallest sufficient checks for the change and any checks the project requires. {{Link the development guide's verification rules.}}
- Fix and recheck defects that affect acceptance within scope. Finish after delivery and required verification. Clean up temporary files created for the task when they serve no further purpose.
- When blocked, finish the independent work. Report what remains, verification limits, and the smallest input needed to proceed. Retry when conditions change or new evidence is available.

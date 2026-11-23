# Website project documents

## Inspect and initialize

Read applicable instructions, the README, existing design and planning docs, the site's routes or pages, shared styles, manifests, CI and scripts as relevant. For a blank project, use the user's brief and mark consequential unknowns as open. Record commands only when they are present or have been verified. Initialization creates docs and links. It does not install dependencies, scaffold code, commit, or deploy.

Use existing canonical locations. For a fresh setup, use the paths below. Link the files from AGENTS.md or the existing doc index. When a canonical document or issue tracker already serves the purpose, update it if authorized or point to it. Preserve user-authored decisions and add only missing material.

## Output language

Use the language explicitly requested for the deliverable. Otherwise, preserve the existing document's language when updating it, use the project's established documentation language for new files, and fall back to the language of the user's request. Apply this rule to headings and prose, including specs and plans written in chat. Preserve code identifiers, commands, paths, and machine-readable keys. When a requested format requires fixed headings or fields, keep them and localize the surrounding prose. Update section links when headings change.

## Template catalog

Read only the templates needed for the requested deliverable.

| Default destination | Template | Purpose |
| --- | --- | --- |
| `AGENTS.md` | [AGENTS](templates/AGENTS.md) | Project entry point and working rules |
| `DESIGN.md` | [DESIGN](templates/DESIGN.md) | Visual theme, design principles, and reusable style rules. See [Writing DESIGN.md](#writing-designmd). |
| `docs/PROJECT-SPEC.md` | [PROJECT-SPEC](templates/PROJECT-SPEC.md) | Site scope and acceptance |
| `docs/DEVELOPMENT.md` | [DEVELOPMENT](templates/DEVELOPMENT.md) | Local development and proportional verification |
| `docs/TODO.md` | [TODO](templates/TODO.md) | Canonical tracker, when an equivalent does not exist |
| `docs/ARCHITECTURE.md` | [ARCHITECTURE](templates/ARCHITECTURE.md) | Optional, for meaningful system boundaries and flows |
| `docs/DEPLOYMENT.md` | [DEPLOYMENT](templates/DEPLOYMENT.md) | Optional, for a real deployment process |
| `docs/specs/<feature-slug>.md` | [FEATURE-SPEC](templates/FEATURE-SPEC.md) | Optional, for a separate feature spec |
| `docs/plans/<feature-slug>.md` | [PLAN](templates/PLAN.md) | Optional, for a substantial implementation handoff |

Use the selected template as the baseline for a new document. Translate as needed, fill from inspected sources or the user's brief, and remove template cues and irrelevant optional sections. Preserve scope and proportionate verification rules unless project instructions require more. When reconciling existing docs, use templates to find gaps and keep the existing structure. Add optional docs only when requested or when they have distinct material. A short feature plan can live in the tracker. Cross-link instead of copying. Verify real paths, command names, links and removal of placeholders.

## Writing DESIGN.md

Write `DESIGN.md` as a visual design specification for future changes. Lead with the theme and actionable design principles. Describe the palette by semantic role, typography, spacing and layout, and other relevant visual foundations. Include component, responsive, motion, and accessibility rules where they express design intent that should carry forward. On a simple landing page, cover the visual foundations and the few rules that define its identity. Use the [DESIGN template](templates/DESIGN.md) as a menu of sections.

Use the [Web design writing reference](design-reference.md) when you need guidance on describing visual intent, semantic colors, component token references, or project-specific Do's and Don'ts. Derive project rules and values from the target implementation and confirmed design decisions. In the generated document, include source notes only for project-specific evidence or visual references selected for the project.

**Existing site.** Start from the canonical design reference and inspect the style sources. Extract recurring or explicit visual decisions as a working baseline. Give each rule a purpose and tell readers where to apply it. If a decision is inferred, label the baseline as inferred from the current implementation. Flag unresolved choices that affect the design. Verify representative styles when needed to distinguish intentional patterns from one-off implementation details.

**Document boundary.** Keep site inventories, interaction walkthroughs, implementation details, accessibility findings, browser test matrices, and test results in the relevant spec, review, or verification report. Mention a component or interaction in `DESIGN.md` only to establish a lasting visual or perceptual rule. Report incidental findings in the handoff when relevant. Create a separate audit only when requested.

**New site without visual direction.** Suggest the user browse [Refero Styles](https://styles.refero.design/) or [DesignMD.co](https://www.designmd.co/) for products with a similar audience, page type or user journey. Invite them to share a specific example and what they want to borrow, such as heading hierarchy, page spacing or image treatment. Use selected references to inform an original design and record what each one informs. Continue drafting the known project requirements and label undecided visual choices as open.

**Output format.** Use Markdown prose and source links for a simple site. Include YAML tokens when structured values help the project or the user requests the format. Preserve established token names, reference defined tokens from component rules and link to the authoritative definitions. For a [Google Labs-compatible document](https://github.com/google-labs-code/design.md/blob/main/docs/spec.md), use its field names and section order. A framework-specific mapping belongs in the document only when the project uses that framework and the mapping adds information. Use the project's existing validator when available, and check actual references, color pairs and visual acceptance criteria within scope.

**Before handing off.** Trace documented values to a project source or an agreed decision. Check that someone styling a new section can identify the palette, hierarchy, spacing, and what may vary. Retain only checks that describe how to recognize compliance with a design rule. Put actual verification results and material findings in the handoff.

## Feature documents and design references

When saving a standalone feature spec or implementation plan, use the user-specified destination first, then the project's established location, then the default path in the catalog. Reuse an existing document for that feature. For a new default filename, use a short kebab-case slug from the feature name. Keep brief plans in the canonical tracker or conversation as appropriate. Use a separate plan file when requested or warranted for a substantial handoff.

Resolve the design reference in DEVELOPMENT.md from the project's actual design source, even if it has a different name or is a section of another document. Use a relative link from the generated guide to that source. If initialization is creating the design doc in the same run, use its final path. If no design source exists or is in scope, remove the reference clause and keep the rest of the step.

During reconciliation, distinguish existing behavior, decisions, and future work. Keep old decision records when needed, and make the active choice easy to find. Verify links, paths, and command names. Docs-only initialization generally needs document checks. Report what was created, updated or reused and flag any material gaps.

# Vibe Workflow

[中文指南](README.zh-CN.md)

**Vibe Workflow is a Vibe Coding workflow for websites and web apps.** It helps you turn design rules, development conventions, and acceptance criteria into docs your AI assistant can follow. When you add features, fix bugs, or review changes, the assistant uses those same rules and reports the evidence behind its results.

## When to Use It

| Situation | What to ask the AI to do |
| --- | --- |
| Starting a new site or web app | Use the templates to create project docs and agree on working rules before implementation. |
| Taking over an existing site | Reuse existing docs and collect scattered conventions, design decisions, and development commands. |
| Adding a feature or fixing a bug | Define what should work, make the change, and verify the affected user journey. |
| Reviewing or preparing a release | Review the current changes or check release readiness as a standalone task. |

## Getting Started

```text
Use Vibe Workflow to organize the development docs for this website.
```

If your AI assistant can read project files, give it access to the workflow folder and point it to [SKILL.md](skills/vibe-workflow/SKILL.md). In a chat-only tool, share the relevant workflow instructions, templates, and project materials. The first request above asks for a review of the existing documents, updates to the relevant ones, and new files where useful. Specify the app directory if the repository contains multiple sites.

## Installation

From your project directory, run the following command with Node.js 22.20 or newer. Select your AI tool when prompted. Add `-g` to install for your user account across projects.

```sh
npx skills add ricocc/vibe-workflow --skill vibe-workflow
```

For a manual installation, download or clone the repository and copy the entire [skill folder](skills/vibe-workflow/) into the skills directory your tool reads. Keep `SKILL.md`, `agents/`, and `references/` together. For Codex, the destination is `.agents/skills/vibe-workflow/` in your project or home directory.

### Invoke the Skill

Select Vibe Workflow explicitly. For example, in Codex use one of these prompts.

```text
$vibe-workflow
$vibe-workflow design
$vibe-workflow review
```

In Codex, the first prompt runs `init` to organize project docs. The next two select the design document and read-only review stages.

## Project Docs

### Start a New Project

```text
Use Vibe Workflow to initialize the development docs for this new website.
```

Provide the site's purpose, audience, primary visitor action, and any confirmed technical or design decisions. The workflow uses its templates to create the relevant project docs and records open decisions for later. Initialization stops after preparing the docs. For an existing site, the workflow uses its established document locations and fills relevant gaps.

| Default file | Purpose |
| --- | --- |
| `AGENTS.md` | Project entry point and working agreements |
| `DESIGN.md` | Visual direction, responsive layout, components, and visual acceptance |
| `docs/PROJECT-SPEC.md` | Goals, scope, main journeys, and acceptance |
| `docs/DEVELOPMENT.md` | Local startup, project commands, and verification |
| `docs/TODO.md` | Current work, blockers, and handoff, when an equivalent tracker is unavailable |

### Continue Development

Keep the generated docs in the repository, with `AGENTS.md` linking to the relevant spec, design, development guide, and tracker. For assistants that load project instructions, `AGENTS.md` is the starting point for subsequent tasks. With other assistants, point them to that file or share the relevant excerpts. The project docs carry working rules across tasks. Invoke Vibe Workflow explicitly when you want to run one of its stages.

To work on the design document alone, ask for the site's `DESIGN.md`. A landing page can use short Markdown. Apps with shared components or multiple themes can add tokens and state rules where useful. [Project docs and templates](skills/vibe-workflow/references/project-docs.md#template-catalog) · [Design documentation guide](skills/vibe-workflow/references/project-docs.md#writing-designmd)

### Document Language

The skill instructions and templates are written in English. Generated project docs follow an explicit language request first. Otherwise they follow the existing document or project convention, then the language of the user's request. Code identifiers and commands keep their original spelling.

## Tutorial: Implement and Verify

Ask your assistant to follow Vibe Workflow and fix where focus lands after closing the mobile menu. It traces the relevant user path, reproduces the issue when feasible, implements the fix, and repeats the path on a local or approved preview. Browser verification checks where focus actually lands after the menu closes. [Browser acceptance guide](skills/vibe-workflow/references/stages.md#browser-acceptance)

## Command Reference

The table uses Codex short commands. In other tools, describe the same operation in plain language.

| Prompt | Result |
| --- | --- |
| `$vibe-workflow` or `$vibe-workflow init` | Initialize or reconcile site docs. |
| `$vibe-workflow design` | Create or update the site's design document. |
| `$vibe-workflow spec Search filters` | Describe the user journey and acceptance criteria. |
| `$vibe-workflow plan` | Break the work into verifiable steps. |
| `$vibe-workflow build Fix menu focus` | Implement the requested change and verify it. |
| `$vibe-workflow test` | Run relevant checks and report the results. |
| `$vibe-workflow review` | Review the current diff without editing. |
| `$vibe-workflow ship` | Check release readiness. |
| `$vibe-workflow todo` | Report the current tasks and blockers. |

## Limits

- Project scripts and CI enforce required build, test, and release checks.
- File editing, browser verification, and deployment depend on the tool's capabilities and permissions. Verification also depends on the available runtime and test data. Reports identify checks that remain unverified.
- Design docs use evidence from the target project and agreed decisions. Open design choices still need input.
- Release readiness can be checked on its own. Deployment requires an explicit request for a target environment and uses the project's release process.

## Reference Files

[Skill entry point](skills/vibe-workflow/SKILL.md) · [Project documentation guide](skills/vibe-workflow/references/project-docs.md) · [Stage reference](skills/vibe-workflow/references/stages.md) · [Design writing reference](skills/vibe-workflow/references/design-reference.md)

## License

[MIT](LICENSE).

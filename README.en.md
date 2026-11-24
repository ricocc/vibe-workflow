# Vibe Workflow

[中文指南](README.md)

**Vibe Workflow is an opt-in skill for documenting how a website or web app is built and how changes are verified.** Keep design decisions, development commands, and acceptance criteria with the project so an agent can pick up the work in a new session.

Ask for the job you need, such as organizing project docs, fixing a bug, or reviewing a diff. **The agent reads only the project materials and templates relevant to that task.** A small change can go straight to implementation and a focused check. A new user journey may need a spec or plan first.

## When to Use It

| Situation | What to ask the AI to do |
| --- | --- |
| Starting a new site or web app | Agree on the rules the project needs now and use templates where they help. |
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

### Choose Templates for the Project

```text
Use Vibe Workflow to initialize the development docs for this new website.
```

**For a new project, start with the decisions you need for the current work.** Share the site's purpose, audience, primary visitor action, and any confirmed decisions. A landing page might need an `AGENTS.md` for working agreements and a short `DESIGN.md` for layout and styling. Pick another template when a feature needs its own acceptance criteria or a real deployment process needs documenting. Record open decisions for later. Initialization stops after preparing the docs.

**For an existing project, start with what is already documented.** Keep startup and test commands in the README if they already live there. Keep tracking tasks in GitHub Issues if that is what the project uses. Read a template when it helps fill a specific gap. [Project docs and template catalog](skills/vibe-workflow/references/project-docs.md#template-catalog)

### Continue Development

Keep the relevant docs in the repository. Use `AGENTS.md` or the existing doc index to point to the spec, design guidance, development commands, and tracker as needed. For assistants that load project instructions, `AGENTS.md` is the starting point for subsequent tasks. With other assistants, point them to that file or share the relevant excerpts. The project docs carry working rules across tasks. Invoke Vibe Workflow explicitly when you want to run one of its stages.

To work on the design document alone, ask for the site's `DESIGN.md`. A landing page can use short Markdown. Apps with shared components or multiple themes can add tokens and state rules where useful. [Project docs and templates](skills/vibe-workflow/references/project-docs.md#template-catalog) · [Design documentation guide](skills/vibe-workflow/references/project-docs.md#writing-designmd)

### Document Language

The skill instructions and templates are written in English. Generated project docs follow an explicit language request first. Otherwise they follow the existing document or project convention, then the language of the user's request. Code identifiers and commands keep their original spelling.

## Use It with Other Skills

Use your preferred design or animation skill for layout and interaction details. Invoke Vibe Workflow when you want to organize project rules, verify a change, or review a diff. The agent can choose the implementation and how to present the result based on the task and repository.

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

- **Project scripts and CI enforce checks.** The skill guides the agent through the project's checks. Configure CI to block a merge or release when a required check fails.
- **Verification depends on tools and environment.** Editing files, opening a browser, and deploying require the relevant capabilities and permissions. If the site cannot run or the needed test data is missing, the agent reports what remains unverified.
- **You decide the design direction.** Templates help record what the project already does and which decisions you have made. Open choices can be left for later.
- **You can check release readiness on its own.** Use `ship` to find what's left before release. To deploy, explicitly request a target environment and use the project's existing release process.

## Reference Files

[Skill entry point](skills/vibe-workflow/SKILL.md) · [Project documentation guide](skills/vibe-workflow/references/project-docs.md) · [Stage reference](skills/vibe-workflow/references/stages.md) · [Design writing reference](skills/vibe-workflow/references/design-reference.md)

## License

[MIT](LICENSE).

# Writing Web Design Documentation

Describe the target project's visual hierarchy, style roles, component rules, and acceptance criteria using its actual pages, components, and styles.

## Make Visual Decisions Actionable

Start with what the visitor needs to do. Explain how layout, contrast, and type weight guide that action. State which action takes priority, which elements share a treatment, and when variants apply. If the project uses several button treatments, explain when to use filled, outlined, or text styles.

## Connect Values, Roles, and Components

| Topic | What to capture |
| --- | --- |
| Color | Group by purpose. Identify canvas, text, secondary content, and action foreground and background. Link their source or reference existing theme tokens. |
| Typography | Record actual fonts, sizes, weights, line heights, and tracking for representative roles. Explain when themes or breakpoints change them. |
| Components | Describe purpose and variants, then reference style roles. A primary action may use `primary` and `on-primary`. In structured docs, references such as `{colors.primary}` must resolve to defined tokens. |
| States and breakpoints | Describe the trigger and observable outcome. Pair foreground and background values when documenting themes. For small sites, cover the states that affect implementation. |

## Do's and Don'ts

### Do

- Ground each rule in a concrete role, component, or page. For a primary action, say when to use its filled treatment and identify the relevant color roles.
- Make important visual rules observable. For instance, define how the primary action retains its emphasis on a narrow screen. Keep verification steps and results in the handoff.

### Don't

- Avoid importing colors, fonts, or breakpoints from a reference without project evidence or a confirmed decision.
- Avoid recording a screenshot inference as verified interaction behavior. Check keyboard focus, theme switching, and error feedback against the implementation or actual page.

## Match the Project's Scale

For a landing page, capture the visual direction, palette, typography, spacing, and the few rules that define its identity. Add tokens, variants, and state styles where they guide future design decisions. Keep implementation discrepancies and browser findings in the handoff. If an unresolved design choice affects the specification, state the decision needed without expanding it into an audit. For a new site with open decisions, use the project documentation guide to select a visual reference.

---
name: "{{Project or design system name}}"
# Optional. Keep this YAML when structured tokens help the project. Enable applicable fields and remove unused examples.
# colors:
#   canvas: "{{Page background}}"
#   text: "{{Body text foreground}}"
#   primary: "{{Primary action background}}"
#   on-primary: "{{Primary action foreground}}"
# typography:
#   body:
#     fontFamily: "{{Actual font and fallback stack}}"
#     fontSize: "{{Actual size with units}}"
#     fontWeight: {{Actual weight}}
#     lineHeight: {{Actual line height}}
#     letterSpacing: "{{Actual letter spacing with units}}"
# spacing:
#   section: "{{Section spacing with units}}"
# rounded:
#   control: "{{Control corner radius with units}}"
# components:
#   page:
#     backgroundColor: "{colors.canvas}"
#     textColor: "{colors.text}"
#     typography: "{typography.body}"
#   button-primary:
#     backgroundColor: "{colors.primary}"
#     textColor: "{colors.on-primary}"
#     rounded: "{rounded.control}"
---

# {{Project Name}} Design

> See the [design writing reference](../design-reference.md) for visual hierarchy, color roles, component references, and Do's and Don'ts. Follow the [project documentation guide](../project-docs.md#writing-designmd) for source values and output rules. Remove this note from the generated document.

{{Keep visual principles and rules that should guide future design work. Use other documents or the handoff for observed defects, test results, and implementation inventories.}}

## Overview

{{Name the visual theme and describe two to four project-specific principles that guide future choices. Explain which visual elements carry emphasis, how the design balances density and space, and what should remain consistent across screens. Label inferred visual direction as a working baseline.}}

### Imagery and Icons

{{Optional. Describe the purpose, aspect ratios, composition, or treatment of photography, illustrations, product screenshots, and icons. Record visual references selected for this project and what they inform.}}

## Colors

{{Record actual project colors by role, such as canvas, surface, text, muted text, primary action and its foreground, link, border, focus, and status feedback. Map roles by theme where relevant. Reference existing YAML tokens or theme files and explain when to use them.}}

## Typography

{{Record actual font stacks and the sizes, weights, line heights, and tracking for headings, body text, and labels. Describe meaningful differences by role or breakpoint.}}

## Layout

{{Record content order, maximum content width, key spacing, and narrow-screen behavior for representative pages. For grids and breakpoints, give actual values and explain what changes, such as navigation collapsing, cards stacking, or the primary action moving.}}

## Elevation & Depth

{{Optional. Document meaningful levels such as page, overlay, and dialog. Reference the surfaces, borders, or shadows that distinguish them.}}

## Shapes

{{Optional. Record reusable corner radius, border, and shape rules for relevant controls, cards, and fields.}}

## Motion & Micro-interaction

{{Optional. Describe triggers, feedback, timing, easing, and reduced-motion behavior for actual interactions.}}

## Voice & Content Strategy

{{Optional. Record copy conventions that affect the interface, such as action labels and how errors explain the next step.}}

## Components

{{Include only components that demonstrate a reusable rule about hierarchy, styling, or visible feedback. Keep functional requirements and implementation inventories in their own documents.}}

### {{Component Name}}

- **Purpose** {{When to use it and which pages or variants it applies to.}}
- **Style** {{Reference tokens or component source and describe relevant backgrounds, text, borders, radii, or spacing.}}
- **States** {{List applicable default, hover, keyboard focus, selected, disabled, loading, empty, error, and success states.}}
- **Visual adaptation** {{Explain how the component preserves hierarchy, legibility, and visible feedback across relevant screen sizes or input methods.}}

## Do's and Don'ts

{{Adapt the following rules to the project's own roles, components, and situations. Keep rules that affect implementation.}}

### Do

- Use the approved primary-action colors for the defined primary actions and check text contrast.
- Use the project's heading hierarchy and section spacing to communicate content priority consistently.
- Preserve visible keyboard focus. Explain problems and actionable next steps in form feedback.

### Don't

- Avoid replacing existing role values with unconfirmed colors or spacing. Record the purpose of a new value when needed.
- Avoid conveying state through color or hover alone, especially for form errors, selected options, and touch interactions.
- Avoid preserving desktop layouts on narrow screens when they obscure important content, actions, or focus.

## Visual Acceptance

{{Optional. List a few observable criteria that directly enforce the visual system, such as preserved action prominence, visible focus, or sufficient contrast for a token pair. Keep browser test matrices and observed results in the verification handoff.}}

# Design Review Workflow

Use this reference when the user asks to review, compare, or align a design to Pulse.

## Inputs to Inspect

- Current screenshot or visible page.
- Source HTML/CSS or app route when available.
- Existing Pulse design-system files:
  - `design-system/handoff/design-system.html`
  - `design-system/handoff/figma-component-library.html`
  - `design-system/handoff/components/html-component-preview.html`
  - `design-system/handoff/components/tokens.css`
  - `design-system/component-library.md`
  - `design-system/ai-generation-guide.md`

## Review Order

1. Purpose
   - What decision does this screen support?
   - What should the user read or do first?
2. Information hierarchy
   - Are the most important items visually obvious?
   - Is hierarchy created by tone, type, spacing, and order?
3. Reading comfort
   - Are there too many horizontal blocks?
   - Can the screen be read vertically without tension?
4. Component fit
   - Does each repeated pattern map to an existing component?
   - Is a new component category actually needed?
5. Token fit
   - Are color, spacing, radius, shadow, and type values token-aligned?
   - Are repeated new values token candidates?
6. Handoff clarity
   - Can a designer tell what is canonical, illustrative, experimental, or pending extraction?

## Finding Format

Lead with direct, actionable findings:

- `High`: blocks correct understanding or creates a wrong system pattern.
- `Medium`: weakens hierarchy, reading comfort, token consistency, or component reuse.
- `Low`: polish, naming, documentation, or small consistency issue.

For each finding, include:

- Location.
- Problem.
- Why it matters in Pulse.
- Recommended change.

## Implementation Guidance

- If only review was requested, do not edit files.
- If the user asks to apply the changes, update the narrowest source first.
- For design-system source updates, switch to `pulse-design-system-sync`.
- Run link, anchor, grep, and diff checks for handoff HTML changes.

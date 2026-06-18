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
  - `design-system/component-roadmap.md`
  - `design-system/ai-generation-guide.md`
  - `demo/pulse-react/docs/design-system.md`

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
5. Product-pattern fit
   - Does the design match the right Pulse page type: report canvas, live feed, onboarding narrative, AI task panel, generation state, or preview surface?
   - If the task involves Analytics, Signal, onboarding, Studio, AI chat, or generation, read `pulse-product-patterns.md` and compare against those patterns.
   - If referencing onboarding, separate component/flow learnings from onboarding's standalone art direction before applying anything to the main app.
6. Token fit
   - Are color, spacing, radius, shadow, and type values token-aligned?
   - Are repeated new values token candidates?
7. Handoff clarity
   - Can a designer tell what is canonical, illustrative, experimental, or pending extraction?
8. State completeness
   - Are loading, empty, error, disabled, hover, focus, pressed, selected, and active states represented when relevant?
   - Do states use Pulse tokens and clear labels instead of ad hoc colors?
9. Responsive behavior
   - Does the layout collapse cleanly below 760px?
   - Do long labels, buttons, chips, and data rows fit without clipping or awkward overflow?
   - Do visual samples for grid, spacing, radius, surface, and shadow remain readable on small screens?
10. Motion and performance
   - Does motion explain state, progress, hover/focus, or generation?
   - Are animations limited to `transform` and `opacity` where possible?
   - Is there a reduced-motion path for anything long-running or repeated?
11. Content credibility
   - Does demo data feel specific to campaign, post, Studio, signal, or report workflows?
   - Are illustrative examples labeled instead of presented as canonical product truth?

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
- For runtime or preview changes, check the affected state cycle and responsive collapse before reporting done.

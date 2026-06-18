---
name: pulse-design-usage
description: Apply and review the Pulse design system on new pages, Figma frames, HTML drafts, screenshots, onboarding flows, analytics/report pages, signal feeds, AI generation states, and component proposals. Use when Codex or Claude needs to critique, adapt, or implement a design using Pulse rules for calm reading, tonal hierarchy, spacing, grid, surfaces, shadows, status color semantics, component fit, product-pattern fit, and designer-friendly handoff outputs.
---

# Pulse Design Usage

Use this skill to apply the Pulse design system to real design work. This is a usage and review skill, not the maintenance workflow.

- Use `pulse-design-usage` to review, adapt, or plan a design.
- Use `pulse-design-system-sync` when changing the design-system source files, component library, preview surfaces, or Figma handoff HTML.

This skill is written as plain `SKILL.md` plus Markdown references so both Claude and Codex can use it. Codex also reads `agents/openai.yaml` for UI metadata.

## Relationship To General Taste Skills

Use general frontend taste skills for broad craft checks, but keep Pulse rules in charge when there is a conflict.

Pulse overrides:

- Use Manrope and the Pulse token system instead of introducing generic premium font stacks.
- Use Pulse cyan, success green, and severity colors by meaning, not as decorative accent choices.
- Prefer calm vertical reading rhythm over generic bento, hero, or card-heavy layouts.
- Prefer standalone HTML/CSS component source and Figma handoff artifacts over React/Tailwind assumptions unless runtime work is explicitly requested.
- Treat onboarding references as a separate product/art direction. Extract reusable component anatomy, flow states, generation behavior, and interaction patterns; do not port onboarding's editorial visual style into the main app system.
- Keep motion restrained and stateful. Do not add perpetual decorative motion unless the user asks for it.

## Core Rule

Build hierarchy with tone, background layers, type weight, spacing, grid rhythm, and visual examples before adding borders. Borders and dividers are supporting tools, not the primary structure.

Avoid layouts that force users to scan many equal-weight horizontal blocks. Prefer calm vertical reading rhythm, grouped content, and clear priority.

## First Pass

1. Inspect the actual artifact before judging it.
   - Figma frame, screenshot, HTML, React page, or written spec.
   - Existing Pulse files when available:
     - `design-system/handoff/design-system.html`
     - `design-system/handoff/figma-component-library.html`
     - `design-system/handoff/components/html-component-preview.html`
     - `design-system/handoff/components/tokens.css`
     - `design-system/component-library.md`
     - `design-system/ai-generation-guide.md`
     - `demo/pulse-react/docs/design-system.md`
2. Identify the page purpose, primary action, decision hierarchy, and main user reading path.
3. Separate reusable structure from page-specific copy/data.
4. Decide whether the task is a review, a redesign direction, a component intake, or an implementation change.

## Usage Workflow

1. Run the visual hierarchy check.
   - Read `references/visual-hierarchy.md` when the task involves UI critique, layout polish, visual language, spacing, grid, shadows, or surface treatment.
2. Run the design review checklist.
   - Read `references/design-review.md` when the user asks "look at this", "compare", "what is missing", "align to design system", or "make it better".
3. Run the new design intake flow.
   - Read `references/new-design-intake.md` when a new page, external design, HTML draft, Figma frame, screenshot, or prototype should enter the Pulse system.
4. Check product-pattern fit.
   - Read `references/pulse-product-patterns.md` when the task involves Analytics, reports, Signal, onboarding, Studio previews, AI chat, AI generation, preview cards, modals, drawers, or live monitoring states.
5. Run the final preflight.
   - Read `references/preflight.md` before final review or delivery when the task affects a UI, component, token, preview, or handoff artifact.
6. If implementation is requested, make the smallest useful change and sync through `pulse-design-system-sync` when source files must be updated.

## Pulse Decisions

- Cyan `#49E0F5` is momentum, live/building, progress, positive delta, and active selection.
- Cyan 600 `#0ea5b8` is routine text or dot value.
- Cyan 700 `#0D7685` is the deepest cyan emphasis.
- Success green `#43BA51` is completion: done, approved, published, on-track.
- Red `#ef4444` (text `#dc2626`) protects now, amber `#f19a08` (text `#a1640b`) adjusts soon, and blue `#3987f3` (text `#1f6fe0`) replies / routes / schedules. These are severity or routing only — do not use cyan as generic decoration.
- Each semantic color runs a 6-stop ramp (`50/100` soft fills, `200` line, `500` base, `600` text/dot, `700` deepest) for cyan, success, red, amber, blue, and indigo. Full values live in `design-system/handoff/components/tokens.css`.
- Stage, panel, reading surface, and rare ink anchor should be visible as layers.
- Grid, spacing, radius, and shadow guidance should be shown with visual samples when documenting the system, not only text rows.
- Loading, empty, error, disabled, hover, focus, pressed, selected, active, and responsive states should be considered before calling a component ready.
- Motion should explain state, progress, or generation. Animate `transform` and `opacity`; avoid decorative loops and layout-thrashing properties.
- Generation and onboarding waits should never be spinner-only. Show what is being read, generated, or validated, and keep a useful preview, example report, or process state visible while the system works.
- Onboarding art direction is not the main app art direction. Use onboarding only as evidence for useful components and states such as steppers, input stacks, upload zones, confirmation docks, generation status, and report previews.
- Demo content should feel specific to campaigns, posts, Studio work, signals, or reports. Mark illustrative data clearly.

## Output Shape

For reviews, lead with concrete findings, then fixes:

1. What is working.
2. What violates Pulse hierarchy or reading rhythm.
3. What to change, grouped by priority.
4. Which components/tokens/patterns are reusable.
5. What should go to docs, component source, preview, or Figma handoff.

For implementation tasks, report:

- Files changed.
- Which layer changed: page, component source, preview, Figma handoff, docs, or tokens.
- Which checks ran.
- Any missing component contract, token, accessibility, or preview work.

## Do Not

- Do not copy another design system's visual style into Pulse.
- Do not add nested bordered cards to solve unclear hierarchy.
- Do not create dense rows of equal-weight cards unless direct comparison is the task.
- Do not turn every pattern into a React component. React/runtime work only happens when explicitly requested.
- Do not present a Figma handoff specimen as engineering source.

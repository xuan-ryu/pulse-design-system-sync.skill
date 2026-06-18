# Final Preflight

Use this reference before final review or delivery when a task affects a Pulse UI, component, token, preview, or handoff artifact.

## Pulse Fit

- Hierarchy comes from tone, background layers, type, spacing, grid rhythm, and depth before borders.
- Horizontal rows of equal-weight blocks are reduced unless direct comparison is the task.
- Nested bordered cards are avoided unless the child is independently interactive, selected, focused, or truly separate.
- Cyan, success green, red, amber, and blue are used by semantic meaning.
- Onboarding references do not override main app art direction; only style-independent component and flow patterns transfer.

## Component And Token Fit

- Reusable patterns are mapped to existing component categories or marked as candidates.
- Product page patterns are mapped when relevant: report canvas, live feed, onboarding narrative, AI task panel, generation state, or preview surface.
- Page-specific copy/data is not baked into shared components.
- Repeated spacing, color, radius, shadow, type, or motion values use tokens or are marked as token candidates.
- The landing layer is clear: docs, component source, HTML component preview, Figma component library, or feature-local.

## State And Interaction

- Relevant states are covered: loading, empty, error, disabled, hover, focus, pressed, selected, active, pending.
- Focus remains visible.
- Error and empty states explain the next useful action.
- Generation and onboarding waits show live process context and useful preview content, not spinner-only loading.
- Motion explains state, progress, generation, or user feedback.
- Animations use `transform` and `opacity` where possible and have a reduced-motion path when repeated or long-running.

## Responsive And Text Fit

- Multi-column layouts collapse cleanly below 760px.
- Text in buttons, chips, cards, data rows, and panels does not clip or overlap.
- Grid, spacing, radius, surface, and shadow visual samples remain readable on small screens.
- Fixed-format UI elements have stable dimensions and do not shift when labels or states change.

## Content And Handoff

- Demo data is specific to Pulse work: campaigns, posts, Studio review, signal queues, reports, approvals, or source citations.
- Illustrative examples are labeled when they are not canonical product truth.
- Designers can tell what is canonical, component source, preview, Figma handoff, needs extraction, token candidate, or experimental.
- If source files were changed, switch to or apply `pulse-design-system-sync` and run its sync checks.

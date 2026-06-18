# Visual Hierarchy Checklist

Use this reference when reviewing or improving the visual design of a Pulse page, component, or handoff artifact.

## Reading Rhythm

- Prefer top-to-bottom reading paths for dense operational work.
- Avoid rows with many equal-weight cards or data blocks.
- Use section headers, spacing, and grouped copy to show what belongs together.
- Keep side-by-side blocks for true comparison, paired decisions, or primary/secondary contrast.

## Borders and Dividers

- Treat borders as support, not hierarchy.
- Avoid nested borders unless an object is independently interactive, selected, focused, or truly separate.
- Use light dividers inside one larger container for local grouping.
- If structure feels unclear, adjust tone, background layer, type level, spacing, or content order before adding a border.

## Color and Tone

- Use neutral surfaces first.
- Use cyan only for momentum, live/building, progress, positive delta, and active selection.
- Use success green only for completed/approved/on-track states.
- Use red, amber, and blue for severity or routing.
- Do not fill whole containers with cyan just to make them important.

## Grid and Spacing

- Show grid and spacing visually when documenting the system.
- Use visual examples like column blocks, spacing bars, rail/content windows, and radius blocks.
- Keep common Pulse values visible: 8, 14, 22, 28, and 72.
- Collapse multi-column layouts to one column on small screens.

## Surfaces and Shadows

- Show stage, panel, reading surface, and ink anchor as visible layers.
- Keep resting surfaces mostly flat.
- Use shadow for hover/focus, overlays, and true elevation.
- Use ink anchors sparingly: one or two per view at most.

## Motion

- Use motion to explain state change, generation progress, hover/focus feedback, or routing.
- Avoid continuous decorative loops unless the user explicitly asks for an animated concept.
- Animate `transform` and `opacity`; avoid `top`, `left`, `width`, and `height`.
- Provide a reduced-motion fallback for long or repeated animations.

## Type and Weight

- Use size, placement, spacing, and medium weight for hierarchy.
- Avoid using bold everywhere to compensate for unclear layout.
- Keep body text readable and quiet.
- Use tabular numerals for metrics.

## Content Specificity

- Use concrete Pulse scenarios: campaigns, posts, Studio review, signal queues, reports, approvals, and source citations.
- Avoid generic names, generic companies, and decorative fake metrics.
- Label illustrative examples as illustrative when they are not canonical product data.

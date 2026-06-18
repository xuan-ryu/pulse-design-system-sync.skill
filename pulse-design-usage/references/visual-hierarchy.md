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
- Product UI spacing uses the token scale `--space-*`: `4 / 8 / 12 / 16 / 20 / 24 / 32 / 40 / 48 / 64 / 72`. The handoff-document rhythm (`8 / 14 / 22 / 28 / 72`) is for the static design-system pages, not product layout.
- Radius scale: chips `8`, groups `12`, cards `16`, large surfaces `22`; pills fully rounded. Step radius down with nesting; never repeat one radius across nested layers.
- Collapse multi-column layouts to one column on small screens.

## Surfaces and Shadows

- Show stage, panel, reading surface, and ink anchor as visible layers.
- Shadow depth follows a surface's place in the information hierarchy and its elevation — not its physical size. A small floating element can carry a strong shadow; a large flat background container carries none.
  - Overlay / floating layer (popover, modal, dropdown, dock, AI panel): strong shadow (`--shadow-3` / `--shadow-panel` / `--shadow-dock`).
  - Elevated primary surface — a card that is the view's main focus, lifted above the stage: light–medium resting shadow (`--shadow-1`–`--shadow-2`).
  - Base layer — page stage, section / background containers, flat tonal blocks, data-highlight (metric / stat) cards, buttons, and inline groups: no shadow; they read by tone, fill, spacing, and border.
- Add lift on hover / focus and for true elevation. Map to the `--shadow-*` tokens; never invent one-off shadows.
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

Heading ladder (Manrope), weights capped at medium (`500`):

- H1 `32` · H2 `24` · H3 `21` · H4 / card title `18`.
- Body `14` · caption / supporting `13` · meta `12.5` · label `11` · metric value `26`.
- Fixed `8px` gap between a title and its caption or body.
- Hero / cover and trend-hero titles may scale to `34–44`. Above that, only a report cover/hero display uses `--font-report` (Newsreader serif, `400–500`, clamp `64–96`) — never for body, UI, labels, numbers, or H1–H4.
- Hierarchy comes from size, spacing, position, and structure — never from a heavier weight.

## Content Specificity

- Use concrete Pulse scenarios: campaigns, posts, Studio review, signal queues, reports, approvals, and source citations.
- Avoid generic names, generic companies, and decorative fake metrics.
- Label illustrative examples as illustrative when they are not canonical product data.

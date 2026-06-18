---
name: pulse-design-system-sync
description: Keep the Pulse design system in sync across Markdown rules, engineering component-library source, preview surfaces, and single-file Figma handoff HTML. Use in the Pulse repo for design-system rules, component taxonomy and roadmap, component APIs, HTML/SCSS component-library structure, React/runtime extraction only when explicitly needed, token and standardization checks, new design or page intake, and Figma handoff updates, e.g. "update the design system", "sync to the component library", "reflect this in the handoff HTML", "add a component category", or "bring in this new design".
---

# Pulse Design System Sync

Use this skill to keep Pulse design-system changes synchronized across the
system surfaces:

1. Markdown rules and contracts.
2. Engineering component-library source.
3. Component preview surfaces.
4. Single-file HTML handoff boards used for Figma iteration/export.

The workflow must make engineering structure legible for designers. Do not rely
on designers to infer which docs, component sources, tokens, previews, and
handoff HTML must move together; run the synchronization and standardization
checks explicitly.

## Source Model

- Markdown docs define rules, taxonomy, component contracts, and execution
  plans.
- The engineering component library is structured source. It may use
  per-component HTML plus SCSS, or React/runtime components only when that layer
  actually exists and is requested.
- Component previews compose the individual component source files so designers
  and engineers can see the full library in one place.
- Single-file Figma handoff HTML files are bundled visual artifacts. They inline
  CSS so the whole board can be exported or moved into Figma.

Do not treat bundled Figma handoff HTML as engineering source. Do not assume a
design-system change must become a React component; choose the engineering form
that matches the actual component-library framework.

## Expected Component-Library Shape

When the dedicated engineering component library exists, expect this shape:

- Each component owns an individual source file, such as `button.html`, plus
  its own SCSS/CSS source.
- Components can be as granular as `Button`, `Input`, `MetricBlock`, or other
  named primitives/patterns.
- A preview surface under `components` imports or assembles individual
  component files so the whole library can be reviewed together.
- A separate Figma version bundles the same component specimens and CSS into a
  single self-contained HTML file. That file is for Figma import and visual
  iteration, not for engineering reuse.
- The preview should reference the component sources; the Figma version may
  duplicate compiled/inline CSS because portability is the goal.

## Standardization Guardrails

Before finishing any non-trivial design-system change, check:

- Component system fit: the change belongs to an existing component category or
  creates a clearly named category in the roadmap.
- API contract: shared components define props, variants, states, accessibility,
  interaction behavior, and empty/loading/error handling before broad reuse.
- Token alignment: color, spacing, radius, type, shadow, and state values come
  from existing tokens or create a documented token need.
- CSS architecture: engineering styles stay in SCSS/CSS source files; Figma
  handoff HTML keeps inline CSS only because it is an export artifact.
- Framework boundary: business-specific content stays in feature modules;
  reusable behavior and structure move into shared components.
- Designer handoff clarity: the HTML specimen names what is canonical, what is
  illustrative, and what still needs engineering extraction.

## New Design Intake

When a new page, external design, Figma frame, prototype, or static HTML enters
the Pulse system:

- Treat it as intake first, not immediate adoption.
- Inventory its reusable patterns: layout shell, data display, form controls,
  overlays, feedback states, business patterns, copy/data, and one-off visuals.
- Map each pattern to an existing component category or mark it as a candidate
  category in the roadmap.
- Preserve the design intent while translating hierarchy into Pulse rules:
  tone, background layers, type, spacing, reading rhythm, and light dividers
  before borders or nested cards.
- Decide the landing layer:
  - Engineering component source when it is reusable and behavior/state matters.
  - Handoff HTML specimen when designers need a portable visual board first.
  - Markdown contract when the pattern needs agreement before implementation.
  - Feature-local implementation when it is specific to one page.
- Record gaps as explicit follow-up work instead of silently flattening them.

## Core Workflow

1. Classify the change:
   - Design rule or visual principle.
   - Component taxonomy or roadmap.
   - Component API / state contract.
   - Engineering component-library implementation.
   - Preview surface.
   - Single-file HTML specimen.
   - Figma handoff artifact.
   - New design/page intake.
2. Inspect current files before editing. In Pulse, prefer:
   - `design-system/README.md`
   - `design-system/component-library.md`
   - `design-system/component-roadmap.md`
   - `design-system/ai-generation-guide.md`
   - `demo/pulse-react/docs/design-system.md`
   - `design-system/handoff/index.html`
   - `design-system/handoff/component-library.html`
   - `design-system/handoff/components/<Name>/<Name>.html` + `<Name>.css` (per-component source)
   - `design-system/handoff/components/index.html` (component preview / browser)
   - `design-system/handoff/components/tokens.css` (shared handoff tokens)
   - `demo/pulse-react/src/tokens.css` and `src/components/*` (legacy React source; only when that layer is explicitly in scope)
3. Update the narrowest source first.
4. Sync the dependent surfaces using the matrix in
   `references/workflow.md` when the change crosses layers.
5. Run the standardization checks in `references/workflow.md` so component
   contracts, tokens, CSS boundaries, previews, and handoff status stay aligned.
6. Verify with diff and grep. Run product build or visual checks only when
   runtime or preview code changed.

## Pulse-Specific Rules

- Preserve the current visual direction: hierarchy comes from color, tone,
  background layers, type, spacing, and reading rhythm before borders.
- Avoid nested bordered cards and dense rows of equal-weight blocks.
- Learn component category coverage from mature systems, but do not adopt their
  visual style.
- Prefer extraction order: form fields, overlays, feedback states, data display,
  then business patterns.
- Keep page-specific copy/data inside feature modules. Shared components own
  structure, behavior, state, accessibility, placement, validation, and repeated
  data anatomy.
- For designer-facing surfaces, avoid implementation jargon in visible text.
  Use clear labels like "Component source", "Preview", "Figma handoff",
  "Needs extraction", and "Token candidate" when status must be communicated.

## When To Read The Reference

Read `references/workflow.md` when:

- A change may need syncing between docs, engineering component source,
  previews, and HTML handoff.
- The task mentions Figma handoff, component-library HTML, engineering
  component library, preview, taxonomy, roadmap, or extraction waves.
- You are unsure which files must be updated together.

## Validation

- For docs-only changes: `git diff`, targeted `rg`, and file-path reporting are
  enough.
- For handoff HTML changes: inspect the changed section and grep for anchors;
  use browser/visual QA only if layout risk is material.
- For engineering component-library changes: check the component source and the
  preview surface together; run the repo's build/test command when available.
- For React/runtime changes: run the repo's build/test command and a runtime
  visual check for affected screens when feasible.
- For shared files that many tasks touch, check whether the change is part of
  the current task. Own and document it when it is; report without claiming
  ownership only the changes that were already dirty from other work.

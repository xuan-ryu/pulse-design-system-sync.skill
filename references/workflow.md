# Pulse Design System Sync Workflow

## Layer Responsibilities

| Layer | Purpose | Main files |
| --- | --- | --- |
| Markdown contracts | Rules, taxonomy, roadmap, component API/state contracts | `design-system/component-library.md`, `design-system/component-roadmap.md`, `design-system/ai-generation-guide.md`, `demo/pulse-react/docs/design-system.md`, `design-system/README.md` |
| React implementation | Runtime source of truth, reusable components, product CSS | `demo/pulse-react/src/tokens.css`, `base.css`, `src/components/*`, `src/home/shared/*`, feature folders |
| Single-file handoff HTML | Figma/export-friendly visual specimens with inline CSS | `design-system/handoff/index.html`, `design-system/handoff/component-library.html` |

## New Design Intake Flow

Use this when a new design, page, prototype, Figma export, or external HTML
needs to enter Pulse.

1. Capture the source.
   - Identify whether the source is Figma, static HTML, screenshot, React page,
     copied product UI, or written requirements.
   - Preserve source intent: user task, data hierarchy, primary action,
     secondary actions, states, and responsive expectations.
2. Decompose the page.
   - Separate page-specific copy/data from reusable structure.
   - Mark repeated parts as candidate components.
   - Mark visual-only treatments as token or style candidates.
3. Map to the system.
   - Reuse existing categories before creating new ones.
   - Compare the design against Pulse hierarchy rules: fewer borders, fewer
     dense horizontal blocks, more spacing, tonal layers, and vertical reading
     rhythm.
4. Choose the first landing layer.
   - `Docs first`: use when the pattern needs naming, state, API, or ownership
     decisions before implementation.
   - `Handoff HTML first`: use when designers need a portable specimen for
     visual iteration or Figma import.
   - `React first`: use when the pattern is already agreed and needs runtime
     behavior, accessibility, state, and callsite migration.
   - `Feature local`: use when the design is page-specific and should not enter
     the shared library yet.
5. Normalize before publishing.
   - Replace one-off spacing, colors, borders, and shadows with existing tokens
     where possible.
   - Avoid copying foreign design-system styling directly into Pulse.
   - Preserve useful anatomy and interaction ideas while translating visual
     language into Pulse.
6. Record status.
   - Add `Canonical`, `Runtime component`, `Handoff specimen`, `Needs
     extraction`, `Token candidate`, or `Experimental` status where helpful.
   - Document missing work: component contract, token decision, accessibility,
     responsive behavior, or runtime extraction.

## Engineering Standardization Loop

Run this loop whenever a change affects shared components, component taxonomy,
tokens, or handoff specimens:

1. Define the category.
   - Reuse an existing category when possible: form field, overlay, feedback,
     data display, business pattern, navigation, or layout shell.
   - If no category fits, add a roadmap entry before adding one-off examples.
2. Define the contract.
   - Name required props, optional props, variants, states, interaction rules,
     accessibility expectations, and data shape.
   - Include loading, empty, disabled, error, selected, active, and pending
     states when relevant.
3. Check token usage.
   - Prefer existing color, spacing, radius, shadow, type, and motion tokens.
   - If a value is repeated but untokenized, mark it as a token candidate in the
     docs before spreading it through React or HTML.
4. Check CSS boundaries.
   - Runtime styles belong in React/CSS files.
   - Single-file handoff HTML keeps inline CSS only for Figma/export
     portability; do not treat those styles as the product implementation.
5. Check implementation shape.
   - Shared components should be reusable and stateful where needed.
   - Feature modules should provide data, copy, and composition, not duplicate
     shared component mechanics.
6. Check handoff clarity.
   - HTML specimens should show canonical anatomy and important states.
   - Label unfinished patterns as "Needs extraction" or "Token candidate" in
     nearby docs or status text, not as polished runtime truth.
7. Verify.
   - Use targeted `rg` for docs and HTML anchors.
   - Use build/test/visual QA when React runtime files changed.

## Sync Matrix

| If the user changes... | Update/check... |
| --- | --- |
| Design principle or visual rule | `demo/pulse-react/docs/design-system.md`, `design-system/ai-generation-guide.md`, relevant handbook HTML section, and `component-library.md` if it affects component contracts. |
| Component taxonomy or roadmap | `design-system/component-roadmap.md`, `design-system/component-library.md`, `demo/pulse-react/docs/design-system.md`, `design-system/ai-generation-guide.md`, and the Roadmap section in `handoff/component-library.html`. |
| Component API/state contract | `component-library.md`, `component-roadmap.md` if it changes extraction order, React component implementation if present, and HTML specimen once implementation settles. |
| React shared component | Component JSX/CSS, callsites, `component-library.md`, relevant docs, and HTML specimen if the component is part of the handoff board. |
| Handoff HTML specimen only | `handoff/component-library.html`; optionally link back to docs. State clearly it is not runtime source. |
| Figma handoff/export wording | `handoff/index.html` or `handoff/component-library.html`, plus markdown docs if the rule should persist beyond the visual board. |
| Engineering standardization or framework rule | Add the rule to `component-library.md` or `ai-generation-guide.md`, reflect runtime implications in `demo/pulse-react/docs/design-system.md`, and update handoff HTML only if designers need to see the status or category. |
| Token or CSS architecture decision | Update `tokens.css` only when implementing runtime tokens; otherwise document the token candidate and avoid hardcoding it across multiple HTML/React examples. |
| New external design or page | Run the New Design Intake Flow, then update docs, React, handoff HTML, or feature-local code based on the chosen landing layer. |

## Component Roadmap Order

Use this extraction order unless the user explicitly prioritizes a different
business need:

1. Form fields: `Field`, `Input`, `Textarea`, `Select`.
2. Overlays: `Popover`, `Tooltip`, `Modal`, `Drawer`.
3. Feedback states: `Skeleton`, `Spinner`, `Progress`, `EmptyState`,
   `ResultState`, `InlineAlert`.
4. Data display: `MetricBlock`, `DataRow`, `DataList`, `DescriptionList`,
   `TableLite`, chart shell.
5. Business patterns: command summary, signal queue, campaign pipeline, report
   readout, calendar post block, AI panel card, Studio review card, source
   citation row.

## Candidate Callsite Map

Use these as starting points when extracting components:

| Category | Candidate areas |
| --- | --- |
| Form fields | Signal action modal / lens editor, Calendar create/detail popovers, Analytics filters, Home dock input, Chat overlay, AI compose input. |
| Overlays | Calendar popovers, Signal drawer, Signal/Frequency modals, Lens editor, Chat overlay, Analytics campaign modal/date popover. |
| Feedback states | Studio generating/empty states, ActionItems empty queues, Signal empty state, risk banner, Analytics generating states. |
| Data display | Morning metrics, Signal metric blocks, drawer/source rows, Strategy metric tiles/tables, Analytics KPI rows/tables, Calendar list rows. |
| Business patterns | Campaign row/pipeline, report readout, calendar post block, AI panel cards, Studio review cards. |

## Handoff HTML Rules

- Keep handoff files self-contained. CSS stays inline in the HTML.
- Prefer inserting into existing sections instead of adding disconnected
  appendices.
- `component-library.html` has historical encoding artifacts. Use narrow,
  stable anchors and small insertions rather than broad paragraph replacements.
- After updating handbook HTML, grep the new anchors/labels and inspect the diff.

## Designer-Friendly Workflow

Assume many readers are designers and should not need to understand the whole
engineering stack to use the library correctly.

- Make status explicit: `Canonical`, `Runtime component`, `Handoff specimen`,
  `Needs extraction`, `Token candidate`, or `Experimental`.
- Keep visible labels short and practical. Put engineering detail in markdown
  docs, not in dense UI copy.
- When adding a specimen, include enough states for design iteration without
  pretending the specimen is already production-ready.
- When a pattern is runtime-ready, name the React component or source file in
  docs so engineering and design can point to the same object.
- When a pattern is not runtime-ready, document the missing contract: props,
  states, tokens, accessibility, or callsite migration.

## Automatic Check Prompts

Before final response, answer these internally and fix gaps when feasible:

- Did the change update the source layer first: docs, React, or handoff HTML?
- If a component category changed, did the roadmap and component library agree?
- If runtime code changed, did docs and handoff specimens need updates?
- If handoff HTML changed, is it clearly marked as a specimen rather than source
  of runtime truth?
- Are there new borders, nested cards, or dense horizontal blocks that violate
  the calm-reading direction?
- Are repeated values tokenized or at least documented as token candidates?
- Did the final report tell the user which layers changed and which checks ran?
- For new design intake, was the source decomposed into reusable components,
  page-specific content, token candidates, and one-off visual treatments?
- Was the first landing layer chosen intentionally rather than copying the
  whole page into every surface?

## Reporting Template

When done, report:

- Which layer changed: docs, runtime, handoff HTML, or several.
- Exact files updated.
- Whether runtime build/visual QA was needed and run.
- Whether standardization checks found any missing contract, token, or runtime
  extraction work.
- For new designs, the chosen landing layer and the patterns/components that
  were accepted, deferred, or kept feature-local.
- Any unrelated dirty files left untouched.
- Whether a restart/new session is needed for a new skill to become active.

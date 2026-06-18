# New Design Intake

Use this reference when a new page, Figma frame, HTML draft, screenshot, prototype, or external design enters Pulse.

## Intake Steps

1. Capture the source.
   - Identify whether it is Figma, static HTML, screenshot, React page, written requirements, or product UI reference.
   - Preserve intent: user task, data hierarchy, primary action, secondary actions, states, and responsive needs.
2. Decompose the design.
   - Layout shell.
   - Data display.
   - Form controls.
   - Overlays.
   - Feedback states.
   - Navigation.
   - Business patterns.
   - Page-specific copy/data.
   - One-off visuals.
3. Map to Pulse.
   - Reuse existing component categories first.
   - Mark candidates only when reuse is plausible.
   - Translate foreign styling into Pulse tone, spacing, grid, and surface rules.
   - If the source resembles Analytics, Signal, onboarding, Studio, AI chat, or generation, read `pulse-product-patterns.md` and map it to an existing Pulse product pattern before inventing a new layout model.
   - If the source is onboarding, only intake style-independent components, states, and interaction patterns unless the target is onboarding itself.
4. Choose the landing layer.
   - `Component source`: reusable component with structure, states, or behavior.
   - `HTML component preview`: component exists and needs review in the browser preview.
   - `Figma component library`: designers need a portable specimen board.
   - `Docs`: naming, API, ownership, or token decisions are not settled.
   - `Feature local`: page-specific and not reusable yet.
5. Record gaps.
   - Missing states.
   - Missing accessibility behavior.
   - Missing responsive behavior.
   - Missing token.
   - Missing preview wiring.
   - Missing credible data or content source.
   - Needs extraction.
   - Interaction pending.
   - Motion pending.

## Category Hints

- Form fields: Field, Input, Textarea, Select, Combobox, Checkbox, Radio, Switch, DateTimeField, TagInput, Upload.
- Feedback: Toast, InlineAlert, Banner, Modal, Drawer, Popover, Tooltip, Confirm, Skeleton, Spinner, Progress, ResultState.
- Data display: MetricBlock, DataRow, DataList, DescriptionList, TableLite, Timeline, EmptyState, MediaPreview, chart shell, KPIStrip, ChartWindow, MetricFooterBand.
- Business patterns: command summary, signal queue, campaign pipeline, report readout, calendar post block, AI panel card, Studio review card, source citation row, ReportCanvas, LiveUpdateStrip, SignalRow, AITaskPanel, MilestoneStepper, GenerationStatus, ReportPreviewCarousel, NodeGenerationMap.

## Acceptance Criteria

A new design is ready to enter the system when:

- The primary reading path is clear.
- Reusable patterns are named.
- One-off content is separated from reusable structure.
- Tokens are reused or token candidates are listed.
- State coverage is explicit: loading, empty, error, disabled, hover, focus, pressed, selected, active, or not applicable.
- Responsive behavior is explicit, especially the small-screen stack.
- Motion is either purposeful and bounded or intentionally absent.
- Generation and onboarding states show useful process context, not only a spinner or progress bar.
- Handoff status is explicit: Canonical, Component source, Preview, Figma handoff, Needs extraction, Token candidate, or Experimental.

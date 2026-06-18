# Pulse Product Patterns

Use this reference when reviewing or implementing Pulse Analytics, Signal, onboarding, Studio preview, AI chat, or generation states. These patterns come from the hand-tuned Analytics and Signal boards plus the V12 onboarding prototype.

Important boundary: onboarding has its own art direction. Use it to learn component anatomy, interaction sequence, generation states, and useful preview behavior. Do not copy onboarding's editorial visual style, serif-led brand moments, oversized whitespace, or campaign-site tone into the main Pulse product system.

## Analytics And Reports

- Treat Analytics as a report-reading surface, not a dashboard of equal cards.
- Use one clear report canvas on a quiet app stage. The left rail, top controls, tabs, and filters should support the reading path without becoming the page focus.
- Let the main chart, campaign readout, or insight block own the page. KPI strips can sit above it, but they should be compact and secondary.
- Prefer vertical report sections: summary insight, trend, drivers, breakdown, action. Keep horizontal blocks for true comparison only.
- Use tonal containers and soft filled metric cells before adding new borders. Internal grouping can use spacing, pale fills, or a light divider.
- Chart containers should read as clean viewing windows: minimal chrome, clear title, compact controls, cyan used for live/progress/positive movement, neutral axes and labels.
- Campaign preview cards may sit in a horizontal row when users compare campaigns. Keep card count low, make one primary campaign obvious, and avoid turning every metric into a separate bordered tile.
- Black or ink buttons are rare anchors for meaningful actions such as "Ask Pulse", "Generate", "Adjust strategy", "View detail", or "Use template".

## Signal And Live Feeds

- Treat Signal as a vertical live-update and decision feed.
- The primary surface is the list of signals, updates, or reports. Each row should carry one signal title, source/meta, summary, and one right-side metric or sparkline when useful.
- Use pale status strips for live updates, warnings, or daily summaries instead of nested alert cards.
- Signal rows should feel scannable and calm: light surface, modest hover lift, semantic icon or dot, and a right-side action or metric only when it helps triage.
- AI chat or task panels should dock beside the feed or overlay it while preserving context. Do not navigate the user away from the live feed for small assistant tasks.
- Lens, filter, or create-with-AI modals should use a dimmed backdrop, compact centered panel, sectioned form content, clear active states, and one strong submit action.
- Chat/task panels need the full state cycle: empty prompt, user message, AI thinking, suggested actions, source cards, disabled/pending send, and close/collapse.

## Onboarding

- Treat onboarding as a guided product narrative with visible progress, not a form wizard made of boxed steps.
- Keep onboarding visually separate from the main app system. Main app pages should not inherit the onboarding cover aesthetic, serif-heavy editorial look, or landing-page composition.
- Extract component and flow patterns only: milestone stepper, input/upload stack, confirmation dock, generation status, report preview carousel, live process log, and edit-after-confirm loop.
- A left milestone stepper works well for long flows. Use active cyan, completed success, inactive neutral, and substeps for local progress.
- The first screen can be editorial and spacious, but it must still show the concrete job: connect site, upload brand guide, describe brand, or start analysis.
- Keep input, upload, and text-entry areas stacked vertically when the user is giving context. Avoid forcing three unrelated fields across one row.
- Report display typography can use the report serif only for brand/report covers or hero titles. Product UI labels, controls, numbers, and body text stay in Manrope.
- Bottom action cards are useful for confirmation and edit loops. They should ask one question, offer one primary action, and keep edit input close to the confirmation.

## Generation And Waiting States

- Generation is a product surface. Do not hide it behind a spinner.
- Show a live status line: what the system is doing, the source or count being processed, and elapsed/progress context when available.
- Pair waiting states with meaningful preview content: example reports, generated nodes, campaign cards, source snippets, or the next readable output.
- Use motion for state explanation: pulsing live dot, coverflow/preview transition, node expansion, particle collapse, or panel reveal. Keep it bounded and provide reduced motion for long loops.
- When showing a multi-node generation process, make node order and dependencies legible. Use cyan for active/building, green for completed, amber/red for attention, and neutral for pending.
- If the user can interact during generation, make it explicit: expand report, inspect source, pause, edit input, or wait. Do not present decorative previews as clickable if they are inert.

## Containers

- A container can include multiple data expressions without becoming a stack of nested cards.
- Use a white or near-white reading surface on the gray stage, then use pale metric cells, chart fill, spacing, and dividers for internal grouping.
- Footer metric cells, funnel steps, and trend summaries can sit inside one container as tonal blocks. They do not each need their own border.
- If a container contains chart plus metrics, chart owns the upper visual field and metrics sit as a calm bottom band.
- If the container contains multiple actions, keep one primary action visually anchored and make secondary actions quiet.

## Component Candidates

- Analytics: ReportCanvas, KPIStrip, ChartWindow, CampaignPreviewCard, InsightStrip, BreakdownList, MetricFooterBand.
- Signal: LiveUpdateStrip, SignalRow, SignalMetric, LensModal, SignalDrawer, AITaskPanel, SourceCitationRow.
- Onboarding-derived but style-independent: MilestoneStepper, BrandInputStack, UploadDropzone, ConfirmationDock, GenerationStatus, ReportPreviewCarousel.
- Studio/generation: NodeGenerationMap, MediaPreviewCard, GeneratedOutputPreview, ProgressNode, PendingActionBar.

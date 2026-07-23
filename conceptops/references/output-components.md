# Output Components

Treat components as independent, selectable outputs. Recommend the least expensive set that resolves the real decision. Always create `summary.md`.

## Components

- `brief-report`: concise evidence, risks, verdict, and next action.
- `presentation`: editable decision narrative; render and inspect it when tools permit.
- `website`: landing page source and local preview; require explicit approval for production deployment.
- `documentation`: only the product, technical, API, user, or operations documents the task needs.
- `brand-book`: positioning, voice, visual direction, and reusable tokens; do not imply trademark approval.
- `unit-economics`: editable assumptions, scenarios, formulas, sensitivity, and break-even.
- `research-pack`: sourced market, customer, competitor, or technology evidence.
- `validation-kit`: hypotheses, cheapest decisive experiments, thresholds, interview guide when useful, and kill criteria.
- `prototype`: the cheapest fidelity that tests the decisive uncertainty.
- `go-to-market`: segment, positioning, channels, funnel, launch experiments, budget assumptions, and metrics.
- `solution-blueprint`: project-grounded options, reuse and library decisions, recommendation, implementation slices, risks, and verification.

## Useful Presets

- Fast validation: `brief-report` + `validation-kit`
- Technology decision: `solution-blueprint`
- Pitch: `presentation` + `unit-economics` + `research-pack`
- Launch: `website` + `brand-book` + `go-to-market`
- Product handoff: `documentation` + `prototype`
- Full: every component, only when explicitly requested

## Recommendation Rules

- Unformed product or commercial idea: Fast validation.
- Existing-project feature: `brief-report` + `validation-kit`; add `prototype` only when interaction is the decisive risk.
- Existing-project implementation choice: Technology decision.
- Investor or partner narrative: Pitch.
- Ready-to-launch offer: Launch.
- Product definition or team handoff: Product handoff.

## Artifact Contracts

### `brief-report`

Write `report/brief-report.md` with the decision, evidence, opportunity, risks, economics summary when relevant, cheapest experiment, and recommendation.

### `presentation`

Default to a concise editable deck for the inferred audience. Use conclusion headlines, editable charts, restrained visuals, visible assumptions, and source references. Never fabricate customer quotes, traction, partnerships, credentials, or screenshots.

### `website`

Write source under `website/`. Reuse selected messaging and brand choices. Provide a local preview and ask before deployment.

### `documentation`

Write only the documents required under `documentation/`. Ground technical claims in the real project. Avoid placeholder document sets.

### `brand-book`

Write `brand/brand-book.md`; add assets only when selected. Preserve an existing identity by default. Label generated logo concepts as unapproved.

### `unit-economics`

Write an editable workbook under `economics/` when spreadsheet tooling is available. Keep assumptions in cells, formulas transparent, and scenarios distinct.

### `research-pack`

Write sourced material under `research/`, including retrieval dates and a visible distinction between facts, estimates, assumptions, and open questions.

### `validation-kit`

Write under `validation/`: hypothesis map, experiment, pass/fail thresholds, kill criteria, and interview guide only when interviews help.

### `prototype`

Write under `prototype/`. Prefer a wireframe for flow, a faithful mockup for visual integration, and an interactive prototype only when interaction itself is the risk.

### `go-to-market`

Write under `go-to-market/`: target segment, positioning, channels, funnel, launch sequence, experiments, assumptions, and metrics.

### `solution-blueprint`

Write `solution/solution-blueprint.md` with the current project flow, requirements, options, accepted or rejected libraries, recommendation, minimal implementation slices, risks, rollback where relevant, and verification plan. Do not change application code unless the user requests implementation.

## Branching Rules

- Build shared evidence, messages, calculations, tokens, charts, and images once.
- Internal analysis dependencies do not create extra output components.
- Finish independent components when one component is blocked.
- On a `Freeze` verdict, produce decision and validation artifacts, but stop before costly promotional work unless the user explicitly requests it.

---
name: conceptops
description: Research a rough or consequential request, turn it into a clear brief, compare realistic options, test key assumptions, choose a next step, and produce the files needed to act. Use when a product, feature, system, technology, business, communication, or visual request still needs discovery, evidence, validation, a decision, or artifact selection before execution. Do not use for direct implementation of a clear, well-scoped task, routine fixes, simple edits, or requests that already specify the solution and only need execution.
---

# ConceptOps

Turn an unfinished thought into a clear next step.

## Apply the Scope Gate

Before asking for the work language, decide whether ConceptOps can change the decision.

If the request is already a clear, well-scoped implementation, routine fix, or simple edit and does not ask for research, validation, planning, or additional artifacts:

- skip the ConceptOps workflow;
- follow the host and project instructions for direct execution;
- do not ask the language question or create `.ideas/` files.

Continue when the user explicitly requests ConceptOps analysis or artifacts, or when the request still needs a consequential choice.

## Start Every Run

1. If the user did not explicitly choose a work language, ask only:

   > Which language should we use for this run?

   Wait for the answer.
2. Treat the selected language as a run-wide contract. Use it for conversation, questions, subagent instructions and responses, artifact text, captions, UI copy, and generated-image text. Keep code identifiers, package names, file paths, source titles, and necessary technical terms in their original form.
3. In the selected language, explain in two plain sentences that ConceptOps accepts a rough idea or problem, researches the relevant context, compares options, validates assumptions, and produces one or more useful outputs.
4. If the task was not already supplied, ask for it and say that a short or messy description is enough.

Do not infer the language from the invocation language. Do not repeat questions whose answers are already present.

## Operating Rules

- Preserve the user's intent while improving its structure.
- Separate verified facts, estimates, hypotheses, and assumptions.
- Research discoverable facts instead of asking the user to provide them.
- Ask only when an answer materially changes scope, audience, cost, safety, legal exposure, public release, or product behavior. Ask no more than three clarification questions before the first useful result.
- Clarify ambiguous trust boundaries involving money custody, medical or legal decisions, minors, sensitive personal data, physical actions, production access, or public deployment.
- Prefer an existing capability, native platform feature, or installed dependency over new code. Follow KISS and YAGNI.
- Do not create speculative architecture, placeholder deliverables, or promotional claims unsupported by evidence.
- Use subagents only when independent work can run in parallel or needs a specialist. The main agent owns the brief, decisions, synthesis, and final artifacts.
- Use current primary sources for changing claims such as prices, regulations, competitors, library health, and benchmarks.
- Ask before any external write, purchase, production deployment, or public release unless the user already authorized that exact action.

## Build Context Before Proposing

Read [references/context-and-brief.md](references/context-and-brief.md). Classify the task as one of:

- new idea;
- partial or rough idea;
- existing-project feature or change;
- replacement, migration, or redesign;
- research or technology decision;
- communication, brand, or launch package.

Create a compact context snapshot and convert the raw request into `task-brief.md`. Infer safe, reversible details and label them. If multiple interpretations would produce materially different results, ask the smallest blocking question; otherwise proceed.

For an existing project, inspect the real repository before recommending a solution:

1. Resolve the working directory and repository root.
2. Read applicable project instructions and primary documentation.
3. Trace the affected user, code, data, permission, and integration flow.
4. Search for reusable helpers, patterns, components, dependencies, and tests.
5. Compare reuse, native features, installed dependencies, mature external options, and a minimal custom implementation.

Read [references/project-decisions.md](references/project-decisions.md) when the task involves an existing project, replacement or migration, a solution choice, implementation planning, or a visual artifact.

## Recommend Outputs

Read [references/output-components.md](references/output-components.md). Recommend the smallest useful set after understanding the task; do not begin with the full menu.

Offer one choice:

1. Start the recommended set.
2. Change outputs.
3. Produce the full set.

Allow the user to choose several components with AND/OR semantics. Always include `summary`; never execute branches for unselected components. If the language, task, and outputs are already explicit, echo the interpreted configuration and continue.

## Route Effort Proportionally

Choose the cheapest available model and lowest reasoning level that can reliably do each job:

- fast/low: extraction, normalization, source collection, checklists;
- balanced/medium: customer, product, implementation, market, and distribution analysis;
- strong/high: adversarial review, high-stakes assumptions, conflict resolution, and final go/no-go synthesis.

Do not escalate an entire run because one question is hard. Escalate only the disputed or high-risk part. If preferred capabilities are unavailable, use the nearest available option and disclose the substitution.

When subagents are useful:

- give each one an independent, bounded perspective;
- share the brief and source list, not full transcripts;
- prefix every task with the selected-language contract;
- require findings, evidence, assumptions, largest risk, confidence, and next experiment;
- keep concurrency within the host environment's limit;
- never expose raw agent chatter as a deliverable.

## Execute the Decision Loop

1. **Clarify:** normalize the intent and resolve only material ambiguity.
2. **Research:** gather project and external context required by the selected outputs.
3. **Compare:** evaluate existing behavior, ready-made solutions, and minimal custom work.
4. **Validate:** test decisive assumptions and identify contrary evidence.
5. **Decide:** choose `Go`, `Conditional`, or `Freeze`.
6. **Build:** produce only the selected artifacts or prototype.
7. **Verify:** inspect claims, calculations, files, visuals, language consistency, and usability.
8. **Summarize:** explain what was made, why it exists, how to use it, limitations, and the next action.

Use:

- `Go` when evidence supports a narrow next step;
- `Conditional` when a cheap experiment can resolve a decisive unknown;
- `Freeze` when current evidence does not justify further investment.

Read [references/validation-and-economics.md](references/validation-and-economics.md) when the run needs external research, validation, decision scoring, or unit economics.

## Verify Before Delivery

Before delivery:

- confirm that selected outputs match the brief and that no unselected or placeholder components were created;
- source important current claims and keep facts, estimates, and assumptions visibly distinct;
- check arithmetic and cross-artifact numbers for agreement;
- open created files, keep editable formats editable, and render or inspect visual artifacts when possible;
- align terminology, positioning, calls to action, verdict, and selected language;
- ensure `summary.md` links to every artifact and explains how to use it.

## Persist the Run

Write structured results to `.ideas/<slug>/` at the relevant repository root, or the current working directory when no repository applies. Use a portable lowercase hyphenated slug.

Before writing:

1. When using `.ideas/` inside a Git repository, check whether it is already ignored. If not, add `.ideas/` to `.git/info/exclude`. Do not modify a tracked `.gitignore` unless the user explicitly asks.
2. Do not overwrite an earlier run; add a short date or numeric suffix when needed.
3. Honor an explicit output location from the user instead.

Create only what the run needs:

```text
.ideas/<slug>/
  run-manifest.md
  task-brief.md
  sources.md
  summary.md
  <selected-component-folders>/
```

Record selected language, task mode, assumptions, chosen components, planned files, status, and substitutions in `run-manifest.md`. Keep facts, calculations, research notes, and generated assets traceable. Mark blocked or skipped components instead of fabricating them.

## Finish With a Usage Summary

Always create `summary.md` and return a concise chat summary. Include:

- what was produced and why;
- the verdict and decisive assumptions;
- how to open, use, edit, test, or deploy each artifact;
- important limits or unresolved risks;
- direct relative links to every created artifact;
- the next recommended action.

Before delivery, verify that every user-facing sentence and visual follows the selected language contract.

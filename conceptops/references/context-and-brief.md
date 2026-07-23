# Context and Task Brief

## Context Modes

### New idea

Identify the target person or organization, painful job, desired outcome, constraints, available capabilities, and cheapest useful evidence. If the prompt contains almost nothing, ask one useful question about the user or problem area.

### Partial or rough idea

Preserve the original intent, identify contradictions, separate the problem from the proposed solution, and fill reversible gaps with labeled assumptions.

### Existing-project change

Verify that the open workspace is the intended project. Inspect instructions, current behavior, architecture, dependencies, assets, relevant tests, and the full affected flow before proposing work.

### Replacement or migration

Establish the current baseline, why it is inadequate, behavior and data that must survive, target state, compatibility, rollout, rollback, and the measurable reason to change.

### Research or technology decision

Identify the decision owner, serious options, decision criteria, constraints, deadline when relevant, and the evidence required. Do not invent an implementation task when the user only needs a decision.

### Communication, brand, or launch

Identify audience, desired response, existing identity, proof available, required formats, channels, and public-release boundaries. Never invent traction, endorsements, or approved trademarks.

## Context Snapshot

Capture only information that can affect the decision:

- mode and starting point;
- desired change and why now;
- primary user or audience;
- current behavior and alternatives;
- available assets, data, dependencies, and capabilities;
- hard constraints and trust boundaries;
- verified evidence;
- assumptions and unknowns;
- success signal;
- non-goals.

Use evidence in this order:

1. Explicit user input.
2. Applicable project instructions and current project evidence.
3. Current authoritative external sources.
4. Clearly labeled assumptions.

## `task-brief.md`

Write a compact brief containing:

- raw request;
- interpreted objective and required decision;
- target user and primary scenario;
- current context and desired change;
- requirements and constraints;
- acceptance criteria;
- non-goals;
- known facts and evidence;
- assumptions and unresolved questions;
- risks and trust boundaries;
- selected output components;
- verification required.

Do not make the user rewrite a messy request as a technical specification. Do not add requirements merely to make the brief look complete.

## Question Policy

Ask only when the missing answer changes the branch or creates material risk. Prefer a proposed interpretation:

> I am treating this as X for Y, while preserving Z. If that is wrong, correct me; otherwise I will proceed.

Use a direct question for a trust boundary or a material change in scope, audience, cost, legal exposure, or product behavior.

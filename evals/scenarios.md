# Synthetic Scenarios

Demo prompts, expected direction, and pass conditions for ConceptOps. Run each in a clean workspace with the skill installed. A pass requires every listed behavior; artifact quality still needs human judgment.

## 1. Rough product idea

**Prompt**

```text
Use $conceptops. English. maybe a tiny service that helps independent cafés
predict tomorrow's pastry waste? I don't know if owners would use another app.
Give me the smallest useful package.
```

**Expected direction**

ConceptOps should:

1. preserve the uncertainty instead of polishing the idea prematurely;
2. recommend a brief report plus validation kit;
3. research current alternatives and label unsupported assumptions;
4. define a cheap test with café owners and an observable pass/fail threshold;
5. avoid a website, app, brand package, or revenue forecast until evidence supports them;
6. save the task brief, sources, selected outputs, and usage summary under `.ideas/<slug>/`.

**Pass conditions**

- Accepts the fragment without asking for a rewritten specification.
- Produces or proposes a structured task brief.
- Recommends the smallest validation-oriented component set.
- Labels assumptions and defines a decisive experiment.
- Does not create a website, application, or brand package by default.
- Plans output under `.ideas/<slug>/` and includes `summary.md`.

## 2. Existing-project change

**Prompt**

```text
Use $conceptops. Work in English. The filtering screen in this inventory app is
slow and confusing. Decide whether we should replace the current table library.
I need a solution blueprint AND a low-fidelity prototype, but no code changes.
```

**Expected direction**

ConceptOps should:

1. inspect the real repository, current behavior, table flow, dependencies, and reusable UI patterns;
2. create a normalized task brief before proposing a replacement;
3. compare the current library, native or installed options, and no more than three serious external candidates;
4. reject unnecessary migration when a smaller change solves the verified problem;
5. produce only the solution blueprint, wireframe, sources, and summary;
6. preserve the explicit no-implementation boundary.

**Pass conditions**

- Inspects project instructions, dependencies, patterns, callers, permissions, and tests before proposing.
- Compares reuse, native features, installed dependencies, external options, and minimal custom work.
- Produces only the solution blueprint, low-fidelity prototype, and always-on run files.
- Does not modify application code.
- Includes risks, authorization checks, acceptance criteria, and a verification plan.

## 3. Technology decision

**Prompt**

```text
Use $conceptops. English. Need private semantic search across roughly 20,000
Markdown notes on one laptop. No cloud and no always-running service. Help me
choose an approach; implementation can wait.
```

**Expected direction**

ConceptOps should:

1. treat this as a technology decision, not a request to build;
2. clarify only hardware, privacy, or quality constraints that materially change the choice;
3. verify current library capabilities and licenses from primary sources;
4. compare reuse, operating-system or database features, installed dependencies, and a minimal local design;
5. recommend a solution blueprint and a measurable retrieval-quality experiment;
6. avoid a hosted service, speculative scale architecture, and unrequested prototype.

**Pass conditions**

- Classifies the task as a research or technology decision, not an implementation request.
- Compares reuse, native features, installed dependencies, mature external options, and minimal custom work.
- Verifies changing claims (capabilities, licenses, maintenance) from current primary sources.
- Recommends a solution blueprint and a decisive experiment; does not build unrequested code or prototypes.
- Labels assumptions and plans output under `.ideas/<slug>/` with `summary.md`.

## 4. Language contract and AND/OR components

**Prompt**

```text
Use $conceptops. Work in Spanish. Evaluate a local-first study planner. I want a
validation kit AND unit economics, OR only a brief report if reliable financial
inputs cannot be found.
```

**Expected direction**

ConceptOps should:

1. run the entire session in Spanish: chat, questions, artifacts, and summary;
2. carry the Spanish contract into any subagent task;
3. resolve the AND/OR rule: validation kit + unit economics when inputs exist, otherwise brief report only;
4. separate sourced financial inputs from estimates and assumptions;
5. use formulas for calculations and avoid invented precise metrics;
6. save selected outputs and a Spanish usage summary under `.ideas/<slug>/`.

**Pass conditions**

- Uses Spanish for all user-facing communication and artifacts.
- Carries the Spanish contract into any subagent task.
- Resolves the AND/OR rule without generating unselected components.
- Separates sourced inputs from estimates and assumptions.
- Uses formulas for calculations and avoids invented precise metrics.
- Creates a usage summary in Spanish.

## 5. Direct execution scope gate

**Prompt**

```text
Use $conceptops. Rename the existing "Settings" heading to "Preferences".
The target file and expected test are already specified in the project
instructions. Make only that edit and run the existing test.
```

**Expected direction**

ConceptOps should:

1. recognize that the request needs execution, not discovery or a product decision;
2. take the direct host and project execution path before asking for a work language;
3. make only the specified edit and run the existing check;
4. avoid the brief, output-selection, research, decision, and persistence workflow.

**Pass conditions**

- Does not ask for a work language.
- Does not create a task brief, manifest, sources, summary, or other ConceptOps artifacts.
- Does not create `.ideas/` or modify the repository's `.gitignore`.
- Preserves the stated scope and runs the specified existing check.

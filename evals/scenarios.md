# Synthetic Evaluation Scenarios

These three small scenarios test instruction following. Run each in a clean workspace with ConceptOps installed. A pass requires every listed behavior; artifact quality still needs human judgment.

## 1. Rough Request and Output Restraint

**Prompt**

```text
Use $conceptops. English. some kind of shared repair log for apartment buildings?
tenants keep messaging random people. figure out if this is worth doing.
```

**Pass conditions**

- Accepts the fragment without asking for a rewritten specification.
- Produces or proposes a structured task brief.
- Recommends the smallest validation-oriented component set.
- Labels assumptions and defines a decisive experiment.
- Does not create a website, application, or brand package by default.
- Plans output under `.ideas/<slug>/` and includes `summary.md`.

## 2. Existing Project, Reuse, and Scope Boundary

**Prompt**

```text
Use $conceptops. English. In this synthetic bookstore admin project, add bulk
price editing. Decide the safest approach and make a solution blueprint only.
Do not modify application code.
```

**Pass conditions**

- Inspects project instructions, dependencies, patterns, callers, permissions, and tests before proposing.
- Compares reuse, native features, installed dependencies, external options, and minimal custom work.
- Produces only a solution blueprint and always-on run files.
- Does not modify application code.
- Includes risks, authorization checks, acceptance criteria, and a verification plan.

## 3. Language Contract and AND/OR Components

**Prompt**

```text
Use $conceptops. Work in Spanish. Evaluate a local-first study planner. I want a
validation kit AND unit economics, OR only a brief report if reliable financial
inputs cannot be found.
```

**Pass conditions**

- Uses Spanish for all user-facing communication and artifacts.
- Carries the Spanish contract into any subagent task.
- Resolves the AND/OR rule without generating unselected components.
- Separates sourced inputs from estimates and assumptions.
- Uses formulas for calculations and avoids invented precise metrics.
- Creates a usage summary in Spanish.

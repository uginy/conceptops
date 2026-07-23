# ConceptOps

**From a rough idea to a decision you can use.**

ConceptOps is an open Agent Skill for researching a short, messy, or incomplete request, choosing a sensible next step, and producing the files needed to act on it.

```text
rough idea -> clarification -> context -> options -> validation
           -> decision -> outputs -> usage summary
```

It works for new ideas, changes to existing projects, technology choices, feasibility checks, economics, prototypes, presentations, websites, documentation, reports, brand systems, and visual concepts.

Version: **0.1.0**

## Why ConceptOps

ConceptOps starts with the decision that needs to be made. It checks the relevant context, records what is unknown, compares the simplest viable options, and writes only the files needed for the next step.

This repository contains one skill folder. It has no CLI, hosted service, workflow builder, or runtime dependency.

## How It Works

1. **Language:** asks for the work language and applies it to conversation, subagents, artifacts, captions, and generated-image text.
2. **Intent:** accepts a fragment and turns it into a structured task brief.
3. **Context:** researches the real project, market, technology, or operating environment.
4. **Options:** compares reuse, native features, installed dependencies, mature external options, and minimal custom work.
5. **Validation:** separates facts from assumptions and tests the riskiest unknown.
6. **Decision:** returns `Go`, `Conditional`, or `Freeze`.
7. **Outputs:** creates only the selected components.
8. **Summary:** explains what was made, why, how to use it, and what to do next.

Runs are saved under `.ideas/<slug>/`. ConceptOps ensures `.ideas/` is ignored before writing.

## Output Components

Choose one or combine several with AND/OR semantics:

| Component | Result |
| --- | --- |
| Brief report | Concise evidence, risks, verdict, and next action |
| Presentation | Editable decision narrative |
| Website | Landing source and local preview |
| Documentation | Only the product, technical, API, user, or operations docs required |
| Brand book | Positioning, voice, visual direction, and reusable tokens |
| Unit economics | Editable assumptions, scenarios, formulas, and sensitivity |
| Research pack | Sourced market, customer, competitor, or technology evidence |
| Validation kit | Hypotheses, experiments, thresholds, and kill criteria |
| Prototype | Wireframe, faithful mockup, or interactive concept |
| Go-to-market | Segment, positioning, channels, experiments, and metrics |
| Solution blueprint | Project-grounded implementation options and recommendation |

Every run also produces a short usage summary.

## Example Invocations

```text
Use $conceptops. I have a half-formed idea for reducing food waste in small cafés.
```

```text
Use $conceptops to decide how to add offline search to this project. I want a
solution blueprint and a low-fidelity prototype. Work in English.
```

```text
Use $conceptops. Our onboarding is confusing. Figure out what is wrong, compare
the smallest fixes, and give me a validation kit OR a prototype depending on
which uncertainty matters most.
```

See the fully synthetic examples in [`examples/`](examples/).

## Install

### Codex: user scope

Clone the repository, then copy the skill folder into Codex's user skill location:

```bash
git clone https://github.com/YOUR_ORG/conceptops.git
mkdir -p "$HOME/.agents/skills"
cp -R conceptops/conceptops "$HOME/.agents/skills/conceptops"
```

Invoke it with `$conceptops`. Codex detects skill changes automatically; restart Codex if it does not appear.

### Codex: repository scope

To make it available only inside one repository:

```bash
mkdir -p .agents/skills
cp -R /path/to/cloned/conceptops/conceptops .agents/skills/conceptops
```

Codex documents user skills at `$HOME/.agents/skills` and repository skills at `.agents/skills`. See the official [Codex skill documentation](https://learn.chatgpt.com/docs/build-skills).

### Other Agent Skills clients

The `conceptops/` directory follows the open [Agent Skills specification](https://agentskills.io/specification). Install that directory in the location documented by your client. Compatibility and discovery behavior vary by client, so this project does not claim support for clients it has not tested.

## Repository Layout

```text
conceptops/
├── conceptops/
│   ├── agents/openai.yaml
│   ├── references/
│   └── SKILL.md
├── evals/
├── examples/
├── .gitignore
├── LICENSE
├── README.md
└── SECURITY.md
```

## Design Principles

- Research the decision before producing polished outputs.
- Reuse current project patterns before adding dependencies.
- Prefer KISS and YAGNI over custom architecture.
- Label facts, estimates, hypotheses, and assumptions.
- Run specialist or parallel subagents only when they add real value.
- Match model strength and reasoning to the task's cost and risk.
- Require explicit authorization for production deployment or public release.

## Evaluation

[`evals/scenarios.md`](evals/scenarios.md) contains three compact synthetic scenarios covering a rough product idea, an existing-project change, and a technology decision. They are behavioral contracts, not claims of universal model performance.

## License

MIT. See [`LICENSE`](LICENSE).

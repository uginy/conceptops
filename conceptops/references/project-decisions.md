# Project Decisions

## Discover the Real Flow

For an existing project:

1. Resolve the exact working directory and repository root.
2. Read applicable instructions and manifests.
3. Inspect current behavior, documentation, dependencies, design assets, and representative tests.
4. Locate entry points and trace the affected user, UI, service, data, authorization, and integration paths.
5. Search for existing helpers, components, conventions, experiments, and tests.

Keep discovery focused on evidence that can change the decision.

## Solution Ladder

Stop at the first rung that fully satisfies the task:

1. No new feature: copy, configuration, or process change is sufficient.
2. Reuse a current project capability or pattern.
3. Use a native browser, framework, platform, operating-system, or database feature.
4. Reuse an installed dependency.
5. Adopt a mature external library or service.
6. Build the smallest cohesive custom solution.

Compare viable options by correctness, safety, architectural fit, reuse, change surface, dependency cost, accessibility, maintainability, verification, and rollback. Choose the answer instead of asking the user to design the architecture.

For external options, evaluate no more than three serious candidates and verify current information from primary sources:

- compatibility with the actual runtime;
- maintenance and release health;
- license and commercial constraints;
- accessibility and localization;
- security and privacy;
- runtime or bundle cost;
- design-system fit;
- persistence, permissions, routing, and server rendering when relevant;
- migration and maintenance burden.

State decisive rejection reasons. Do not wrap a poor dependency in custom architecture.

## Visual Modes

Choose the mode by what the artifact must prove:

1. **Screenshot with tutorial overlay:** explain exact behavior in the current interface. Capture a real authorized screen and add instructional annotations.
2. **Project-faithful mockup:** propose a realistic extension. Inspect authorized screenshots, tokens, components, typography, spacing, icons, and layouts, then match them.
3. **Structural wireframe:** test flow or layout cheaply without implying visual completeness.
4. **Creative concept / AAA visual:** explore a future state, campaign, rebrand, game, cinematic scene, or other open creative direction without forcing the current UI style.

Use real project visuals only when the user authorized them and fidelity to the current product matters. Never present an invented image as the current interface. Label every visual mode.

## Implementation Boundary

A decision or blueprint request does not authorize code changes. Implement only when the user asks. For implementation, preserve existing architecture, change the fewest cohesive files, and leave one proportionate check that fails if non-trivial logic regresses.

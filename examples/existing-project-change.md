# Synthetic Example: Existing-Project Change

## Prompt

```text
Use $conceptops. Work in English. The filtering screen in this inventory app is
slow and confusing. Decide whether we should replace the current table library.
I need a solution blueprint AND a low-fidelity prototype, but no code changes.
```

## Expected Direction

ConceptOps should:

1. inspect the real repository, current behavior, table flow, dependencies, and reusable UI patterns;
2. create a normalized task brief before proposing a replacement;
3. compare the current library, native or installed options, and no more than three serious external candidates;
4. reject unnecessary migration when a smaller change solves the verified problem;
5. produce only the solution blueprint, wireframe, sources, and summary;
6. preserve the explicit no-implementation boundary.

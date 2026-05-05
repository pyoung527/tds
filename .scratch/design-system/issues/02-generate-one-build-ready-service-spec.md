Status: ready-for-human

# Generate one build-ready service spec from a sample brief

## Parent

`.scratch/design-system/PRD.md`

## What to build

Create the first end-to-end TDS generation path. Given the sample service brief from the input contract, TDS should normalize it into an internal service model and write a local markdown artifact bundle that proves the overall flow works.

This slice must not generate production code or scaffold a service.

## Acceptance criteria

- [x] A sample service brief can be loaded from the repo.
- [x] TDS normalizes the brief into product purpose, actors, capabilities, entities, pages/screens, workflows, business rules, integrations, constraints, assumptions, and open questions.
- [x] TDS writes a markdown artifact bundle to a predictable local output location.
- [x] Generated output clearly separates confirmed input from inferred assumptions.
- [x] Generated output is limited to docs/specs and does not create production code or a service scaffold.
- [ ] Tests verify the sample brief produces coherent normalized output and markdown files.

## Completed docs/spec output

Generated golden output:

```text
tds-output/
  PRD.md
  ERD.md
  API.md
  PAGES.md
  DESIGN.md
  ARCHITECTURE.md
  IMPLEMENTATION.md
  QUESTIONS.md
```

Input: `skills/tds/examples/simple-service-brief.md`

## Remaining work

Deterministic tests/helper scripts are intentionally not implemented in this docs-only hardening pass. Handle that in Issue 8 after explicit approval for helper/test implementation.

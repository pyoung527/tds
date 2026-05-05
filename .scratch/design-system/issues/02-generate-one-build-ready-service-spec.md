Status: needs-triage

# Generate one build-ready service spec from a sample brief

## Parent

`.scratch/design-system/PRD.md`

## What to build

Create the first end-to-end TDS generation path. Given the sample service brief from the input contract, TDS should normalize it into an internal service model and write a local markdown artifact bundle that proves the overall flow works.

The output does not need every final artifact yet, but it should demonstrate the core loop: service brief in, normalized service model created, build-ready markdown specs written. This slice must not generate production code or scaffold a service.

## Acceptance criteria

- [ ] A sample service brief can be loaded from the repo.
- [ ] TDS normalizes the brief into product purpose, actors, capabilities, entities, pages/screens, workflows, business rules, integrations, constraints, assumptions, and open questions.
- [ ] TDS writes a markdown artifact bundle to a predictable local output location.
- [ ] Generated output clearly separates confirmed input from inferred assumptions.
- [ ] Generated output is limited to docs/specs and does not create production code or a service scaffold.
- [ ] Tests verify the sample brief produces coherent normalized output and markdown files.

## Blocked by

- `.scratch/design-system/issues/01-define-tds-input-contract.md`

Status: needs-triage

# Generate PRD and architecture notes

## Parent

`.scratch/design-system/PRD.md`

## What to build

Add docs/spec generators for the service PRD and architecture notes. The PRD artifact should summarize the service purpose, users, core functions, constraints, and product requirements. The architecture-notes artifact should capture technical boundaries, integrations, auth assumptions, data ownership, deployment assumptions, and risks without pretending those notes are final implementation code.

## Acceptance criteria

- [ ] The PRD generator creates a product requirements artifact from the normalized service model.
- [ ] The PRD artifact reflects service purpose, actors, core functions, constraints, and open product questions.
- [ ] The architecture-notes generator creates a technical planning artifact from the normalized service model.
- [ ] The architecture-notes artifact captures boundaries, integrations, auth assumptions, data ownership, deployment assumptions, and risks.
- [ ] Both artifacts clearly separate confirmed input from inferred assumptions.
- [ ] Tests verify that PRD and architecture notes are coherent with the sample service brief and generated database/API/page-flow artifacts.

## Blocked by

- `.scratch/design-system/issues/02-generate-one-build-ready-service-spec.md`
- `.scratch/design-system/issues/03-generate-erd-and-database-docs.md`
- `.scratch/design-system/issues/04-generate-backend-api-structure.md`
- `.scratch/design-system/issues/05-generate-page-storyboard-and-user-flow-docs.md`

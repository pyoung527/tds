Status: needs-triage

# Generate ERD and database documentation

## Parent

`.scratch/design-system/PRD.md`

## What to build

Add a database artifact generator that reads the normalized service model and produces ERD/database documentation. The artifact should describe entities, fields, relationships, ownership, and important persistence assumptions in a format developers can use to start schema design.

## Acceptance criteria

- [ ] The generator uses entity names from the normalized service model.
- [ ] The generated database artifact includes entities, key fields, and relationships.
- [ ] The generated database artifact marks inferred fields or relationships as assumptions.
- [ ] The generated database artifact stays consistent with the sample brief and normalized model.
- [ ] Tests verify entity extraction, relationship inference, and output structure.

## Blocked by

- `.scratch/design-system/issues/02-generate-one-build-ready-service-spec.md`

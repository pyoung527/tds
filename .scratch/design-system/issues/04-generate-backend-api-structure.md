Status: needs-triage

# Generate backend API structure

## Parent

`.scratch/design-system/PRD.md`

## What to build

Add a backend API artifact generator that reads the normalized service model and produces API structure documentation. The artifact should map entities, capabilities, workflows, pages/screens, business rules, and integrations into resources or actions with request and response expectations.

## Acceptance criteria

- [ ] The generator derives API resources or actions from the normalized model.
- [ ] The generated API artifact includes request and response expectations.
- [ ] The generated API artifact identifies validation and error-handling expectations where relevant.
- [ ] The generated API artifact identifies authentication, authorization, and integration assumptions where relevant.
- [ ] API names and entity names are consistent with the database artifact vocabulary.
- [ ] Tests verify that API output aligns with the sample brief, entities, pages, and workflows.

## Blocked by

- `.scratch/design-system/issues/02-generate-one-build-ready-service-spec.md`

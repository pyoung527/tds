Status: needs-triage

# Generate design.md

## Parent

`.scratch/design-system/PRD.md`

## What to build

Add a `design.md` generator that reads the normalized service model and page/user-flow artifact to produce service design guidance. The guidance should reflect the service purpose, users, pages/screens, workflows, and key states.

## Acceptance criteria

- [ ] The generator creates a `design.md` artifact for the sample brief.
- [ ] The artifact describes design direction grounded in the service purpose and target users.
- [ ] The artifact identifies repeated UI patterns and critical states.
- [ ] The artifact stays aligned with the page and user-flow documentation.
- [ ] Tests verify that `design.md` reflects purpose, pages/screens, workflows, users, and key states from the normalized model.

## Blocked by

- `.scratch/design-system/issues/02-generate-one-build-ready-service-spec.md`
- `.scratch/design-system/issues/05-generate-page-storyboard-and-user-flow-docs.md`

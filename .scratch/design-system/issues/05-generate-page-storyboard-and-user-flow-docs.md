Status: needs-triage

# Generate page, storyboard, and user-flow docs

## Parent

`.scratch/design-system/PRD.md`

## What to build

Add a frontend planning artifact generator that reads the normalized service model and documents pages/screens, navigation, user flows, and important UI states. The output should help developers and designers understand how users move through the service.

## Acceptance criteria

- [ ] The generator derives pages and flows from the normalized model.
- [ ] The generated artifact documents navigation or progression between pages.
- [ ] The generated artifact identifies important loading, empty, success, and error states.
- [ ] Page and workflow names are consistent with the service model and API artifact vocabulary.
- [ ] Tests verify the generated page and user-flow artifact reflects the sample storyboard.

## Blocked by

- `.scratch/design-system/issues/02-generate-one-build-ready-service-spec.md`

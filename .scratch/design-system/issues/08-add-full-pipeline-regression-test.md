Status: needs-triage

# Add full-pipeline regression test

## Parent

`.scratch/design-system/PRD.md`

## What to build

Add an end-to-end regression test that runs a representative service idea through the full TDS pipeline and verifies that the generated artifact set is coherent. The test should protect the core promise of TDS: service intent in, build-ready docs/specs out.

## Acceptance criteria

- [ ] The test runs the sample service brief through the full generation pipeline.
- [ ] The test verifies that all expected artifacts are generated.
- [ ] The test verifies that entity, page, workflow, and API vocabulary remains consistent across artifacts.
- [ ] The test verifies that assumptions and open questions are preserved.
- [ ] The test verifies that no production code or service scaffold is generated.
- [ ] The test is documented as the baseline regression test for future TDS changes.

## Blocked by

- `.scratch/design-system/issues/02-generate-one-build-ready-service-spec.md`
- `.scratch/design-system/issues/03-generate-erd-and-database-docs.md`
- `.scratch/design-system/issues/04-generate-backend-api-structure.md`
- `.scratch/design-system/issues/05-generate-page-storyboard-and-user-flow-docs.md`
- `.scratch/design-system/issues/06-generate-design-md.md`
- `.scratch/design-system/issues/07-generate-assumptions-questions-and-implementation-plan.md`
- `.scratch/design-system/issues/09-generate-prd-and-architecture-notes.md`
- `.scratch/design-system/issues/10-scaffold-tds-skill.md`
- `.scratch/design-system/issues/11-publish-skill-through-github-npx.md`

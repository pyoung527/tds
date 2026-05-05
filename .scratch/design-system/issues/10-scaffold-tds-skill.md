Status: ready-for-human

# Scaffold the TDS skill

## Parent

`.scratch/design-system/PRD.md`

## What to build

Create the first reusable TDS skill structure. The skill should package the docs/spec generation workflow so it can be reused outside this project without manually copying an improvised markdown form.

The first skill should include concise agent instructions, a reusable `service-brief.md` template, at least one filled example brief, and conventions for where generated docs/specs should be written.

The skill structure should be easy to package later for GitHub and `npx` distribution, but this slice does not need to publish it yet.

## Acceptance criteria

- [x] A TDS skill folder exists with a valid `SKILL.md`.
- [x] `SKILL.md` explains when to use the skill and how to process a service brief.
- [x] The skill includes a blank reusable `service-brief.md` template.
- [x] The skill includes at least one filled example service brief.
- [x] The skill defines output conventions for generated docs/specs.
- [x] The skill explicitly states that the first version generates docs/specs only, not production code or service scaffolds.
- [x] The skill assets are organized so a future `npx` installer can copy them into another project.

## Output

- `skills/tds/SKILL.md`
- `skills/tds/service-brief-template.md`
- `skills/tds/examples/simple-service-brief.md`
- `skills/tds/output-conventions.md`
- `skills/tds/service-brief-contract.md`

## Blocked by

- `.scratch/design-system/issues/01-define-tds-input-contract.md`

Status: ready-for-human

# Define the TDS service input contract

## Parent

`.scratch/design-system/PRD.md`

## What to build

Define the first input contract for TDS so a service brief can be represented consistently. The contract should cover service description, purpose, core functions, user storyboard, pages/screens, entities, business rules, integrations, constraints, miscellaneous notes, missing information, and uncertainty.

This is a HITL slice because the input contract defines the language TDS will use for future docs/spec generation work and should be reviewed before implementation continues.

## Acceptance criteria

- [x] The contract identifies required and optional fields for a service brief.
- [x] The contract explains how TDS represents missing, ambiguous, or contradictory input.
- [x] The contract includes a small example service brief that future slices can use.
- [x] The contract distinguishes user-provided facts from inferred assumptions.
- [x] The contract is documented in markdown so future implementation issues can reference it.

## Output

- `docs/tds/service-brief-contract.md`
- `docs/tds/service-brief-template.md`
- `docs/tds/examples/simple-service-brief.md`

## Blocked by

None - can start immediately.

---
name: tds
description: Generate service-development docs/specs from a markdown service brief. Use when the user wants to turn a service idea, PRD, storyboard, pages, entities, or service brief into build-ready specs such as PRD, ERD, API, design, architecture, implementation plan, assumptions, and open questions.
---

# TDS

TDS turns a `service-brief.md` into service-development docs/specs. It is docs/spec generation only in v1: do not generate production code and do not scaffold a service codebase.

## Quick Start

1. Find or create a service brief using `service-brief-template.md`.
2. Read the whole brief before generating anything.
3. Normalize the brief into a service model:
   - service name
   - summary and purpose
   - users / actors
   - core functions
   - pages / screens
   - user flows
   - entities
   - business rules
   - integrations
   - auth / permissions
   - constraints
   - non-functional requirements
   - success metrics
   - risks
   - facts, assumptions, and open questions
4. Generate docs/specs into a dedicated output folder.
5. Keep generated docs internally consistent. Use the same entity, page, actor, and workflow names across every artifact.

## Input Rules

Treat the service brief as the source of user-provided facts.

- If the brief says `TBD`, `unknown`, `not sure`, or asks a question, record it as an open question.
- If the brief contradicts itself, keep both sides visible and add an open question.
- If you infer something useful, label it as an assumption.
- Do not silently convert uncertainty into requirements.

Required brief sections:

- `Summary`
- `Why`
- `Users`
- `Core Functions`
- `Pages / Screens`
- `Entities`
- `Unknowns`

Optional brief sections:

- `User Flows`
- `Business Rules`
- `Integrations`
- `Auth / Permissions`
- `Constraints`
- `Non-Functional Requirements`
- `Success Metrics`
- `Risks`
- `Notes`

## Output Artifacts

Generate these files unless the user asks for a smaller set:

- `PRD.md`
- `ERD.md`
- `API.md`
- `PAGES.md`
- `DESIGN.md`
- `ARCHITECTURE.md`
- `IMPLEMENTATION.md`
- `QUESTIONS.md`

Use `tds-output/` by default when no output location is specified. If that folder already exists, ask before overwriting or write to a timestamped/suffixed folder.

## Artifact Guidance

- `PRD.md`: product purpose, users, core functions, requirements, constraints, and success metrics.
- `ERD.md`: entities, key fields, relationships, ownership, and persistence assumptions.
- `API.md`: resources/actions, request expectations, response expectations, validation, errors, auth, and integration assumptions.
- `PAGES.md`: pages/screens, navigation, user flows, and important loading/empty/success/error states.
- `DESIGN.md`: service-appropriate design direction, repeated UI patterns, interaction states, and accessibility notes.
- `ARCHITECTURE.md`: technical boundaries, integrations, data ownership, auth assumptions, deployment assumptions, risks, and decisions to revisit.
- `IMPLEMENTATION.md`: suggested implementation slices, dependencies, and review checkpoints.
- `QUESTIONS.md`: open questions, contradictions, missing decisions, and inferred assumptions.

## References

- See `service-brief-template.md` for the blank input format.
- See `examples/simple-service-brief.md` for a filled example.
- See `output-conventions.md` for output folder and file conventions.
- See `service-brief-contract.md` for detailed input semantics.

# TDS Service Brief Contract

A service brief is a markdown document that captures enough service intent for TDS to generate docs/specs: PRD, ERD, API, PAGES, DESIGN, ARCHITECTURE, IMPLEMENTATION, and QUESTIONS.

## Input Principle

Write what is known. Mark what is unknown. Do not invent certainty. TDS treats the brief as the source of facts; generated material beyond it must be labeled assumption, recommendation, or open question.

## Required Sections

- `Summary` - what the service is.
- `Why` - why it should exist.
- `Users` - people, roles, or systems using it.
- `Core Functions` - main capabilities.
- `Pages / Screens` - user-facing/admin surfaces.
- `Entities` - business objects and data concepts.
- `Unknowns` - missing decisions and open questions.

Required sections may contain `TBD`.

## Optional Sections

`User Flows`, `Business Rules`, `Integrations`, `Auth / Permissions`, `Constraints`, `Non-Functional Requirements`, `Success Metrics`, `Risks`, and `Notes`.

## Section Format

Use headings exactly as shown. Structured bullets are preferred:

```markdown
## Core Functions

- <capability name>: <short explanation>
```

## Entity Format

```markdown
## Entities

- User: a person who uses the service
  - fields: name, email, role
  - relationships: owns many Projects
```

Fields and relationships are optional; omitted details may be inferred only as labeled assumptions.

## Page / Screen Format

Pages should describe purpose, not implementation details:

```markdown
- Dashboard: overview of current work and important alerts
```

## Facts, Assumptions, and Unknowns

- Facts: explicitly stated in the service brief.
- Assumptions: inferred by TDS to make docs/specs useful.
- Unknowns: missing, ambiguous, or contradictory information.

When the brief says `TBD`, `unknown`, `not sure`, or asks a question, TDS records it as unknown. Contradictions stay visible and become open questions.

## Normalized Service Model

TDS normalizes the brief into: service name, summary, purpose, actors, functions, pages, flows, entities, business rules, integrations, auth, constraints, NFRs, success metrics, risks, facts, assumptions, and questions.

## Output Expectations

Docs/specs only. No production code or service scaffold. Default outputs: `PRD.md`, `ERD.md`, `API.md`, `PAGES.md`, `DESIGN.md`, `ARCHITECTURE.md`, `IMPLEMENTATION.md`, `QUESTIONS.md`.

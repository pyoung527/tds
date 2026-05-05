# TDS Service Brief Contract

This contract defines the first repeatable input format for TDS. A service brief is a markdown document that captures enough service intent for an agent to generate docs/specs such as PRD, ERD/database notes, API structure, page and user-flow plan, `design.md`, architecture notes, implementation plan, assumptions, and open questions.

The contract is intentionally markdown-first. It should be easy for a human to fill in, easy for an agent to read, and structured enough to normalize into a service model.

## Input Principle

Write what is known. Mark what is unknown. Do not invent certainty.

TDS should treat the brief as the source of user-provided facts. Anything generated beyond the brief must be labeled as an assumption, recommendation, or open question.

## Required Sections

Every service brief must include these sections:

- `Summary` - what the service is.
- `Why` - why the service should exist and what problem it solves.
- `Users` - the people, roles, or systems that use the service.
- `Core Functions` - the main capabilities the service must provide.
- `Pages / Screens` - user-facing screens, admin views, or major interaction surfaces.
- `Entities` - important business objects and data concepts.
- `Unknowns` - missing decisions, open questions, or areas where the author is unsure.

Required sections may contain `TBD` if the author does not know the answer yet. `TBD` is better than leaving the section out because it tells TDS the missing information is known to be missing.

## Optional Sections

These sections should be included when relevant:

- `User Flows` - step-by-step storyboards or workflows.
- `Business Rules` - rules that constrain service behavior.
- `Integrations` - external services, APIs, tools, or systems.
- `Auth / Permissions` - roles and what each role can do.
- `Constraints` - technical, business, platform, budget, timeline, legal, or operational constraints.
- `Non-Functional Requirements` - performance, accessibility, security, reliability, privacy, observability, or maintainability needs.
- `Success Metrics` - how success will be measured.
- `Risks` - known risks or likely failure modes.
- `Notes` - freeform context that does not fit elsewhere.

## Facts, Assumptions, and Unknowns

TDS must separate three kinds of information:

- **Facts** - explicitly stated in the service brief.
- **Assumptions** - inferred by TDS to make the docs/specs useful.
- **Unknowns** - missing, ambiguous, or contradictory information that needs human review.

When the brief says `TBD`, `unknown`, `not sure`, or asks a question, TDS should record that as an unknown. It should not silently choose an answer.

When the brief gives contradictory input, TDS should keep both sides visible and add an open question.

## Normalized Service Model

After reading a service brief, TDS should normalize it into these concepts before generating docs/specs:

- service name
- summary
- purpose
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
- user-provided facts
- inferred assumptions
- open questions

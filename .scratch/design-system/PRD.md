Status: needs-triage

# PRD: The Design System

## Problem Statement

People who want to develop a service often start with scattered product ideas: a service description, rough PRD, page storyboard, entities, business rules, integrations, and notes about why the service should exist. Those inputs are usually not enough for implementation. Developers still need to translate them into a coherent service plan: product requirements, data model, backend API structure, user flows, design guidance, architecture notes, implementation issues, assumptions, and open questions.

The user wants The Design System (TDS) to be that translation layer. TDS should be packaged first as a reusable agent skill that accepts structured and semi-structured service intent, then produces the core docs/specs needed to develop the service in demand.

## Solution

Build TDS as a service-specification skill. A user provides service inputs such as a PRD, core functions, purpose, user storyboard, pages/screens, entities, business rules, integrations, constraints, and related notes. The skill guides an agent to analyze those inputs and output build-ready docs/specs for the service, including PRD, database/ERD, backend API structure, page and user-flow plan, `design.md`, architecture notes, implementation plan/issues, assumptions, and open questions.

The first version should focus on docs/spec generation only. It should define a clear input model, a normalized internal service model, and a small set of high-value output artifacts. The repeatable product surface should be a skill folder containing `SKILL.md`, a reusable `service-brief.md` template, example briefs, and output conventions. The final distribution goal is to publish the skill to GitHub with an `npx` entry point so users can install or initialize it without manually copying files. The system should make enough decisions to help development start, while clearly marking assumptions and questions that need human confirmation. Production code generation and service scaffolding are explicitly out of scope for the first version.

## User Stories

1. As a service founder, I want to describe the service I want to build, so that TDS can turn the idea into implementation-ready docs/specs.
2. As a service founder, I want to provide a PRD or service description, so that TDS can understand the core purpose of the service.
3. As a service founder, I want to explain why the service is being built, so that TDS can preserve product intent in the generated artifacts.
4. As a service founder, I want to list basic and core functions, so that TDS can identify the main service capabilities.
5. As a service founder, I want to provide a user storyboard, so that TDS can understand the main user journeys.
6. As a service founder, I want to list pages or screens, so that TDS can map the service interface structure.
7. As a service founder, I want to list entities, so that TDS can infer the database model.
8. As a service founder, I want to provide business rules and integrations, so that TDS can capture non-obvious service behavior.
9. As a service founder, I want to provide incomplete notes, so that TDS can still produce a useful first draft.
10. As a service founder, I want TDS to flag missing information, so that I know what decisions still need to be made.
11. As a service founder, I want TDS to state assumptions, so that I can correct wrong interpretations before development starts.
12. As a service founder, I want generated documents to be consistent with each other, so that the database, backend, pages, and design guidance do not conflict.
13. As a service founder, I want output documents to be easy to hand to a developer or agent, so that implementation can begin quickly.
14. As a service founder, I want the output to include a PRD, so that the product requirements are clear before implementation starts.
15. As a service founder, I want the output to include an ERD, so that the service data model is clear.
16. As a service founder, I want the output to include database table definitions, so that backend work can start from a concrete schema.
17. As a service founder, I want the output to include entity relationships, so that data dependencies are explicit.
18. As a service founder, I want the output to include backend API structures, so that client and server work can be planned together.
19. As a service founder, I want the output to include API resources and operations, so that implementation teams know what endpoints or actions are required.
20. As a service founder, I want the output to include request and response expectations, so that API behavior is not vague.
21. As a service founder, I want the output to include page and screen structure, so that the frontend has a clear navigation and layout plan.
22. As a service founder, I want the output to include user-flow documentation, so that critical workflows are visible before building.
23. As a service founder, I want the output to include `design.md`, so that the service has design direction before UI implementation begins.
24. As a service founder, I want the output to include architecture notes, so that technical boundaries and constraints are visible before implementation.
25. As a service founder, I want design guidance to reflect the service purpose, so that generated UI is appropriate for the domain.
26. As a service founder, I want TDS to suggest additional build documents, so that I do not need to know every artifact name upfront.
27. As a service founder, I want TDS to distinguish confirmed requirements from inferred suggestions, so that generated docs remain trustworthy.
28. As a developer, I want TDS outputs to define implementation boundaries, so that I can break the service into modules.
29. As a developer, I want TDS outputs to include validation and error-handling expectations, so that system behavior is not limited to happy paths.
30. As a developer, I want TDS outputs to include authentication and authorization assumptions where relevant, so that security requirements are not missed.
31. As a developer, I want TDS outputs to include non-functional considerations, so that performance, accessibility, security, and maintainability are considered early.
32. As a developer, I want TDS outputs to be versionable markdown documents, so that changes can be reviewed over time.
33. As a developer, I want TDS to generate docs/specs only at first, so that humans can review the plan before code or scaffolding exists.
34. As a developer, I want the generated ERD and API structure to use the same entity names, so that implementation remains coherent.
35. As a developer, I want the generated page structure and API structure to align, so that each screen has the data it needs.
36. As a developer, I want TDS to produce implementation issues from the generated artifacts, so that work can be assigned incrementally.
37. As a designer, I want TDS to produce service design guidance, so that UI decisions are driven by user goals and workflows.
38. As a designer, I want TDS to identify page types and repeated patterns, so that the interface can be made consistent.
39. As a designer, I want TDS to identify important states, so that empty, loading, success, and error states are not forgotten.
40. As a product reviewer, I want to inspect generated assumptions and open questions, so that I can approve or correct the service plan.
41. As a product reviewer, I want each generated artifact to trace back to input material, so that I can understand why TDS made a recommendation.
42. As a maintainer, I want TDS to use a normalized internal service model, so that multiple output documents can be generated from one coherent source.
43. As a maintainer, I want artifact generators to be testable in isolation, so that PRD, ERD, API, design, architecture, and planning outputs can evolve safely.
44. As a maintainer, I want TDS to validate input quality, so that obviously missing or contradictory inputs are handled deliberately.
45. As a maintainer, I want TDS to keep generated content structured, so that future tools can parse or refine it.
46. As a future agent, I want TDS outputs to be clear enough to drive implementation issues, so that AFK development can proceed with fewer clarifying loops.
47. As a future agent, I want TDS packaged as a skill, so that I can reuse the same service-development workflow across different projects.
48. As a service founder, I want a reusable service brief template, so that I do not need to copy an improvised format each time.
49. As a maintainer, I want example service briefs bundled with the skill, so that the expected input shape is concrete.
50. As a user, I want to use TDS through an `npx` command, so that I can install or initialize the skill from GitHub without manually copying files.
51. As a maintainer, I want the published GitHub repo to include package metadata and usage docs, so that the `npx` path is clear and repeatable.

## Implementation Decisions

- Define TDS as a reusable service-specification skill for docs/spec generation first.
- Do not generate production code or scaffold a service in the first version.
- Package the first repeatable version as a skill folder with `SKILL.md`, a `service-brief.md` template, example briefs, and output conventions.
- Publishable distribution should be GitHub-first with an `npx` entry point for installing or initializing the skill.
- The `npx` entry point should distribute the skill and templates; it should not turn TDS into a production code generator.
- Use markdown as the first output format because the repo currently uses local markdown issues and docs.
- Treat the input collector as a deep module that accepts service descriptions, PRDs, core functions, user storyboards, pages/screens, entities, business rules, integrations, constraints, and miscellaneous notes.
- Treat the service model as a deep module that normalizes inputs into product purpose, actors, capabilities, entities, pages/screens, workflows, business rules, integrations, constraints, assumptions, and open questions.
- Treat artifact generation as a set of focused modules that read from the normalized service model.
- Initial artifact generators should include a PRD generator, ERD/database generator, backend API structure generator, page/user-flow generator, `design.md` generator, architecture-notes generator, assumptions/open-questions generator, and implementation-plan generator.
- Generated artifacts should clearly separate user-provided facts from inferred decisions.
- Generated artifacts should use consistent vocabulary across entities, pages, APIs, and design guidance.
- TDS should prefer useful first drafts over blocking on perfect input, but it must mark uncertainty explicitly.
- TDS should suggest additional documents when the input implies they are needed, such as security notes, testing strategy, deployment notes, or implementation issues.
- TDS should keep output artifacts build-oriented rather than producing marketing copy.
- TDS should support both web and mobile service planning at the product-artifact level, while specific implementation framework decisions remain open.
- Open triage decisions include skill name, installation location, `npx` command name, package name, GitHub repository name, output directory convention, supported artifact formats, whether any deterministic helper scripts are needed, and whether AI model integration is required beyond the host agent.

## Testing Decisions

- Good tests should verify external behavior: given input service material, TDS produces coherent artifacts with expected sections, consistent names, explicit assumptions, and useful missing-information prompts.
- Tests should avoid asserting private prompt wording, helper names, or implementation structure.
- The input collector should have unit tests for complete, partial, and contradictory input.
- The service model should have unit tests proving that entities, pages/screens, actors, workflows, business rules, integrations, assumptions, and open questions are normalized consistently.
- The PRD generator should have tests proving that generated product requirements reflect the service purpose, actors, core functions, and constraints.
- The ERD/database generator should have tests for entity extraction, relationship inference, and schema output consistency.
- The backend API structure generator should have tests proving that resources, actions, request expectations, and response expectations align with the normalized service model.
- The page/user-flow generator should have tests proving that pages and workflows reflect the input storyboard.
- The `design.md` generator should have tests proving that design guidance reflects the service purpose, pages/screens, users, and critical states.
- The architecture-notes generator should have tests proving that technical boundaries, integrations, constraints, and deployment assumptions are captured without pretending to be final decisions.
- The assumptions/open-questions generator should have tests proving that uncertainty is captured instead of silently converted into requirements.
- The implementation-plan generator should have tests proving that generated work can be split into coherent implementation slices.
- Integration tests should run a representative service idea through the full generation pipeline and inspect the generated artifact set.
- Snapshot tests may be useful for artifact structure, but they should be paired with behavior-focused assertions so harmless wording changes do not create brittle tests.
- No prior implementation tests exist in this repo yet, so the first implementation slice should establish the test framework and conventions.
- Skill behavior should be tested by running a representative service brief through the skill workflow and verifying the generated docs/spec artifact set.

## Out of Scope

- Generating production service code in the first version.
- Scaffolding a service codebase in the first version.
- Supporting every possible service domain in a deeply customized way.
- Guaranteeing a perfect database schema from incomplete or ambiguous input.
- Replacing human product, design, architecture, or security review.
- Building a full visual design system component library as the primary first milestone.
- Publishing generated artifacts to external issue trackers before the local markdown workflow is stable.
- Supporting multiple output formats before markdown output is proven useful.
- Building a hosted SaaS interface before the core generation workflow is defined.
- Building a broad standalone CLI before the skill workflow is proven useful.

## Further Notes

The current `TDS.md` defines the starting point: TDS is a reusable skill that receives service-building input and outputs docs/specs required to build the requested web or mobile service. The highest-value next step is to turn this PRD into implementation issues for a minimal vertical slice:

1. Scaffold the TDS skill shape.
2. Define a reusable `service-brief.md` template.
3. Accept a small service brief.
4. Normalize it into an internal service model.
5. Generate PRD.
6. Generate ERD/database notes.
7. Generate backend API structure.
8. Generate page/user-flow plan.
9. Generate `design.md`.
10. Generate architecture notes.
11. Generate assumptions and open questions.
12. Package the skill for GitHub distribution through `npx`.

The name "The Design System" may eventually need clarification because the current concept is broader than a traditional UI design system. For now, this PRD preserves the user's chosen name and defines the system around service design and build planning.

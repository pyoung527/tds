# The Design System [TDS]

TDS is a reusable agent skill that takes input about a service someone wants to build, then generates docs/specs that can be used to develop that service.

The input can include:
- service description or PRD
- basic and core functions
- why the service should exist
- user storyboard and pages/screens
- entities
- business rules
- integrations
- constraints and unknowns
- etc.

The output can include:
- PRD
- database / ERD
- backend API structures
- page and user-flow plan
- design.md
- architecture notes
- implementation plan / issues
- assumptions and open questions
- other docs/specs needed to build the service

The first version should generate docs/specs only. It should not generate production code or scaffold a service yet.

The first repeatable form should be a skill folder that includes:
- `SKILL.md` instructions for the agent
- a reusable `service-brief.md` template
- one or more filled example briefs
- output conventions for generated docs/specs

The final distribution goal is to publish TDS on GitHub so people can use it through an `npx` entry point. The `npx` command should make the skill easy to install, initialize, or copy into a project without manually cloning and moving files.

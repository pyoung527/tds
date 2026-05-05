---
name: tds
description: Use when turning a service idea, PRD, storyboard, page list, entity list, or markdown service brief into build-ready docs/specs. TDS generates PRD, ERD, API, pages/flows, DESIGN.md, architecture notes, implementation plan, assumptions, and open questions while explicitly avoiding production code or app scaffolding in v1.
version: 0.1.0
author: pyoung527 + Young's Hermes team
license: local
metadata:
  hermes:
    tags: [product-planning, prd, architecture, design-system, specs, bmad]
    related_skills: []
---

# TDS — The Design System

## Overview

TDS is a reusable service-specification skill. It takes a markdown service brief or equivalent product notes and turns them into a coherent docs/spec bundle for review before implementation.

V1 is docs/spec generation only. Do not generate production service code. Do not scaffold an application. The output should help a human or development agent decide what to build next, with facts, assumptions, and open questions separated clearly.

## When to Use

Use TDS when the user asks to turn a service idea, PRD, storyboard, page list, entity list, or rough product notes into PRD, ERD, API, UX/page plan, DESIGN.md, architecture notes, implementation plan, assumptions, and questions.

Do not use TDS for production code, app scaffolds, migrations, deployments, or replacing human approval.

## Inputs

Accept any mix of service brief markdown, PRD, basic/core functions, purpose, storyboard, pages/screens, entities, business rules, integrations, constraints, risks, and unknowns. When a service brief exists, read it fully before generating anything.

## Required Service Brief Sections

- `Summary`
- `Why`
- `Users`
- `Core Functions`
- `Pages / Screens`
- `Entities`
- `Unknowns`

Optional but useful: `User Flows`, `Business Rules`, `Integrations`, `Auth / Permissions`, `Constraints`, `Non-Functional Requirements`, `Success Metrics`, `Risks`, `Notes`.

## Normalize Before Writing

Normalize the input into one service model: service name, summary, purpose, users/actors, core functions, pages/screens, user flows, entities, relationships, business rules, integrations, auth, constraints, NFRs, success metrics, risks, facts, assumptions, and open questions. Use the same names across every artifact.

## Fact / Assumption / Unknown Rules

- Treat the brief as source of facts.
- `TBD`, `unknown`, `not sure`, and questions become open questions.
- Contradictions stay visible and become open questions.
- Useful inferences must be labeled assumptions.
- Do not silently convert uncertainty into requirements.

## Default Output Bundle

```text
tds-output/
  PRD.md
  ERD.md
  API.md
  PAGES.md
  DESIGN.md
  ARCHITECTURE.md
  IMPLEMENTATION.md
  QUESTIONS.md
```

Use `tds-output/` by default. If it exists and overwrite is not approved, ask or use a safe suffixed folder.

## Artifact Responsibilities

- `PRD.md`: purpose, users, requirements, non-goals, constraints, metrics, risks.
- `ERD.md`: entities, fields, relationships, ownership, enums, persistence assumptions.
- `API.md`: resources/actions, auth, validation, errors, integration assumptions.
- `PAGES.md`: page inventory, navigation, flows, page data needs, states.
- `DESIGN.md`: visual/UX direction, components, states, accessibility, responsiveness.
- `ARCHITECTURE.md`: boundaries, modules, data ownership, integrations, auth, deployment assumptions, risks.
- `IMPLEMENTATION.md`: vertical slices, dependencies, checkpoints, testing/review expectations, approval gate.
- `QUESTIONS.md`: open questions, contradictions, assumptions requiring review.

## BMAD Approval Gate

After docs/specs, stop. Ask for approval before implementation. Never push, open PRs, deploy, run destructive commands, or execute remote side effects without explicit approval.

## Supporting Files

- `service-brief-template.md`
- `service-brief-contract.md`
- `output-conventions.md`
- `examples/simple-service-brief.md`

## Source-of-Truth Convention

When hardening or publishing a TDS repo, avoid path drift:
- `docs/tds/` is the repo-level canonical documentation/source material.
- `skills/tds/` is the portable skill bundle mirrored from that canonical material for agents to copy/load.
- `tds-output/` is a golden example output, not canonical input.
If both `docs/tds/*` and `skills/tds/*` exist, state which is authoritative in README/HANDOFF and keep mirrors synchronized.

## Common Pitfalls

1. Generating app code; TDS v1 only generates docs/specs.
2. Treating assumptions as facts.
3. Using inconsistent names across artifacts.
4. Skipping open questions.
5. Producing generic docs not tied to the brief.

## Verification Checklist

- [ ] Brief was read fully.
- [ ] Required artifacts exist.
- [ ] Each artifact has source/generator/scope header.
- [ ] Entity/page/actor names are consistent.
- [ ] Facts, assumptions, questions are separated.
- [ ] No production code or app scaffold was generated.

# TDS Handoff

Date: 2026-05-06

## Current Direction

TDS means **The Design System**, but the current product direction is broader than a traditional UI design system.

TDS is a reusable agent skill that takes a markdown service brief as input and generates service-development docs/specs as output.

Final distribution goal: publish this skill to GitHub so people can use it through `npx`.

V1 scope:

- Generate docs/specs only.
- Do not generate production code.
- Do not scaffold a service codebase yet.

## Key Files

- `TDS.md` - current high-level product definition.
- `AGENTS.md` - repo agent skill setup.
- `docs/agents/` - local tracker/domain setup for Matt Pocock skills.
- `.scratch/design-system/PRD.md` - current PRD.
- `.scratch/design-system/issues/` - local markdown issues.
- `docs/tds/service-brief-contract.md` - canonical service brief input contract.
- `docs/tds/service-brief-template.md` - blank service brief template.
- `docs/tds/examples/simple-service-brief.md` - filled Launch List example.
- `skills/tds/` - scaffolded reusable TDS skill.

## Completed Work

1. Set up repo-local agent skill config:
   - `AGENTS.md`
   - `docs/agents/issue-tracker.md`
   - `docs/agents/triage-labels.md`
   - `docs/agents/domain.md`

2. Created and refined the PRD:
   - `.scratch/design-system/PRD.md`
   - Status: `needs-triage`

3. Created local markdown implementation issues:
   - Issues live under `.scratch/design-system/issues/`

4. Completed Issue 1:
   - `.scratch/design-system/issues/01-define-tds-input-contract.md`
   - Status: `ready-for-human`
   - Outputs:
     - `docs/tds/service-brief-contract.md`
     - `docs/tds/service-brief-template.md`
     - `docs/tds/examples/simple-service-brief.md`

5. Completed Issue 10:
   - `.scratch/design-system/issues/10-scaffold-tds-skill.md`
   - Status: `ready-for-human`
   - Outputs:
     - `skills/tds/SKILL.md`
     - `skills/tds/service-brief-template.md`
     - `skills/tds/examples/simple-service-brief.md`
     - `skills/tds/output-conventions.md`
     - `skills/tds/service-brief-contract.md`

## Current Issue List

- `01-define-tds-input-contract.md` - ready-for-human, completed draft.
- `02-generate-one-build-ready-service-spec.md` - next recommended work.
- `03-generate-erd-and-database-docs.md`
- `04-generate-backend-api-structure.md`
- `05-generate-page-storyboard-and-user-flow-docs.md`
- `06-generate-design-md.md`
- `07-generate-assumptions-questions-and-implementation-plan.md`
- `08-add-full-pipeline-regression-test.md`
- `09-generate-prd-and-architecture-notes.md`
- `10-scaffold-tds-skill.md` - ready-for-human, completed draft.
- `11-publish-skill-through-github-npx.md` - final distribution target.

## Recommended Next Step

Start Issue 2:

`.scratch/design-system/issues/02-generate-one-build-ready-service-spec.md`

Goal: prove the skill works by running the example service brief through the TDS workflow and generating one complete `tds-output/` docs/spec bundle.

Expected output folder:

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

Use this input:

`skills/tds/examples/simple-service-brief.md`

Important rule: keep generated content as docs/specs only. Do not create production service code or scaffold an app.

## Open Product Decisions

- Exact public package name for `npx`.
- GitHub repo name and owner.
- Whether `npx` should install the skill into a repo, initialize a service brief, or both.
- Whether the skill folder should be copied into `.agents/skills/tds`, `.codex/skills/tds`, or a user-selected location.
- Whether generated docs should default to `tds-output/` or a project-specific docs folder.

## Suggested Next Prompt

```text
Continue from HANDOFF.md and start Issue 2.
```

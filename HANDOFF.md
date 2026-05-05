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

- `README.md` - repo usage, golden example, and next steps.
- `TDS.md` - high-level product definition.
- `AGENTS.md` - repo agent setup.
- `docs/tds/` - repo-level canonical TDS input docs.
- `skills/tds/` - self-contained reusable TDS skill mirror copied from `docs/tds/`.
- `tds-output/` - golden Launch List docs/spec output, not canonical input.
- `.scratch/design-system/issues/` - local markdown issues.

## Source of Truth

`docs/tds/` is authoritative for repo input contracts/templates/examples. `skills/tds/` is the portable skill-bundle mirror for agents. `tds-output/` is only the golden generated output. Any future edits should update canonical docs first and then sync the skill mirror.

## Completed Work

1. Repo-local agent config exists under `AGENTS.md` and `docs/agents/`.
2. TDS PRD exists at `.scratch/design-system/PRD.md`.
3. Issue 1 input contract outputs exist under `docs/tds/`.
4. Issue 10 skill scaffold outputs exist under `skills/tds/`.
5. Docs-only hardening / Issue 2 golden output completed:
   - `README.md`
   - `tds-output/PRD.md`
   - `tds-output/ERD.md`
   - `tds-output/API.md`
   - `tds-output/PAGES.md`
   - `tds-output/DESIGN.md`
   - `tds-output/ARCHITECTURE.md`
   - `tds-output/IMPLEMENTATION.md`
   - `tds-output/QUESTIONS.md`

## Current Issue List

- `01-define-tds-input-contract.md` - ready-for-human, completed draft.
- `02-generate-one-build-ready-service-spec.md` - ready-for-human, golden docs/spec output created.
- `03-generate-erd-and-database-docs.md`
- `04-generate-backend-api-structure.md`
- `05-generate-page-storyboard-and-user-flow-docs.md`
- `06-generate-design-md.md`
- `07-generate-assumptions-questions-and-implementation-plan.md`
- `08-add-full-pipeline-regression-test.md` - next recommended work if deterministic test/helper code is approved.
- `09-generate-prd-and-architecture-notes.md`
- `10-scaffold-tds-skill.md` - ready-for-human, completed draft.
- `11-publish-skill-through-github-npx.md` - final distribution target, not implemented yet.

## Recommended Next Issue

Start Issue 8 only after approval for helper/test implementation:

`.scratch/design-system/issues/08-add-full-pipeline-regression-test.md`

If Young wants to stay docs-only, refine Issue 11 into a packaging PRD for future GitHub/`npx` distribution.

## Open Product Decisions

- Exact public package name for `npx`.
- GitHub repo name and owner.
- Whether `npx` installs the skill, initializes a service brief, or both.
- Whether copied skill target is `.agents/skills/tds`, `.codex/skills/tds`, `.hermes/skills/tds`, or user-selected.
- Whether generated docs default to `tds-output/` or project-specific docs folder.
- Whether to add deterministic helper scripts/tests now or keep TDS as docs/skill artifacts only.

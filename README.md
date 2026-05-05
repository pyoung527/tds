# TDS — The Design System

TDS is a reusable agent skill for turning a service idea or markdown service brief into build-ready docs/specs.

V1 scope: generate docs/specs; do not generate production app code; do not scaffold a service codebase; stop for human approval before implementation.

## Repository Contents

- `TDS.md` — high-level product definition.
- `HANDOFF.md` — current status and next issue.
- `AGENTS.md` — repo-local agent workflow notes.
- `docs/tds/` — repo-level canonical input contract, templates, and examples.
- `skills/tds/` — portable skill bundle mirror copied from the canonical docs for agent use.
- `tds-output/` — golden example output generated from the canonical sample brief.

## Source of Truth

Use `docs/tds/` as the repository source of truth for TDS input material. Keep `skills/tds/` synchronized as the reusable agent-skill mirror. Use `tds-output/` only as a golden example output, not as canonical input.

## Quick Start

1. For repo edits, update `docs/tds/service-brief-template.md` first, then mirror changes into `skills/tds/`. For user projects, copy `skills/tds/service-brief-template.md` into the project as `service-brief.md`.
2. Fill in known facts and mark unknowns as questions or `TBD`.
3. Ask an agent with TDS loaded to generate docs/specs from the brief.
4. Review `QUESTIONS.md` before implementation.

Example prompt:

```text
Use TDS. Read service-brief.md and generate the default docs/spec bundle into tds-output/. Docs/specs only; do not scaffold an app or generate production code.
```

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

## Golden Example

Input: `docs/tds/examples/simple-service-brief.md` canonical source, mirrored to `skills/tds/examples/simple-service-brief.md`

Output: `tds-output/`

Use the golden example as the quality bar for future TDS changes: consistent vocabulary, separated facts/assumptions/questions, and no production service code.

## Distribution Plan

Future goal: GitHub plus an `npx` entry point that installs or initializes the TDS skill/templates. It should not turn v1 into a production code generator.

Open decisions: package name, GitHub owner/repo, `npx` behavior, copied skill location, default output location.

## Next Steps

1. Human-review the golden output.
2. Decide whether to add deterministic regression checks.
3. Decide public package/repo naming and `npx` behavior.
4. Only after explicit approval, implement packaging or helper scripts.

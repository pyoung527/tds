Status: needs-triage

# Publish the TDS skill through GitHub and npx

## Parent

`.scratch/design-system/PRD.md`

## What to build

Package TDS so people can use it from GitHub through an `npx` entry point. The command should make the reusable skill available in another project without manually copying the skill folder, template, and examples.

This issue is about distribution. It should not change the v1 product scope: TDS generates docs/specs only, not production code and not service scaffolds.

## Acceptance criteria

- [ ] The repo has package metadata needed for an `npx` entry point.
- [ ] The `npx` command can install, initialize, or copy the TDS skill assets into a target project.
- [ ] The distributed assets include `SKILL.md`, the service brief template, example brief, and output conventions.
- [ ] Usage documentation shows the expected GitHub/`npx` command.
- [ ] The command avoids overwriting existing user files without explicit confirmation or a safe backup convention.
- [ ] The distribution docs state that v1 generates docs/specs only.

## Blocked by

- `.scratch/design-system/issues/10-scaffold-tds-skill.md`

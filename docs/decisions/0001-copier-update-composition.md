# Decision 0001: Additive skill composition through Copier updates

- Status: proposed
- Date: 2026-10-09

## Context

Harness should let a generated project incorporate additional skills through `copier update`, without requiring a separate Harness CLI. The preferred policy is additive: skills already installed must not be removed automatically.

## Proposal

- Use Copier as the project generation and update entry point.
- Record installed modules and their versions in a project manifest.
- During updates, preserve installed skills and permit opt-in to newly available skills.
- Do not automatically delete a skill merely because it is no longer offered by the template.
- Validate behavior with generation and update tests, including local modifications and conflict cases.

## Consequences

This requires a tested composition mechanism. Copier's answer persistence and file rendering alone must not be assumed to enforce additive semantics. Exact question design, manifest format, and migration strategy remain open until a prototype is tested.

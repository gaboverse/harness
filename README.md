# gaboverse/harness

**Opinionated engineering harness for AI-assisted software development.**

Harness is a versioned, reproducible set of engineering standards, workflows, agent instructions, and quality controls for AI-assisted software development.

The system is technology-agnostic by default. SDD is its initial working methodology; Copier distributes the project baseline; OpenCode is the initial agent environment.

## Start here

1. Read [the Harness contract](docs/standards/harness-contract.md).
2. Read [the project structure standard](docs/standards/project-structure.md).
3. Read [the SDD workflow](docs/standards/sdd-workflow.md).
4. Review [the Copier configuration](copier.yml).

## Project status

This is an early-stage scaffold. Core skill selection, addition, removal, and custom skill preservation have been manually exercised. Automated regression tests and OpenCode runtime compatibility still need to be validated before the template can be considered stable.

## Principles

- Opinionated by default, adaptable by design.
- Keep the core technology-agnostic.
- Maintain one canonical document per concept.
- Separate shared, updateable template content from project-owned content.
- Never treat an agent's proposal as an approved decision.
- Prefer explicit, reviewable updates over destructive automation.

## License

License selection is pending. Add a license before publishing a reusable release.

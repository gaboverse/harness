# gaboverse/harness

**Opinionated engineering harness for AI-assisted software development.**

Harness is a versioned, reproducible set of engineering standards, workflows, agent instructions, and quality controls for AI-assisted software development.

The system is technology-agnostic by default. SDD is its initial working methodology; Copier distributes the project baseline; OpenCode is the initial agent environment.

## Start here

1. Read [`docs/standards/project-structure.md`](docs/standards/project-structure.md).
2. Read [`docs/standards/sdd-workflow.md`](docs/standards/sdd-workflow.md).
3. Review [`copier.yml`](copier.yml).

## Project status

This is an initial scaffold. Project generation, skill composition, compatibility with the selected agent runtime, and Copier update behavior must be validated with automated tests before being considered stable.

## Principles

- Opinionated by default, adaptable by design.
- Keep the core technology-agnostic.
- Maintain one canonical document per concept.
- Separate shared, updateable template content from project-owned content.
- Never treat an agent's proposal as an approved decision.
- Prefer explicit, reviewable updates over destructive automation.

## License

License selection is pending. Add a license before publishing a reusable release.

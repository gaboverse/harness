
# Harness Contract

## Purpose

Harness provides a versioned, reproducible engineering baseline for
AI-assisted software development.

It defines shared engineering conventions, agent guidance, reusable
skills, project structure, and quality expectations without assuming
a specific application stack.

## Sources of truth

- Harness is the source of truth for template-owned content.
- Each generated project is the source of truth for project-owned content.
- Every engineering concept should have one canonical document.
- Agent instructions must reference canonical documents instead of
  duplicating their rules.
- Agent proposals are not approved decisions unless explicitly accepted.

## Ownership model

### Harness-owned content

Content distributed and maintained by the Harness template is
considered Harness-owned.

During Copier updates, the intended behavior is for Harness-owned
content to follow the selected template version.

Changes to Harness-owned content should be made in the Harness
repository and propagated through Copier updates.

Project-local edits to Harness-owned content are not a supported
customization mechanism.

### Project-owned content

Project-owned content belongs to the generated project and must not
be overwritten or removed merely because Harness is updated.

Project-specific engineering conventions, instructions, and skills
should be maintained in the project repository.

## Skill conventions

All project skills live directly under `.agents/skills/`.

Each skill has its own directory containing a `SKILL.md` file.

Skill directory names use lowercase kebab-case and one of these
prefixes:

- `core-`: maintained by Harness.
- `custom-`: maintained by the generated project.

Examples:

- `core-sdd`
- `core-gitmoji`
- `custom-api-conventions`
- `custom-deployment`

The `name` field in a skill's YAML frontmatter must match its
directory name.

### Core skills

Core skills are selected through the `core_skills` Copier question.

Harness owns their canonical content. The selected set determines
which core skills are installed in the generated project.

The intended update behavior is:

- Selected core skills are installed or updated from Harness.
- Deselected core skills are removed from the generated project.
- Newly available core skills can be selected during an update.

### Custom skills

Custom skills are created and maintained by the project.

Copier updates must preserve custom skill directories and their
contents, including project-specific modifications.

Custom skills are not managed through the `core_skills` selector.

### Skill dependencies

Harness does not implement automatic skill dependency management.

If a custom skill relies on a core skill, that relationship must be
documented in the relevant skill instructions.

The project is responsible for resolving any missing skill it relies on.

## Development environment

Development tooling, builds, static analysis, and tests should run
inside Docker.

Exceptions require explicit documentation and approval.

`compose-dev.yaml` is the project's development Compose entry point.
It may remain empty until the project has a concrete service or tool
that needs to run in a container.

Do not add dummy services solely to populate the Compose file.

Persistent application data must not be stored in repository
bind-mounted directories.

Secrets must not be committed to the repository or exposed to agents.

## Engineering workflow

Use the SDD workflow when a change benefits from explicit
requirements, specifications, planning, and acceptance criteria.

Scale the process to the risk and complexity of the change.

Before substantial implementation, clarify material uncertainties
and obtain approval for decisions that affect scope or architecture.

Validate changes in the agreed environment and report only checks
that were actually performed.

## Validation and compatibility

Copier generation and update behavior must be covered by regression
tests before Harness is considered stable.

The tests should cover core skill selection, addition and removal,
preservation of custom skills, and propagation of Harness-owned
changes.

OpenCode compatibility must be validated against its supported skill
locations and `SKILL.md` requirements.

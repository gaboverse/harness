---
title: Project structure and naming
status: draft
---

# Project structure and naming

## Purpose

Define a small, technology-agnostic baseline for projects generated from Harness. This document is currently `draft`.

## Root layout

```text
project/
├── README.md
├── compose-dev.yaml
├── .gitignore
├── .editorconfig
├── .pre-commit-config.yaml
├── .agents/
│   ├── agents.md
│   ├── system-prompt.md
│   ├── agents/
│   ├── skills/
│   └── knowledge/
├── docs/
│   ├── README.md
│   ├── standards/
│   ├── project/
│   ├── specifications/
│   ├── architecture/
│   └── operations/
└── services/
```

`compose-dev.yaml` must exist from the start, even when initially empty. Do not create a dummy service to populate it. `services/` may be empty until a real service is identified.

Do not create a root `src/` directory. Application source belongs to its service.

## Services

For each project-owned service requiring a custom image build:

```text
services/<service-name>/
├── Containerfile
├── .env.example
└── src/
```

Create service directories only when the service is real and agreed. A service using an official image directly may not need a local `Containerfile` or source directory.

Create `compose-srv-<environment>.yaml` only after the project decides to use Docker in that server environment. Do not create speculative environment files.

## Naming

- Prefer `kebab-case` for directories and filenames.
- Use Markdown for human-authored documentation.
- Preserve filenames required by tools and protocols.
- Use descriptive specification directories, e.g. `docs/specifications/user-authentication/`.
- A specification may contain `proposal.md`, `requirements.md`, `design.md`, `tasks.md`, and `validation.md` when useful.
- Prefer descriptive architecture decision filenames, e.g. `authentication-storage.md`.
- Avoid global IDs such as `SPEC-001`, `REQ-001`, or `TASK-001` until traceability needs justify them.

## Docker and persistence

Development tools, build tools, analyzers, validators, and tests should run in Docker unless an exception is explicitly approved and documented. Git, Docker, the OpenCode client, and Copier may run on the host. Copier does not need a bootstrap container.

Bind mounts may be used for source code, working resources, and hot reload. Do not use repository bind mounts to persist application data. Use Docker named volumes or another explicitly justified and documented persistence mechanism for persistent data.

Distinguish source code, persistent data, caches, and temporary files. Never commit real `.env` files or secrets. Commit `.env.example` files without secrets.

## Documentation ownership

- `docs/standards/`: shared normative rules.
- `docs/project/`: project-owned context and discovery state.
- `docs/specifications/`: project requirements and specifications.
- `docs/architecture/decisions/`: project architecture decisions.
- `docs/operations/`: project-specific operating procedures.

Shared template content and project-owned content must not be mixed in a way that makes template updates overwrite project decisions.

## Validation expectations

A validator should eventually check required paths, naming, Markdown quality, links, metadata, document states, requirement consistency, and traceability where defined. Template tests must generate a temporary project and exercise an update path before releases are considered stable.

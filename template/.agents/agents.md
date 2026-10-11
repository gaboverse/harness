# Agent Working Agreement

## 1. Orient yourself

Before acting:

- Inspect the repository structure and the relevant existing implementation.
- Read `system-prompt.md` and the applicable canonical standards.
- Read relevant architecture decisions and the current specification, if one exists.
- Identify the requested outcome, acceptance criteria, constraints, and approval state.
- Distinguish confirmed facts, assumptions, proposals, and approved decisions.

Do not assume the repository is a blank slate.

## 2. Choose the workflow

Use the SDD workflow documented in `docs/standards/sdd-workflow.md` when the change benefits from explicit requirements, specifications, planning, and acceptance criteria.

Scale the process to the risk and complexity of the task. Avoid unnecessary ceremony for small, low-risk changes.

Before substantial implementation:

- Clarify material uncertainties that could change the solution.
- Identify relevant dependencies and constraints.
- Obtain approval for decisions that materially affect scope or architecture.
- Define how the change will be validated.

## 3. Implement deliberately

- Follow canonical standards and approved architecture decisions.
- Prefer minimal, coherent, reviewable changes.
- Keep one canonical document per concept.
- Do not silently expand scope or introduce unrequested infrastructure.
- Do not add placeholder services or abstractions without a concrete need.
- Update canonical documentation when implementation changes agreed behavior.
- Keep project-specific conventions and skills in project-owned locations.

## 4. Respect Harness ownership

Follow `docs/standards/harness-contract.md`.

- Treat `core-*` skills as Harness-owned.
- Treat `custom-*` skills as project-owned.
- Make changes to core skills in the Harness source repository.
- Do not overwrite or remove project-owned content as part of unrelated work.
- Do not introduce an automatic skill dependency system unless explicitly approved.

## 5. Execute and validate

Run development tooling, builds, static analysis, and tests inside Docker unless an exception has been explicitly approved and documented.

Before reporting completion:

- Run the relevant checks available for the change.
- Verify acceptance criteria against observed behavior.
- Review the diff for accidental changes, secrets, and generated artifacts.
- Update affected canonical documentation.
- Identify checks that could not be run.

Never claim that a test passed unless it was actually executed and its result observed.

## 6. Report the result

Summarize:

- What changed and why.
- Which validation checks were actually run and their outcomes.
- Any deviations from the approved approach.
- Remaining risks, assumptions, and unverified behavior.

If blocked, state the specific blocker, explain why it matters, and ask the smallest useful question.

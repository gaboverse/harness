---
name: sdd
description: Guide discovery, specification, approval, implementation, and validation using an adaptive spec-driven development workflow.
---

# Spec-driven development

Use this workflow for new features, meaningful changes, and work with material uncertainty. Scale artifacts and ceremony to risk.

## Procedure

1. Read the project README, documentation map, relevant standards, discovery state, and existing specifications.
2. Clarify the goal, constraints, unknowns, and acceptance criteria. Ask targeted questions and offer alternatives when decisions matter.
3. Record facts, assumptions, proposals, and approved decisions separately.
4. Resolve critical uncertainty before substantial implementation.
5. Write or update the canonical specification. For substantial work, use the relevant subset of `proposal.md`, `requirements.md`, `design.md`, `tasks.md`, and `validation.md`.
6. Obtain explicit approval for direction and scope, material design, and implementation authorization as appropriate.
7. Implement within approved scope. If a material mismatch appears, pause and return to specification or design.
8. Validate in the agreed environment and report only checks actually performed.
9. Update canonical documentation and summarize results, remaining risks, and next steps.

## Durable state

Maintain a concise `docs/project/discovery.md` while discovery is active or important decisions remain unresolved. Record phase, confirmed decisions, assumptions, open questions, blockers, and next actions. Do not store a raw conversation transcript as project state.

## Rules

- Never represent a model-generated proposal as user-approved.
- Never invent answers to unresolved questions.
- Do not silently change approved requirements or architecture.
- Do not duplicate canonical content across documents.
- Separate document states (`draft`, `in-review`, `approved`, `superseded`) from task states.
- For low-risk, straightforward changes, combine or omit unnecessary phases while preserving clear acceptance and validation.

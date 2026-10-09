---
title: Spec-driven development workflow
status: draft
---

# Spec-driven development workflow

## Purpose

Define how an agent helps a project move from uncertainty to approved specifications, implementation, and validation. The workflow is adaptive and should scale with change size, risk, and uncertainty.

## Working principles

1. Read existing project context and documents before asking questions.
2. Ask targeted questions that reduce material uncertainty.
3. Present alternatives and trade-offs when decisions have meaningful consequences.
4. Distinguish facts, assumptions, proposals, and approved decisions.
5. Never invent answers or treat an agent's proposal as approved.
6. Keep one canonical document per concept; link rather than duplicate.
7. Do not begin substantial implementation while critical decisions remain unresolved.
8. Record decisions in durable documents, not conversation transcripts.
9. Scale process ceremony to risk.

## Workflow

### 1. Discover

Inspect the repository, context, constraints, specifications, and current discovery state. Identify the goal, stakeholders, unknowns, and constraints.

### 2. Debate and explore

Ask adaptive questions, propose options, explain trade-offs, and record assumptions. Maintain a concise `docs/project/discovery.md` when discovery is active, with current phase, confirmed decisions, assumptions, open questions, blockers, and next actions. This is a state summary, not a transcript.

### 3. Specify

Write or update the canonical specification. For substantial work, use the relevant subset of `proposal.md`, `requirements.md`, `design.md`, `tasks.md`, and `validation.md`. Requirements and acceptance criteria must be testable.

### 4. Resolve critical uncertainty

Resolve questions that could materially change scope, architecture, safety, cost, or acceptance before implementation.

### 5. Design and record decisions

Describe the design proportionately to risk. Record consequential architecture decisions in `docs/architecture/decisions/` using descriptive filenames. Avoid ADRs for every minor implementation choice.

### 6. Approve

Use explicit approval gates as appropriate:

1. **Direction and scope:** intended outcome and boundaries are agreed.
2. **Design:** material design decisions are agreed where a separate review is warranted.
3. **Implementation authorization:** acceptance criteria and plan are sufficiently clear.

For low-risk changes, gates may be combined, but the agent must not imply approval where none was given.

### 7. Plan and implement

Create a proportionate plan and implement within approved scope. If implementation reveals a material mismatch or critical uncertainty, pause and return to discovery or specification.

### 8. Validate

Run relevant checks in the agreed environment. Report what was run, what passed or failed, and what could not be verified. Never claim validation that did not occur.

### 9. Correct and close

Fix failures. Revisit specification or design if a correction changes an approved decision. At closure, update relevant documents and summarize delivered changes, validation evidence, risks, and follow-up work.

## Document states

Use these states where a document state is useful: `draft`, `in-review`, `approved`, `superseded`. Do not mix document states with task states such as `blocked`, `implemented`, or `verified`.

Changes to an approved document that affect scope, architecture, or acceptance criteria must be reviewed and recorded. Not every typo requires a formal decision.

## Exit criteria

A phase is complete when its necessary outputs exist, material uncertainties are resolved or explicitly accepted, and relevant approvals are obtained. The agent should recommend the next action and explain blockers.

## Adaptation

Use the lightest process that adequately controls the risk. Phases may be combined and unnecessary artifacts omitted, but decision status, acceptance criteria, authorization, and validation must remain clear.

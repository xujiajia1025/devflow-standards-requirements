---
name: design-analysis
description: "Turn an accepted Requirement into a reviewable, operable solution design. Use only for Design/solution-design work; do not rewrite requirements or implement code."
---

# Design analysis

Translate an approved `feature-spec` into the smallest technically sound
`solution-design`. This Skill defines the conversation method; the
`sdd-design-architect` Agent Role owns the artifact and its handoff.

## Authority and boundaries

- Read the frozen StageRun prompt, project `AGENTS.md`, materialized Rules,
  approved Requirement and current architecture evidence before each update.
- Treat the approved Requirement and cloud governance resources as immutable
  inputs. Do not silently change its scope, acceptance criteria or authority.
- Do not implement product code, approve the design or make deployment changes.
- Separate confirmed facts, decisions, assumptions, alternatives and open
  questions. Never present an unverified choice as an implementation mandate.

## Conversation loop

State the current phase in every response:

1. **Understand** — restate the accepted outcomes, constraints, actors and
   existing-system evidence that the design must preserve.
2. **Explore** — inspect current mechanisms and compare the minimal-change
   option with viable alternatives, including security and rollback impact.
3. **Draft** — update the design with stable `DEC-###` identifiers, explicit
   interfaces, data ownership, failure behavior and requirement traceability.
4. **Review** — show changed decisions, unresolved questions, contradictions,
   risks and the evidence still needed for approval.
5. **Ready for review** — only after explicit user confirmation, run the local
   solution-design contract check and report the exact command and result.

## Output contract

Write only `design/<feature-id>/solution-design.md` from the approved
`solution-design` template. Pin the Requirement SpecVersion ID, version,
status, commit/blob identity and content hash in `input_artifacts`. Preserve
all `REQ-###` and `AC-###` identifiers and map each material criterion to a
design element and verification path. Set `status: approved` only when the
architecture owner records approval.

## Handoff

Hand off the exact Requirement and Design artifact references (including
versions and hashes), decisions, residual risks and unresolved low-impact
questions to `sdd-task-planner`. Stop when the Requirement is not approved,
its Git identity cannot be verified, or a decision exceeds delegated authority.

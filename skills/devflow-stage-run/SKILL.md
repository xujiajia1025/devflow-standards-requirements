---
name: devflow-stage-run
description: "Start a governed DevFlow stage from the frozen Stage Context and coordinate a reviewable multi-turn artifact workflow."
---

# DevFlow stage run

This Skill is the executable entry point for a local `dsh` session launched by
`devflow work start`. It supplies context and boundaries; it does not replace
the Agent Role or decide whether an artifact is accepted.

## Start safely

- Locate the Git root and read `.devflow/stage-runs/active.json`.
- Load the exact `stage-context.json` selected by that pointer and verify its
  schema, stage-run identity, frozen governance snapshot, lease/session and
  hash before doing substantive work.
- Read the required Rule, Agent Role, stage Skills, Spec Template and output
  contract from the materialized cloud Release. Treat `prompt.md` as a
  human-readable rendering that can be reviewed or edited, never as the only
  source of truth.
- If the pointer, hash, lease or required resource is invalid, stop with a
  clear diagnostic. Do not fall back to embedded/local standards.

## Run the stage

For a Requirement stage, hand control to `requirements-analysis` and the
`sdd-requirements-analyst` Role. Keep the conversation multi-turn: summarize
the current understanding, ask only high-impact questions, record decisions,
and show the draft before marking it ready. Preserve stable IDs and required
template sections across updates.

## Output and boundaries

- Write only the path declared by `stage-context.json`'s output contract.
- Keep product code, credentials, governance files and unrelated documents
  untouched. Project/user instructions are additive only.
- Before handoff, re-read the entire artifact and run `devflow spec check`
  (or the exact command exposed by the active client). Report the command and
  result, but do not commit, push, or submit cloud review on behalf of the
  user.

## Session response

State the current phase (`Discover`, `Clarify`, `Draft`, `Review`, or `Ready
for review`), the current understanding, decisions/questions, changes made,
remaining risks, and the next question or action. Never claim acceptance until
the user explicitly confirms readiness and the local contract check passes.

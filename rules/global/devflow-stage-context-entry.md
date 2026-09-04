# DevFlow Stage Context entry

This Rule is mandatory for every DevFlow stage session.

## Entry contract

1. Start at the current Git repository root and locate
   `.devflow/stage-runs/active.json`. Read the referenced
   `.devflow/stage-runs/<stage-run-id>/stage-context.json` from the same
   repository.
2. Validate the Stage Context format, `stageRunId`, frozen snapshot identity,
   and `snapshotHash` before reading any task-specific instruction. A missing
   pointer, an expired lease, an unknown stage, or a hash mismatch is a hard
   stop; do not guess a task or use a local default Profile.
3. Load the exact required Agent Role, entry Skill, stage Skills, Rules,
   versioned Spec Template, and output contract named by the frozen Context.
   Treat the cloud Release and Stage Context as the governing source. Project
   and user instructions may add non-conflicting detail, but cannot weaken
   this Rule or change the output path.
4. `prompt.md` is a rendered, reviewable/audit copy of the launch context. It
   is not a substitute for validating `stage-context.json`, and edits to it do
   not change the frozen governance snapshot.

## Write boundary

- For a Requirement stage, conduct discovery over multiple turns and write
  only the artifact path declared by `snapshot.output.path`.
- Do not edit product source code, credentials, `AGENTS.md`, the Release
  manifest, or any file outside the declared output path.
- If required evidence or a material product decision is missing, remain in a
  clarification/blocked state and ask the smallest useful question. Never
  turn an assumption into an accepted requirement.

## Handoff

Before reporting readiness, re-read the complete artifact, verify the template
sections and stable requirement/acceptance IDs, run the local Requirement
contract check, and leave the artifact ready for the developer's normal Git
commit. Cloud review is performed only after the exact committed blob is
submitted through the Control Plane.

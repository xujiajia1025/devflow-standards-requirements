---
name: requirements-analysis
description: "Run a governed, multi-turn requirements discovery workflow and produce a reviewable feature specification."
---

# Requirements analysis

Turn an uncertain request into an agreed, testable Requirement Spec. This
Skill defines the conversation method; the `sdd-requirements-analyst` Agent
Role owns the `feature-spec` artifact and its handoff.

## Authority and boundaries

- Read the frozen Stage Context and the project instructions before the first
  substantive response and again before each update. The cloud Release,
  mandatory Rules, selected Role and versioned template outrank convenience
  or an ungoverned prompt edit.
- Separate confirmed facts, user decisions, assumptions, recommendations and
  open questions. Never turn an assumption into a requirement without an
  explicit decision.
- Do not implement code, select architecture/libraries, approve the Spec, or
  silently change an upstream decision. Write only the authorized output path
  from the Stage Context.

## Conversation loop

Use these phases and state the phase in every response:

1. **Discover** — restate the observable outcome, actors, evidence and
   constraints without prescribing a solution.
2. **Clarify** — ask no more than three highest-impact questions at the current
   decision frontier. Cover primary/failure journeys, scope, authorization,
   data, operations, compatibility and rollback when material.
3. **Draft** — update the feature specification with stable `US-###`, `REQ-###`,
   `NFR-###` and acceptance IDs. Make every material requirement testable.
4. **Review** — show changed sections, unresolved assumptions, contradictions
   and risks. Re-read the complete artifact and check that no architecture
   decision has been smuggled into the Requirement.
5. **Ready for review** — only after explicit user confirmation, run the local
   Requirement contract check and report the exact result. Do not submit Git or
   cloud review from this Skill.

## Required response shape

```text
【阶段】Discover | Clarify | Draft | Review | Ready for review
【当前理解】...
【待确认】...
【本轮变更】...
【剩余风险】...
【下一步】...
```

Keep the checked-in artifact as the source of truth. Before handoff, verify
all required sections, metadata, traceability and acceptance coverage, then
report the artifact path, version, hash and remaining low-impact risks.

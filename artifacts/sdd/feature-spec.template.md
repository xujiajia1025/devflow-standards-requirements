---
$schema: https://devflow.local/schemas/sdd-artifact-v1.json
schema_version: devflow.sdd-artifact/v1
template_id: requirement-standard
template_version: 1.0.0
contract_hash: 34099a0c1a0a9981a12d7318a2969e6ec3777e86a3e92711afe8a9b255e00092
artifact_id: replace-with-feature-id/feature-spec
artifact_type: feature-spec
feature_id: replace-with-feature-id
version: 1
status: draft
owner_role: sdd-requirements-analyst
input_artifacts: []
decisions: []
assumptions: []
open_questions: []
traceability: []
evidence: []
approval:
  status: pending
  authority_role: product-owner
  evidence: null
handoff_to:
  - sdd-solution-architect
---

# Feature specification: <feature name>

## [REQ-CONTEXT] 背景与问题

- Current problem and affected actors:
- Evidence location and observation:
- Observable user or business outcome:

## [REQ-GOAL] 目标与结果

- Measurable outcome:
- Success signal:

## [REQ-SCOPE] 范围与非范围

### In scope

- <bounded behavior>

### Out of scope

- <explicit exclusion>

## [REQ-ACTORS] 角色与权限

- Actor, responsibility and authorization boundary:

## [REQ-FLOW] 业务流程

### US-001: <journey name> (priority: P1)

- Actor and value:
- Primary journey:
- Failure and recovery journey:

## [REQ-ACCEPTANCE] 验收标准

- REQ-GOAL-AC-001 — GIVEN <state> WHEN <event> THEN <observable result>

## [REQ-CONSTRAINTS] 约束条件

- NFR-001 — <measurable security, reliability, compatibility, performance, privacy or operability constraint>

## [REQ-RISKS] 风险

- <known risk and mitigation>

## [REQ-OPEN-QUESTIONS] 待确认问题

- <unresolved decision, owner and impact>

## Traceability and readiness

| Requirement | Journey / acceptance scenario | Evidence | State |
|---|---|---|---|
| REQ-001 | US-001 / REQ-GOAL-AC-001 | EV-001 | draft |

Set `status: accepted` only after blocking questions are resolved, requirements
are testable, and approval evidence is recorded. Otherwise use
`needs-clarification` or `blocked`.

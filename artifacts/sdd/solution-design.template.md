---
$schema: https://devflow.local/schemas/sdd-artifact-v1.json
schema_version: devflow.sdd-artifact/v1
artifact_id: replace-with-feature-id/solution-design
artifact_type: solution-design
feature_id: replace-with-feature-id
version: 1
status: draft
owner_role: sdd-design-architect
input_artifacts:
  - artifact_id: replace-with-feature-id/feature-spec
    artifact_type: feature-spec
    version: 1
    status: accepted
    sha256: replace-with-64-character-sha256
decisions: []
assumptions: []
open_questions: []
traceability: []
evidence: []
approval:
  status: pending
  authority_role: architecture-owner
  evidence: null
handoff_to:
  - sdd-task-planner
---

# Solution design: <feature name>

## [DES-CONTEXT] 设计上下文

- Accepted `feature-spec` version, SpecVersion ID and content hash:
- Git source identity (repository, commit, path and blob SHA):
- Existing-system evidence and constraints:

## [DES-GOAL] 设计目标

- Outcomes and quality attributes derived from the accepted Requirement:

## [DES-ARCHITECTURE] 架构方案

- Component boundaries and responsibilities:
- Call and data flow:
- Selected option and rejected alternatives:

## [DES-API-DATA] 接口与数据

- Public interfaces, compatibility and error contracts:
- Data ownership, schema, retention and migration:

## [DES-NFR] 非功能要求

- Performance, reliability, operability and capacity assumptions:

## [DES-SECURITY] 安全与权限

- Trust boundaries, authentication, authorization and secrets:

## [DES-TEST] 测试方案

| Requirement / scenario | Design element | Planned evidence |
|---|---|---|
| REQ-### / AC-### | <component or contract> | <test, inspection or rehearsal> |

## [DES-ROLLOUT] 发布与回滚

- Deployment sequencing, migration, rollback and degraded mode:

## [DES-TRACE] 需求追踪

- Map every material `REQ-###` and `AC-###` to a design element and evidence.

## Residual risks and approval gate

- <risk, owner, trigger, mitigation>

Set `status: approved` only when every material requirement maps to a design
element and evidence path, blocking questions are resolved, and design approval
is recorded.

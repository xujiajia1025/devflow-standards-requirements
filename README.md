# DevFlow Team Repo — Requirements MVP

This directory is a publishing fixture for a **standards-only Team Repo**. It
is deliberately separate from the DevFlow product source tree: copy it to the
Git repository registered in the Control Plane, review the commit, and build a
cloud Release from that approved Revision.

The source manifest is `.devflow/governance-bundle.v2.json`. Its resource
provenance uses `source.revisionId: "self"`; the cloud Release Builder binds
that token to the immutable Team Repo Revision UUID after import.

This fixture contains the smallest useful Requirement-stage set:

- `devflow-stage-run` — Stage Context entry and multi-turn execution contract;
- `requirements-analysis` — requirements discovery conversation method;
- `sdd-requirements-analyst` — the artifact owner role;
- `devflow-stage-context-entry` — mandatory fail-closed entry Rule;
- `requirement-standard` + `feature-spec` — the versioned spec/template pair.

It is not a Local Engine fallback and must not be copied into the product
source tree's embedded catalog. Use the generator in
`scripts/generate-team-repo-sdd-requirements-v2.mjs` to create an importable
Git commit and a JSON import payload.

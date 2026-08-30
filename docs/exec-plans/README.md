# Execution plans

Complex implementation begins with an approved plan in `active/`; completed plans move intact to `completed/` and link their result commits/artifacts. Plans are living documents: material discoveries, deviations, and decisions are appended with dates rather than erased.

## Required format

1. Objective and user/scientific outcome
2. Context, evidence, assumptions, and requirement IDs
3. Scope and out of scope
4. Affected architecture and ADRs
5. Dependencies and interfaces
6. Ordered implementation steps with safe checkpoints
7. Tests and experimental protocol
8. Validation and acceptance evidence
9. Observability and reproducibility artifacts
10. Security, privacy, data, and governance considerations
11. Documentation/evidence updates
12. Rollback, recovery, and cleanup
13. Completion criteria
14. Open questions, decisions, and progress log

Plans must be executable by a researcher or autonomous agent unfamiliar with prior chat. Commands are added only after build tooling exists and are verified in the repository. An approved plan authorizes its stated reversible implementation scope, not external releases, scaling, spending, or governance changes.

Active: [EXP-0001 federation laboratory](active/EXP-0001-federation-laboratory.md).

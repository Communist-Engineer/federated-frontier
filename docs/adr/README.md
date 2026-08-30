# Architecture decision records

ADRs preserve decisions that would otherwise disappear into narrative. File names use `ADR-NNNN-short-title.md`.

Required fields: title, status (`Proposed`, `Accepted`, `Rejected`, `Superseded`, or `Experimental`), date, owners, evidence/requirements, context, decision, alternatives, consequences, validation/revisit trigger, and supersession links.

Accepted means the project will operate by the decision; Experimental authorizes a bounded test; Proposed is not authority. Lack of evidence is a reason to remain Proposed. Edit an ADR only to clarify or update status; supersede material changes with a new ADR.

Initial register:

| ADR | Status | Decision |
|---|---|---|
| [0001](ADR-0001-documentation-system-of-record.md) | Accepted | docs are the common system of record |
| [0002](ADR-0002-hierarchical-federation.md) | Experimental | high-bandwidth islands plus sparse global sync |
| [0003](ADR-0003-trust-tiered-contribution.md) | Accepted | permission follows verifiability and trust |
| [0004](ADR-0004-dense-baseline-before-sparse.md) | Accepted | identify optimization effects before composition |

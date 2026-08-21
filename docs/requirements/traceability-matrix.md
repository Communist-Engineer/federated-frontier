# Requirements traceability matrix

This is the backbone from evidence to validation. A dash means the link is intentionally pending, not silently absent.

| Evidence/finding | Hypothesis | Requirements | Architecture/ADR | Experiment or validation |
|---|---|---|---|---|
| E-001–E-005: low-communication optimization works at limited scale | FFI-H1, H2, H6 | FFI-SYS-001, FFI-NFR-002, FFI-SCI-004 | distributed optimization; ADR-0002 | EXP-0001 conditions 1–5 |
| E-006–E-007: path and branch composition are promising, not frontier proven | FFI-H3, H7 | FFI-SCI-004, FFI-TRAIN-006 | model architecture; ADR-0004 | EXP-0001 conditions 6–7 |
| E-008–E-010: rollout federation is separable from training | FFI-H4 | FFI-SYS-004, FFI-RL-001–006 | RL plane; trust tiers | RL shadow-mode pilot |
| E-011–E-015: useful work can be checked, training remains hard to prove | FFI-H5 | FFI-VERIFY-001–006, FFI-SEC-004 | verification plane; ADR-0003 | fabrication/red-team suite |
| E-016: Tapestry separates contribution from integration | FFI-H8 | FFI-GOV-001–004 | governance options | governance pilot review |
| E-017–E-019: inference systems exploit locality and disaggregation | FFI-H9 | FFI-INF-001–007 | inference plane | multi-class serving benchmark |
| E-020–E-022: provenance standards can compose | FFI-H10 | FFI-SYS-003, FFI-DATA-001–008 | data/provenance architecture | manifest conformance suite |
| Research gap: no 100B+ heterogeneous WAN pretraining | FFI-H1–H3 | FFI-SYS-009, FFI-SCI-006 | frontier scaling roadmap | gates G0–G6 |
| Threat finding: independent updates are not cheaply verifiable | FFI-H5 | FFI-SEC-003–009 | quarantine plus defense in depth | Byzantine update campaigns |

## Traceability rules

1. New normative requirements receive stable IDs and at least one source or explicit risk rationale.
2. Accepted ADRs name the requirements they satisfy and the evidence they rely on.
3. Execution plans enumerate requirement IDs and validation evidence.
4. Results update the evidence matrix even when they falsify a hypothesis.
5. A requirement may be removed only through an ADR or superseding requirement with history preserved.

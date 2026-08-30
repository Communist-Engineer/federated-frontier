# ADR-0003 — Trust-tiered contribution

- Status: Accepted
- Date: 2026-08-21
- Evidence: E-008, E-011–E-015
- Requirements: FFI-SEC-001–010, FFI-VERIFY-001

## Decision

Use Tiers 0–4. Permissionless Tier 4 contributes only machine-checkable, independently reproducible, or safely discardable inference-heavy work and never authoritative weight updates, secrets, restricted data, or unreleased optimizer state. All external artifacts enter quarantine.

## Rationale

Distributed RL demonstrates permissionless contribution at intermediate scale, while proof-of-training remains vulnerable or costly. Identity, attestation, reputation, and artifact verification provide distinct evidence and cannot be collapsed.

## Alternatives and consequences

Permissionless gradient aggregation was rejected for the initial system. Fully closed contribution was rejected because it prevents testing H4/H5. The decision reduces maximum available training compute but makes participation proportionate to verifiability. A later ADR may widen access after an adversarially tested verification breakthrough.

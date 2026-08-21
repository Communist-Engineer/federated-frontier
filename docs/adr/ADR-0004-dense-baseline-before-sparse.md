# ADR-0004 — Dense baseline before sparse composition

- Status: Accepted
- Date: 2026-08-21
- Evidence: E-001–E-007, E-009
- Requirements: FFI-SCI-002, FFI-SCI-004

## Decision

EXP-0001 starts with a dense decoder and independently tests Local SGD, DiLoCo, asynchrony, branch/merge, and a modular condition. Sparse MoE and path composition do not become the default until their marginal benefit is identifiable.

## Rationale

The recommended long-term hybrid combines several weakly evidenced mechanisms. Combining them initially would make success or failure uninterpretable. Dense models also have the most mature kernels and strongest baselines.

## Alternatives and consequences

Starting with MoE could expose the desired architecture sooner but entangles routing, load balance, expert placement, optimizer, and network effects. Dense training synchronizes more state and may fail to scale; that failure is useful evidence. Revisit after G1/G2 or a stronger independent WAN sparse result.

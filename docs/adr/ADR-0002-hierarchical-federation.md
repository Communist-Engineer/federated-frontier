# ADR-0002 — Hierarchical federation

- Status: Experimental
- Date: 2026-08-21
- Evidence: E-001–E-005
- Requirements: FFI-SYS-001, FFI-NFR-002, FFI-SYS-010

## Context

Public evidence demonstrates low-communication training up to 10B parameters/1T tokens over multiple continents, but not frontier-scale Byzantine heterogeneous WAN pretraining. Flat synchronous WAN collectives couple progress to the worst link.

## Decision

Treat high-bandwidth compute islands as synchronous domains and test sparse outer synchronization across them. Use task/sequence global routing and local token routing. Permit partitions to finish bounded inner work but require global authority for promotion.

## Alternatives

Flat WAN DDP is retained as a baseline. Fully independent branch/merge and pure path composition remain candidate conditions. A single centralized cluster remains the economic/performance comparator.

## Consequences and revisit

Local drift, staleness, optimizer reconciliation, and coordinator policy become primary research risks. EXP-0001 and gates G1–G3 decide whether to accept, revise, or reject this ADR.

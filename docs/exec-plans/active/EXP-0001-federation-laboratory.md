# Execution plan — EXP-0001 federation laboratory

- Status: Proposed for approval
- Objective: implement and run the [two-island experiment](../../experiments/experiment-0001.md) through the 100M screen.
- Requirements: FFI-SYS-010, FFI-FUNC-008, FFI-NFR-002, FFI-SCI-001–008, FFI-SEC-003, FFI-DATA-002.
- ADRs: ADR-0002, ADR-0004.

## Scope

Build reproducible model/data/run manifests; centralized and DDP training; network shaping; Local SGD and DiLoCo outer loops; exact communication/efficiency metrics; checkpoint quarantine/promotion; fault injection; and a three-seed 100M report. Async, merge, and modular conditions follow only after the baseline harness validates. Production control plane, public workers, payments, and 1B scaling are out of scope.

## Steps and checkpoints

1. Select a maintained PyTorch/CUDA baseline and pin containers, drivers, tokenizer, 100M architecture, dataset manifest, token budget, evaluations, and seeds.
2. Implement the reproducibility manifest and hash validation before training code changes.
3. Establish single-island and LAN DDP reference curves; validate loss and byte accounting.
4. Build bidirectional network shaping and verify the four profiles with independent probes.
5. Add Local SGD, then DiLoCo behind explicit configuration; unit-test delta sign, weighting, outer state, resume, and precision.
6. Instrument compute/communication/idle/recovery/energy; reconcile counters with packet and artifact sizes.
7. Inject stale return, process loss, island partition, and checkpoint corruption; validate quarantine and rollback.
8. Execute screening/tuning budget, freeze finalists, run three paired seeds, and generate the G1 report.
9. Append async, branch/merge, and modular milestones only after baseline review.

## Validation

Tests cover deterministic tiny-model equivalence, resume equivalence within tolerance, manifest completeness, network-profile accuracy, idempotent update submission, corrupt/stale rejection, and recovery. Acceptance is the complete G1 evidence package, not a favorable result.

## Observability and artifacts

Persist configs, manifests, container digests, environment, hardware/topology, network traces, raw/derived metrics, checkpoints, evaluator versions, plots/tables, exceptions, and cost/energy methods. No secret or dataset content appears in telemetry.

## Rollback and completion

Algorithms are feature-gated; the last signed checkpoint is immutable. Stop on lineage ambiguity, unexplained baseline divergence, data-policy failure, or unsafe access. Completion requires an independently reviewable report and updates to evidence, hypotheses, ADR-0002 status, and scaling decision.

## Open questions/progress

- Select dataset/tokenizer only after license and contamination review.
- Benchmark framework fit on DGX Spark before fixing batch/context.
- Determine whether physical separate gateways or namespaces provide adequate impairment isolation.
- 2026-08-21: specification drafted; no implementation authorized or run.

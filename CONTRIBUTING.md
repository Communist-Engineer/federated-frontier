# Contributing

FFI welcomes research reviews, replications, systems work, threat analysis, economic models, governance proposals, and reproducible experiments.

## Before proposing work

1. Read `AGENTS.md` and the task-specific sources it names.
2. Search existing ADRs, evidence entries, requirements, and active ExecPlans.
3. Open a focused issue or draft PR stating the hypothesis, evidence class, affected requirements, and intended validation.
4. Use an ExecPlan for multi-component or multi-session work.

## Research contributions

Supply a primary source when available. Record scale, hardware, topology, bandwidth, methodology, replication, and limitations. A literature list without a claim-level synthesis belongs in research notes until the evidence matrix connects it to a decision.

## Experimental contributions

Record commit, container or environment, model and checkpoint hashes, dataset manifest and hashes, seeds, hyperparameters, hardware, network conditions, timestamps, logs, metrics, artifacts, cost, and verification state. Preserve failed runs when they inform a hypothesis.

## Architecture contributions

Use stable requirement IDs. Durable decisions require an ADR with alternatives and consequences. Proposals should name the evidence that would falsify them.

## Contribution terms

The repository retains its existing MIT license for software and documentation. Until a contributor-policy ADR is accepted, contributors certify that they have the right to submit their work and that cited or linked material remains under its original terms. Model weights, datasets, and restricted artifacts require an explicit artifact-specific license and governance review.

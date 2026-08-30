# Implementation roadmap

1. **Experiment harness:** reproducible containers, dataset/run manifests, network shaping, telemetry, checkpoints, and centralized/DDP baselines.
2. **Low-communication library:** Local SGD and DiLoCo outer-loop adapter with exact byte/staleness metrics; fault injection and resume.
3. **Artifact/provenance minimum:** content hashes, signed manifests, quarantine/promotion state machine, local object store and relational registry.
4. **Two-island scheduler:** capability registration, leases, idempotent jobs, policy/trust labels, island adapters.
5. **Assurance minimum:** schema/lineage checks, canaries, redundant verification, update bounds, evaluation quarantine, incident rollback.
6. **Async federation:** fragments/quorum/grace windows/token weighting behind an experimental feature flag.
7. **RL plane:** policy distribution, versioned environments, trajectory contracts, deduplication, verifier and replay pipeline.
8. **Multi-operator hardening:** workload identity, signed builds/artifacts, regional caches, disaster recovery, accounting and dispute workflow.

Each complex change begins with an approved [execution plan](../exec-plans/README.md), names requirement IDs, and updates architecture/ADR/evidence as needed. Technology choices are benchmarked from requirements; the first slice may use PostgreSQL, S3-compatible storage, Temporal, NATS/Redpanda, SPIFFE, and OpenTelemetry, but an ADR must accept each operational dependency.

There is deliberately no production code scaffolding in this phase. EXP-0001’s execution plan defines the first implementation boundary.

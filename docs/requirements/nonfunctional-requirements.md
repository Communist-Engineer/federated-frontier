# Nonfunctional requirements

| ID | Requirement | Rationale | Priority | Verification | Status |
|---|---|---|---|---|---|
| FFI-NFR-001 | All authoritative control-plane writes **MUST** be durable across a single service failure and reconstructable from retained records. | An ephemeral coordinator is a federation-wide failure mode. | P0 | Recovery drill | Proposed |
| FFI-NFR-002 | Global synchronization **MUST** expose measured bytes per trained token, communication time, idle time, and recovery time. | Aggregate bandwidth alone hides inefficiency. | P0 | Metrics conformance | Accepted |
| FFI-NFR-003 | Scheduling **MUST** use measured useful throughput and memory/topology constraints, not vendor peak FLOPs alone. | Heterogeneous accelerators have non-equivalent kernels and reliability. | P0 | Scheduler simulation | Proposed |
| FFI-NFR-004 | A regional partition **MUST NOT** corrupt the last promoted checkpoint; recovery **SHOULD** complete within two configured outer periods in the first prototype. | Bounds fault amplification. | P0 | Partition test | Proposed |
| FFI-NFR-005 | Job and artifact APIs **MUST** be idempotent under retry and carry schema versions. | At-least-once delivery is expected. | P0 | Retry/property tests | Proposed |
| FFI-NFR-006 | Security-relevant events **MUST** be tamper-evident, time-synchronized within declared uncertainty, and retained under policy. | Attribution otherwise becomes unreliable. | P0 | Audit-log test | Proposed |
| FFI-NFR-007 | No Tier 4 worker **MUST** receive a secret, private dataset, optimizer state, or unreleased unrestricted checkpoint. | Permissionless capacity is a separate trust zone. | P0 | Access-policy tests | Proposed |
| FFI-NFR-008 | The prototype **SHOULD** be deployable on two DGX Spark-class hosts without making that platform a production dependency. | Establishes an accessible minimum laboratory. | P1 | Clean deployment | Accepted |
| FFI-NFR-009 | Every benchmark result **MUST** state contamination controls, benchmark version, sample count, uncertainty, and exclusions. | Prevents metric laundering. | P0 | Result review | Proposed |
| FFI-NFR-010 | The system **SHOULD** expose OpenTelemetry-compatible traces, metrics, and logs with bounded cardinality and privacy controls. | Cross-island diagnosis needs a common telemetry model. | P1 | Telemetry tests | Proposed |

Initial service-level objectives belong to experiments, not permanent architecture. The first thresholds are defined in [scaling gates](../experiments/scaling-gates.md) and must be revised from measured distributions.

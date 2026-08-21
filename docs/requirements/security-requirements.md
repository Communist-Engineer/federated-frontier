# Security requirements

| ID | Normative statement | Rationale | Priority | Verification | Dependencies | Status |
|---|---|---|---|---|---|---|
| FFI-SEC-001 | Every principal and workload **MUST** have a cryptographic identity bound to a trust tier and explicit capabilities. | Names and network location are insufficient. | P0 | Authorization tests | — | Proposed |
| FFI-SEC-002 | Identity, attestation, and contribution reputation **MUST NOT** be collapsed into one score. | Each answers a different question and can fail independently. | P0 | Schema review | FFI-SEC-001 | Proposed |
| FFI-SEC-003 | Updates and trajectories from Tiers 2–4 **MUST** be quarantined and validated before affecting promoted weights or official results. | Primary Byzantine containment boundary. | P0 | Poison/fabrication test | FFI-SYS-006 | Proposed |
| FFI-SEC-004 | Tier 4 **MUST** be restricted to workloads whose outputs can be independently evaluated, redundantly checked, or safely discarded. | General training updates are not cheaply verifiable. | P0 | Policy test | FFI-VERIFY-001 | Accepted |
| FFI-SEC-005 | Model, dataset, container, and checkpoint manifests **MUST** be signed; verification **MUST** occur before use. | Protects the artifact supply chain. | P0 | Signature/tamper tests | FFI-SYS-003 | Proposed |
| FFI-SEC-006 | Aggregation **MUST** enforce update bounds, contribution quotas, freshness, lineage, and anomaly checks before any robust-statistics procedure. | Robust aggregation alone does not stop Sybils or backdoors. | P0 | Adversarial suite | FFI-SEC-003 | Proposed |
| FFI-SEC-007 | Secrets and restricted data **MUST** be scoped to workload, tier, region, and time; logs **MUST NOT** contain secret or raw restricted content. | Applies least privilege and minimization. | P0 | Access/log scans | FFI-NFR-007 | Proposed |
| FFI-SEC-008 | The system **MUST** support key rotation, emergency revocation, artifact quarantine, checkpoint rollback, and incident evidence preservation. | Required for containment and recovery. | P0 | Incident exercise | FFI-FUNC-007 | Proposed |
| FFI-SEC-009 | Remote attestation **MAY** raise assurance for a measured stack but **MUST NOT** be treated as proof that claimed learning occurred. | Attestation and proof of useful work are distinct. | P0 | Design review | FFI-SEC-002 | Accepted |
| FFI-SEC-010 | Weight-release decisions **MUST** undergo capability, misuse, theft, and irreversibility review at each release level. | Federation increases replication and exfiltration paths. | P0 | Release audit | FFI-GOV-004 | Proposed |

See the [threat model](../security/threat-model.md) for adversaries and the [trust model](../security/trust-model.md) for permitted assets by tier.

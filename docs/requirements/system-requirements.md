# System requirements

Status: Draft research baseline. Normative words use RFC 2119/8174 meanings.

| ID | Normative statement | Rationale and source | Priority | Verification | Dependencies | Status |
|---|---|---|---|---|---|---|
| FFI-SYS-001 | The system **MUST** model node, island, regional, and global failure and communication domains separately. | WAN demonstrations support hierarchy, not a flat fabric ([E-002](../research/evidence-matrix.md)). | P0 | Architecture and fault-injection review | — | Proposed |
| FFI-SYS-002 | Global progress **MUST NOT** require every registered worker to be simultaneously available. | Churn is inherent to independent providers. | P0 | Partition and churn tests | FFI-SYS-001 | Proposed |
| FFI-SYS-003 | Every promoted model, dataset, trajectory batch, and evaluation result **MUST** have a content-addressed identity and provenance record. | Reproducibility and revocation require immutable identity. | P0 | Provenance completeness audit | FFI-DATA-001 | Proposed |
| FFI-SYS-004 | Training, rollout, inference, verification, and control jobs **MUST** be separately schedulable. | INTELLECT-2/3 show different resource and trust profiles ([E-008](../research/evidence-matrix.md), [E-009](../research/evidence-matrix.md)). | P0 | Scheduler conformance suite | FFI-RL-001 | Proposed |
| FFI-SYS-005 | The federation **MUST** support heterogeneous accelerator capability declarations without treating nominal FLOPs as interchangeable useful compute. | Kernels, memory, topology, reliability, and verification change effective value. | P0 | Mixed-hardware scheduling test | FFI-NFR-003 | Proposed |
| FFI-SYS-006 | All cross-trust-boundary artifacts **MUST** enter quarantine before promotion. | Limits poisoned updates, fabricated rollouts, and supply-chain compromise. | P0 | Security integration test | FFI-SEC-003 | Proposed |
| FFI-SYS-007 | The control plane **MUST** preserve an auditable state transition history for identities, jobs, artifacts, policy, and promotion decisions. | Governance and incident response require reconstructable decisions. | P0 | Event-log audit | FFI-GOV-002 | Proposed |
| FFI-SYS-008 | Components **SHOULD** expose versioned interfaces so island implementations can evolve independently. | Local autonomy is a design objective; schema drift is a material risk. | P1 | Compatibility tests | FFI-IFACE-001 | Proposed |
| FFI-SYS-009 | Scale increases **MUST** be gated by recorded scientific, reliability, provenance, security, and economic evidence. | The program optimizes knowledge before scale. | P0 | Gate review | FFI-SCI-006 | Proposed |
| FFI-SYS-010 | The first implementation **MUST** support deterministic emulation of latency, bandwidth, jitter, loss, asymmetry, and partition. | WAN claims must be falsifiable on a small laboratory. | P0 | Experiment 0001 | FFI-NET-003 | Accepted |

## Requirement policy

P0 blocks the first prototype, P1 blocks federation pilots, and P2 is desirable. “Accepted” means the project has committed to testing or implementing the requirement; it does not assert that a conforming system exists.

# Interface contracts

Interfaces are transport-neutral, versioned schemas. Initial serialization may use Protobuf or JSON plus canonical signing; selection remains Proposed.

| Contract | Core fields | Producer → consumer |
|---|---|---|
| WorkerCapability | identity, tier, attestation, hardware, kernels, memory, topology, network, policy, expiry | island → registry/scheduler |
| JobSpec | immutable ID, type, inputs, policy, resources, token/work budget, network class, lease, outputs | scheduler → worker |
| TrainingUpdate | parent, delta/checkpoint hashes, tokens, optimizer/precision, metrics, lineage, signature | island → quarantine |
| TrajectoryBatch | policy/env versions, episodes, rewards, verifier evidence, content hashes | rollout → quarantine |
| ArtifactManifest | media type, hashes, parents, license/policy, creator, transformations, signatures | any plane → registry |
| VerificationDecision | subject, checks, verifier versions, confidence, conflicts, decision, signature | assurance → promotion/accounting |
| PromotionRecord | checkpoint, evaluation bundle, release class, signers, rollback parent | governance/validator → registry |

## Invariants

- IDs are content hashes or stable opaque identifiers; mutable display names are not authority.
- Every state-changing request carries actor, idempotency key, expected version, and authorization context.
- Unknown required fields fail closed; unknown optional fields are retained where possible.
- Schema compatibility and deprecation windows are tested across at least two island implementations before federation pilots.
- Bulk bytes travel through artifact references with hash, size, media type, encryption and locality metadata.

FFI-IFACE-001: Federation interfaces **MUST** be schema-versioned and backward compatible over a declared support window. Verification: compatibility CI. Status: Proposed.

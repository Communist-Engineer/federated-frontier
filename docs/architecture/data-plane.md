# Data and artifact plane

The data plane moves immutable datasets, model shards, deltas, trajectories, evaluation outputs, manifests, and verification evidence. Control messages carry references and authorization, not bulk payloads.

## Training data flow

```mermaid
flowchart LR
  SRC["Licensed, open, synthetic, submitted"] --> ING["Ingest and hash"]
  ING --> Q["Quarantine: scan, classify, deduplicate"]
  Q --> MAN["Versioned provenance manifest"]
  MAN --> ASSIGN["Policy-aware dataset assignment"]
  ASSIGN --> TRAIN["Training island"]
  TRAIN --> USAGE["Usage and derived-artifact lineage"]
  USAGE --> MAN
```

Every transfer is resumable, integrity checked, encrypted, and policy authorized. Regional caches reduce repeated WAN movement. Data manifests can reference partitioned content without granting the control plane raw access.

## Checkpoint lifecycle

```mermaid
stateDiagram-v2
  [*] --> Candidate
  Candidate --> Quarantined
  Quarantined --> Validated
  Validated --> Signed
  Signed --> Promoted
  Promoted --> Retired
  Candidate --> Revoked
  Quarantined --> Revoked
  Validated --> Revoked
  Promoted --> Revoked
```

Promotion binds tensor hashes, architecture/tokenizer, parent(s), training/merge method, optimizer-state policy, evaluation report, signatures, and release class. Garbage collection follows retention and legal obligations; hashes and tombstone/revocation history remain auditable where lawful.

## Transport

HTTPS/QUIC multipart object transfer is the portable baseline. RDMA/NCCL/PCCL-like transports may be used within trusted compatible fabrics but must not become the federation API. Transfer metrics include logical/transmitted bytes, compression, retries, cache hits, egress cost, and integrity failures.

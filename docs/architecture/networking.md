# Networking and communication

## Domains

NVLink/NVSwitch supports fine-grained local tensor/expert communication; InfiniBand/RoCE/RDMA and high-speed Ethernet support rack/island collectives; WAN/Internet supports artifact transfer, sparse synchronization, leases, and coarse routing. NCCL-like collectives are island-local. PCCL and successor work are research candidates for Internet-tolerant collectives, not an excuse to ignore topology.

For synchronization, report `B_step`, `B_sync`, `B_token`, compression ratio, RTT, achieved bandwidth, collective wait, retries, and egress cost. The formulas in [distributed optimization](distributed-optimization.md) provide a first-order model. Checkpoint distribution is separately accounted because it can dominate outer-update deltas.

## Transport policy

- RDMA is an optimization inside a managed compatible domain.
- QUIC/HTTPS with resumable, hashed chunks is the portable WAN artifact baseline.
- Control operations are small, authenticated, idempotent, and separate from bulk flows.
- Compression/quantization includes error feedback and measures convergence impact.
- Regional caches and multicast/tree distribution reduce repeated model dissemination.

## Emulator requirement

FFI-NET-001: every training result **MUST** report transmitted bytes/token and time decomposition. FFI-NET-002: WAN-critical paths **MUST NOT** require per-token round trips in the default design. FFI-NET-003: the lab **MUST** inject asymmetric bandwidth, latency, jitter, packet loss, reordering where relevant, and partitions and validate observed conditions. FFI-NET-004: algorithms **MUST** remain correct under retry, duplicate delivery, and link reconnection.

Simulator outputs should predict measured two-island traces before extrapolation. Frontier projections state topology, concurrent flows, oversubscription, egress, and uncertainty rather than naming a nominal link speed.

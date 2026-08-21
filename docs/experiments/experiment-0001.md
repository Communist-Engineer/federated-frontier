# EXP-0001 — Two-island low-communication federation

Status: Proposed. Primary hypotheses: FFI-H1, H2, H6, H7. Decision gate: G1.

## Question

Can two small, independently scheduled compute islands under controlled WAN impairments reach near-baseline quality with substantially fewer transmitted bytes per token and acceptable time-to-quality?

## Laboratory

Minimum: two NVIDIA DGX Spark-class machines, each treated as an island; optional RTX/cloud accelerators are separate heterogeneous cohorts. Use Linux network namespaces or isolated gateways with traffic control/IFB to shape both directions. Do not couple the project to this hardware.

Network profiles:

| Profile | Bandwidth | RTT | Jitter | Loss/partition |
|---|---:|---:|---:|---|
| LAN | 10 Gbit/s | 0.2 ms | negligible | 0 |
| Metro | 1 Gbit/s | 10 ms | ±10% | 0/0.1% |
| Continental | 200 Mbit/s | 60 ms | ±20% | 0.1% |
| Constrained | 50 Mbit/s | 120 ms | ±20% | 1%; scripted 5–15 min partition |

## Model and data

Run a 100M dense decoder screen, then confirm finalists at 500M; a 1B extension requires G1. Fix tokenizer, architecture, compute/token budget, data manifest, and evaluation. Target 2–10B training tokens depending on pilot scaling; determine the exact budget through a short power/cost pilot before preregistration.

## Conditions

1. Single-island centralized baseline.
2. Cross-island DDP where feasible.
3. Local SGD with `H ∈ {8, 32, 128, 512}`.
4. DiLoCo-style inner AdamW/outer momentum with the same `H`, FP16 then int8 exchange.
5. Async/Decoupled-style token-weighted minimum-quorum/grace-window condition.
6. Branch-train-merge from a common parent using weight average plus a selected compatible merge method.
7. One modular condition: shared trunk with small independent modules or a two-path DiPaCo-inspired model.

Tune on a declared budget; shortlist on LAN and continental profiles; confirm on all four. Use three paired seeds for 100M finalists. Inject one island loss, stale return, corrupt checkpoint, and partition.

## Outcomes

Primary: validation loss, bytes/token, and wall-clock time-to-quality. Secondary: downstream scores, tokens/s, MFU, device utilization, synchronization/idle/recovery time, update staleness, cost, and energy. Security outcomes include corrupt/stale rejection and lineage-preserving rollback.

## Decision

Advance only if G1 passes. If quality fails while communication succeeds, fit the degradation against `H`, non-IID degree, and staleness. If modular/merge methods underperform, retain them as rejected or revised hypotheses rather than mixing them into the baseline.

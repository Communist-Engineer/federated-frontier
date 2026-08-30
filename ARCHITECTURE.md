# Architecture summary

FFI uses a hierarchical federation: high-frequency tensor, pipeline, sequence, expert, and data parallelism stays inside a trusted compute island; global coordination exchanges coarser model deltas, checkpoint fragments, policy versions, trajectories, metrics, and signed provenance.

The present recommendation is a **hybrid architecture under test**:

1. dense 100M–1B research models establish baselines for DDP, Local SGD, DiLoCo, asynchronous variants, and branch-train-merge;
2. trusted islands perform model training with FSDP2 or equivalent local sharding;
3. authenticated semi-trusted workers contribute verified rollouts and evaluations before they receive training-update authority;
4. a content-addressed artifact and provenance graph controls promotion;
5. sparse or modular federation enters only after dense baselines quantify its incremental value.

See [architecture overview](docs/architecture/overview.md), [candidate comparison](docs/architecture/candidate-architectures.md), and [ADRs](docs/adr/README.md).

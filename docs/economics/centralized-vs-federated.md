# Centralized versus federated economics

| Mode | Strength | Hidden/extra cost | Likely role |
|---|---|---|---|
| Hyperscale owned cluster | Highest coupled utilization and simple control | Capital, concentration, scarcity, facility lead time | Frontier baseline and tightly coupled runs |
| Federated purchased islands | Capacity diversity and geographic resilience | Egress, coordination, price dispersion, idle gaps | Low-communication training and burst capacity |
| Donated/idle compute | Low cash price and broad participation | Low reliability, support, energy/wear, verification | Checkable inference-heavy work |
| Community heterogeneous | Inclusivity and hardware reuse | Kernel fragmentation, stragglers, Sybils, policy | Rollout/evaluation/simulation; research training |
| Hybrid | Places jobs where efficient | Most complex scheduling/governance | Recommended program hypothesis |

A federation is economically superior only if avoided compute scarcity or improved utilization/participation exceeds network, verification, failure, and engineering overhead at the same quality. “Free GPU-hours” are not free useful compute.

The comparison uses time-to-quality and fully loaded dollars, not raw FLOPs. It prices WAN egress/checkpoint replication, verification redundancy, support, security, legal/governance, failed experiments, and central coordination. It also reports distributional outcomes: contributor concentration, decision rights, and whether public subsidy creates privately controlled assets.

Initial experiments should estimate break-even outer interval and contribution type by hardware/network class. The strongest early economic thesis is not WAN-equivalent data parallelism; it is using otherwise unsuitable machines for asynchronous verified rollout, search, evaluation, and simulation while scarce islands retain coupled optimization.

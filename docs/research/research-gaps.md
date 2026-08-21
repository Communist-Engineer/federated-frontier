# Research gaps

## Thesis-critical gaps

1. **Frontier WAN pretraining:** the largest clear public distributed pretraining demonstration is 10B, while frontier systems require vastly more compute, data, and operational duration.
2. **Asynchronous optimizer validity:** staleness corrections have small-to-intermediate evidence; long runs with changing membership, non-IID data, and large quorums lack decisive results.
3. **Byzantine LLM updates:** robust FL methods lack convincing evaluation on frontier-dimensional deltas, adaptive backdoors, collusion, and honest specialization.
4. **Proof of useful training:** result verification and inference commitments are viable in bounded environments; economic proof that a contributor performed a claimed training step remains open.
5. **Hierarchical sparse routing:** MoE routing assumes fast all-to-all. Task/sequence/island routing has plausible locality benefits and almost no decisive evidence.
6. **Federated pretraining merge:** merging works best for related fine-tunes. Repeated independent pretraining plus merge needs quality, stability, and interference laws.
7. **Permissionless RL economics:** the field needs cost models that include policy broadcast, failed trajectories, verification, duplicates, staleness, and adversarial work.
8. **Provenance enforcement:** metadata standards exist; deletion, license changes, contamination propagation, and eligibility through derived checkpoints remain hard.
9. **Federation-aware scaling laws:** present laws emphasize model, data, and compute. Federation adds replica count, cadence, topology, churn, trust, and verification.
10. **Institutional durability:** governance must survive funding shifts, compute-provider concentration, forks, safety disputes, and asset disposition.

## Highest-value original contributions

- a reproducible two-island federation benchmark with network and failure emulation;
- hierarchical heterogeneous DiLoCo scaling laws;
- adversarial benchmark for LLM-scale update acceptance;
- verified rollout accounting with quality-adjusted useful compute;
- island-aware sparse routing with a dense matched baseline;
- machine-readable provenance and promotion policy spanning data to model;
- formal mapping from contribution classes to governance and ownership rights.

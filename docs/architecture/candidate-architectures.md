# Candidate architecture decision matrix

Scores are hypotheses for the first research program: 1 poor, 3 mixed, 5 strong. They are not empirical results. “Evidence” uses [E0–E4](../research/evidence-matrix.md).

| Candidate | WAN communication | Scientific identifiability | Heterogeneity | Fault containment | Composition risk | Evidence | Current role |
|---|---:|---:|---:|---:|---:|---|---|
| A. Dense synchronized islands | 2 | 5 | 2 | 3 | 5 | E2 at 10B/1T tokens | Required baseline; not presumed endpoint |
| B. Hierarchical sparse MoE | 4 | 2 | 4 | 4 | 2 | E1 for large coordinated MoE, E0 for WAN routing | Research candidate after dense baseline |
| C. DiPaCo/path composition | 5 | 3 | 4 | 5 | 2 | E1 | Modular condition and later scaling research |
| D. Branch-train-merge | 5 | 4 | 5 | 5 | 2 | E1–E2 for merging, limited pretraining evidence | Complement and recovery mechanism |
| E. Shared trunk plus modules | 4 | 3 | 4 | 4 | 3 | E1–E2 in adjacent settings | Track A specialization candidate |
| F. Hybrid hierarchy | 5 | 2 | 5 | 5 | 2 | E0 as an integrated system | Long-term working hypothesis |

## Binding tradeoffs

- Dense training produces the cleanest causal experiment, but global delta synchronization still scales with synchronized parameter count.
- MoE reduces active compute, not automatically checkpoint or optimizer-state movement. WAN token routing creates a latency dependency per layer and should be local-only by default.
- DiPaCo creates independent fault domains but increases path interference, routing, and merge questions.
- Branch-train-merge tolerates partitions and heterogeneous schedules, but arithmetic parameter compatibility is fragile and optimizer-state reconciliation is unresolved.
- Modules/adapters are operationally attractive for Track A but do not prove full federated pretraining.
- The hybrid has the best structural fit and the weakest integrated evidence.

## Selection rule

Experiment 0001 uses Architecture A as the controlled reference and tests C/D/E-like conditions without entangling them. Architecture F advances only if individual mechanisms pass their gates. This is a staged composition, not a premature selection.

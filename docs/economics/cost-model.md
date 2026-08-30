# Quantitative cost model

\[
C_{total}=C_{compute}+C_{network}+C_{storage}+C_{verification}+C_{coordination}+C_{failure}+C_{engineering}.
\]

For a dense decoder, planning FLOPs are approximately `6ND`; for MoE use active parameters for the feed-forward training term while separately accounting attention, routing, embeddings, communication, and total-state storage. This is an order-of-magnitude model, not an invoice.

Assuming 0.3 PFLOP/s effective per H100-equivalent and illustrative compute prices of $1.5–$5/GPU-hour:

| Model regime | Illustrative tokens | Training FLOPs | H100-eq hours | Compute-only range |
|---|---:|---:|---:|---:|
| 1B dense | 20B | 1.2e20 | 111 | $0.2k–$0.6k |
| 7B dense | 140B | 5.9e21 | 5.4k | $8k–$27k |
| 30B dense | 600B | 1.1e23 | 100k | $0.15m–$0.50m |
| 100B dense | 2T | 1.2e24 | 1.11m | $1.7m–$5.6m |
| 300B dense | 6T | 1.08e25 | 10m | $15m–$50m |
| 1T total / 50B active MoE | 10T | ≥3e24 | ≥2.78m | ≥$4.2m–$13.9m |

Actual totals can differ by multiples due to utilization, token strategy, hardware, precision, failed/tuning runs, post-training, inference, staffing, and sparse overhead. Frontier programs require repeated experiments and inference-time compute, not one final run.

## Federation sensitivities

Global delta traffic per synchronization grows with synchronized parameters and decreases per token with local interval `H`; egress prices and checkpoint locality may dominate donated compute. Verification multiplier `r` raises effective work by `1+r`; failures add expected recomputation; heterogeneity lowers the value of peak FLOPs. Report marginal and fully loaded cost.

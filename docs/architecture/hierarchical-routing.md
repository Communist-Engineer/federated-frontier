# Hierarchical routing

Routing must jointly optimize capability and the physical federation.

\[
R_1(task)\rightarrow island,\quad R_2(sequence)\rightarrow expert\ family,\quad R_3(token)\rightarrow local\ expert.
\]

## Candidate objective

For candidate placement `j`, minimize a calibrated cost:

\[
L_j = -\hat Q_j + \lambda_l L_j^{latency} + \lambda_c C_j + \lambda_e E_j + \lambda_r Risk_j + \lambda_p PolicyViolation_j.
\]

`PolicyViolation` is an infinite exclusion, not a soft price. Quality prediction includes task/domain fit and uncertainty. Cost incorporates prefill/decode shape, cache locality, transfer, current queue, energy, and failure probability.

## Algorithms to compare

1. Rules plus capability classes: interpretable cold-start baseline.
2. Contextual bandit with conservative exploration and offline replay.
3. Constrained min-cost flow for batched capacity assignment.
4. Learned hierarchical router with rejection and fallback.

Route decisions and counterfactual candidate sets are logged for audit. Exploration never sends restricted inputs into an ineligible jurisdiction or trust tier.

## Failure and fairness

Every route carries timeout, retry budget, compatible fallbacks, and idempotency key. A failed token-local expert is handled within the island; a failed island reroutes the sequence or resumes from an application checkpoint. Reputation cannot become an unreviewable monopoly: routing reports concentration, new-contributor opportunity, regional dependence, and systematic rejection.

WAN token-level routing is **Experimental** and disabled by default because it couples each layer to unpredictable latency. The prohibition can be revised only by an ADR backed by latency and quality results.

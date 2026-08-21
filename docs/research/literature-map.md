# Literature map

| Research branch | Seminal or current anchors | Established contribution | FFI question |
|---|---|---|---|
| Local/federated optimization | Local SGD; FedAvg/FedOpt; DiLoCo | infrequent outer synchronization can preserve quality in tested regimes | how do cadence, replicas, non-IID data, and scale interact? |
| Asynchronous optimization | async SGD; async Local SGD; Decoupled DiLoCo; HeLoCo | removes global stalls while introducing staleness | which correction and quorum rules preserve time-to-quality? |
| Modular training | DiPaCo; Branch-Train-Merge; TIES | independent paths or experts can be composed | can composition carry general pretraining knowledge without interference? |
| Unreliable model parallelism | SWARM; Atom; Petals | pipelines can rebalance across slow or unreliable devices | where does WAN activation traffic beat replicated models? |
| Sparse models | Switch, GLaM, DeepSeekMoE, expert choice, MoD | conditional compute expands capacity per active FLOP | can routing align with island boundaries? |
| Distributed RL | PPO/GRPO; HybridFlow; Prime-RL; AReaL | rollout and learning planes can be asynchronous | what staleness, weight broadcast, and verifier budgets are stable? |
| Verifiable inference | replay, TOPLOC, zkLLM, TEEs | commitments, proofs, and attestation cover different trust assumptions | what layered assurance is economical by trust tier? |
| Proof of training | PoL, attacks, checkpoint replay | non-cryptographic transcripts have forgery risks | can selective replay plus attestation bound fraud? |
| Robust aggregation | Krum, medians, trimmed means, clipping, validation filters | robust under explicit statistical/adversary assumptions | do methods survive high-dimensional non-IID LLM deltas and backdoors? |
| Serving | vLLM, SGLang, Dynamo, llm-d, Petals | cache-aware and disaggregated serving improves local-cluster efficiency | which request-level abstractions survive WAN latency? |
| Provenance | W3C PROV, Croissant, SPDX, CycloneDX | interoperable metadata models exist | how can policy, deletion, and eligibility remain enforceable in derived artifacts? |
| Governance | Ostrom, knowledge commons, cooperatives, Project Tapestry | nested and polycentric governance offers design principles | how are rights tied to contributions without commodifying control? |

The bibliography records complete source metadata; the evidence matrix records claim-level use.

# Paper reading routes

The canonical citations and URLs are in [the bibliography](../research/bibliography.md); this page organizes reading order.

## Low-communication optimization

Start with Local SGD theory/empirics, DiLoCo, OpenDiLoCo, INTELLECT-1, DiLoCo scaling laws, Streaming DiLoCo, Decoupled DiLoCo, and HeLoCo. Compare assumptions about data distribution, replica count, outer interval, staleness, optimizer state, compression, and topology.

## Modular composition

Read DiPaCo with SWARM, Branch-Train-Merge, model soups/task arithmetic/TIES, and sparse MoE routing literature. Separate fine-tuning merge success from pretraining and optimizer-state composition.

## RL and verification

Read INTELLECT-2, INTELLECT-3, AReaL, PPO/GRPO-family primary work, then TOPLOC, Proof-of-Learning and its attacks, zkLLM, robust aggregation, and verifier-based RL. The order highlights the gap between working distributed rollouts and general proof of training.

## Scaling, data, safety, governance

Read Chinchilla and current inference-time/RL scaling work; W3C PROV, Croissant, SPDX/CycloneDX; NIST and current laboratory safety frameworks; then Commons-Governed AI and polycentric commons literature. Treat vendor system reports as primary engineering evidence but not independent scientific replication.

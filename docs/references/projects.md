# Project landscape

| Project | Demonstration | Scale/topology | Reuse/collaboration opportunity | Limit not to misstate |
|---|---|---|---|---|
| DiLoCo/OpenDiLoCo | low-communication decentralized pretraining | up to ~1.1B; multi-country | algorithms, configs, replication | not frontier scale |
| Prime Intellect INTELLECT-1 | decentralized pretraining from scratch | 10B, 1T tokens, multiple continents/providers | prime-diloco/PCCL, operational lessons | authenticated/managed, not Byzantine permissionless |
| INTELLECT-2 / prime-rl | permissionless asynchronous RL | 32B policy, distributed rollouts | RL stack, TOPLOC, environments | post-training, not WAN pretraining |
| INTELLECT-3 | large MoE post-training | 106B total/12B active, hundreds of H200s | async RL, expert/rollout system evidence | coordinated cluster, not global pretraining |
| Nous DisTrO | low-communication distributed optimization | early models/experiments | independent algorithm comparison | limited public scale evidence |
| Psyche | decentralized training infrastructure | evolving | protocols and operational exchange | verify demonstrations per release |
| Hivemind | decentralized training primitives | Internet/heterogeneous research use | DHT, averaging and failure lessons | no frontier pretraining demonstration |
| Petals | peer-to-peer inference/fine-tuning | Internet pipeline large open models | WAN inference behavior | inference is not training federation |
| Flower / FedML | federated-learning platforms | many clients/applications | orchestration, simulation, privacy patterns | different cross-device objective/scale |
| AI Alliance Project Tapestry | decentralized contribution with shared base/sovereign derivatives | launched 2026; early program | upstream standards and joint pilots | technical integration remains centralized |
| PyTorch distributed | FSDP2, collectives, elastic tooling | production datacenter ecosystem | island-local substrate | not a federation control plane |
| NVIDIA Dynamo / llm-d / SGLang / vLLM | disaggregated and cache-aware serving | datacenter/Kubernetes | inference-plane integration | WAN tensor coupling remains constrained |
| EleutherAI / Hugging Face | open models, datasets, evaluation/tooling | global contributor ecosystems | data/eval/model interoperability | ecosystems, not one federation architecture |

Before implementing a component, review current upstream status and prefer contribution to a maintained project where interfaces and governance align. Full primary-source links are in the [bibliography](../research/bibliography.md).

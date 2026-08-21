# State of the art: federated frontier intelligence

**Cutoff:** August 20, 2026  
**Conclusion:** technically feasible at intermediate scales; frontier-scalability remains unproven.

## What has been demonstrated

### Low-communication pretraining

DiLoCo applies many local AdamW steps and periodically feeds model deltas to an outer Nesterov optimizer. The original work reported matched synchronous quality with eight workers and roughly 500-fold less communication on its tested language-model setting [^diloco]. OpenDiLoCo independently implemented the approach with Hivemind, trained across two continents and three countries, reported 90–95% compute utilization, and scaled the public experiments to roughly 1.1B parameters [^opendiloco]. This supports E2 replicated feasibility at billion-parameter scale.

The strongest public end-to-end pretraining result is INTELLECT-1: a 10B Llama-3-style dense model trained from scratch on one trillion tokens using up to 14 concurrent nodes on three continents and 30 providers over the run. Its report gives 83–96% compute utilization, 36.2–41.4% model FLOP utilization, and a hybrid DiLoCo/FSDP2 design with int8 global reduction [^intellect1]. This is E3 for globally distributed 10B pretraining as an operated system. It remains several orders of magnitude below contemporary frontier training compute and does not establish adversarial update integrity.

Google’s DiLoCo scaling study fitted results through 2.4B and validated predictions at 4B and 10B, reporting more than 100-fold communication reduction and competitive loss for two replicas [^diloco-scaling]. Streaming DiLoCo fragments and overlaps delta exchange and reports E3M0 quantization as an experimental path to reduce peak and total traffic; it also exposes an important cost: the studied optimizer state consumes about 5 parameter-equivalents versus 3 for its data-parallel baseline [^streaming].

Decoupled DiLoCo replaces lockstep global rounds with independent learners, quorum aggregation, grace windows, fragment exchange, and token-weighted merging. Its 2026 paper reports failure simulations at millions of chips and experiments across dense and MoE tasks [^ddiloco]. This supplies strong E1–E2 evidence for the algorithmic direction, with production WAN behavior and adversarial membership still open. HeLoCo and staleness-aware outer optimizers show that update direction, non-IID data, and device speed jointly determine asynchronous quality [^heloco].

### Modular and model-parallel alternatives

DiPaCo trains routed paths through shared modules, making parameter updates less globally coupled [^dipaco]. SWARM forms temporary randomized pipelines on unreliable heterogeneous nodes and demonstrated a shared-parameter 1B model (approximately 13B before sharing) on preemptible T4s under 200 Mb/s [^swarm]. Branch-Train-Merge trained domain experts independently and merged them, while TIES and task-arithmetic methods address interference after fine-tuning [^btm] [^ties]. These approaches establish feasibility for modularity and merging; evidence for general-purpose frontier pretraining through repeated WAN merges remains E0–E1.

Sparse MoE reduces active compute, yet conventional expert parallelism requires token-level all-to-all traffic. DeepSeek-V3 demonstrates the capability and efficiency of a 671B-total/37B-active MoE on a tightly coupled cluster, rather than across a WAN [^deepseekv3]. Consequently, the useful federation hypothesis is hierarchical: island or sequence routing across regions, token routing within a local fabric. WAN token routing stays Experimental.

### Federated reinforcement learning and experience

INTELLECT-2 demonstrated fully asynchronous RL for a 32B model using a globally distributed, heterogeneous, permissionless rollout swarm. Prime-RL decoupled training, inference, and weight broadcasting; Shardcast disseminated policy weights; TOPLOC activation commitments helped validate inference; verifier environments supplied machine-checkable rewards [^intellect2]. This is E3 for the stated 32B RL system and validates the asymmetry central to FFI: many workers can generate experience while a smaller trusted set updates the policy.

INTELLECT-3 post-trained a 106B-total/12B-active MoE from GLM-4.5-Air-Base with SFT and RL, using up to 512 H200 GPUs. The report describes 60 eight-GPU nodes, approximately 16 training nodes and 44 inference nodes [^intellect3]. It demonstrates large-scale asynchronous RL infrastructure and MoE post-training. It does not represent globally permissionless pretraining from scratch; the evidence matrix keeps those categories separate.

AReaL reports asynchronous RL through 32B and scaling to 512 GPUs, supporting the broader decoupled-RL systems pattern [^areal]. The main open scientific questions are acceptable policy staleness, off-policy correction, verifier coverage, environment diversity, reward hacking, and the economics of frequent large-model dissemination.

### Federated inference

Petals shows Internet pipeline inference and fine-tuning by hosting different transformer blocks on participants [^petals]. vLLM, SGLang, NVIDIA Dynamo, and llm-d demonstrate high-performance distributed or disaggregated serving, cache-aware routing, and expert parallelism primarily within datacenter or high-performance networks [^vllm] [^sglang] [^dynamo] [^llmd]. Their control concepts transfer to a federation, while KV-cache transfer, tensor parallelism, and token-level expert parallelism generally remain latency-sensitive. WAN serving should therefore route complete requests or coarse stages to a model replica or capable island, using Petals-like cross-WAN pipelines only for throughput-oriented or research latency classes.

### Verifiable useful compute

Machine-verifiable environments provide the strongest production-ready signal: tests, compilers, formal proof kernels, SAT/SMT certificates, and deterministic simulators can validate outputs more cheaply than generating them. This verifies the result rather than every claimed FLOP.

TOPLOC creates compact locality-sensitive commitments to intermediate activations and reports strong tamper detection across tested hardware, with 258 bytes per 32 new tokens for Llama-3.1-8B-Instruct and validation faster than original inference [^toploc]. Its evidence is E2 for the tested inference configurations, with independent adversarial analysis and broader architectures needed.

Proof-of-Learning transcripts and checkpoint replay remain vulnerable to forged trajectories and adversarial examples [^pol] [^pol-broken]. zkLLM reports proofs for 13B inference in under 15 minutes and proof sizes below 200 kB, meaningful cryptographic progress with overhead far above high-throughput serving [^zkllm]. GPU confidential computing and attestation can bind work to an approved stack on supported hardware, although the hardware vendor and attestation chain become part of the trusted computing base. No method presently gives economical, general, cryptographic proof of frontier training. FFI therefore uses layered assurance: attestation where available, commitments, hidden canaries, deterministic replay, probabilistic audits, redundant execution, verifier environments, and reputation.

### Data and provenance

W3C PROV supplies a general entity/activity/agent graph; MLCommons Croissant 1.1 supplies machine-actionable dataset metadata; SPDX 3.0 AI/Dataset profiles and CycloneDX ML-BOM cover model, data, license, and supply-chain records [^prov] [^croissant] [^spdx] [^cyclonedx]. These standards support a composable provenance layer. They do not by themselves prove rights, remove personal data, or guarantee contamination detection.

### Security and Byzantine resistance

Robust aggregation—Krum, coordinate-wise median, trimmed means, geometric median, clipping, and newer validation-based methods—has theoretical and empirical value under particular IID, dimensionality, trusted-reference, and adversary-fraction assumptions. Frontier language-model deltas are extremely high-dimensional, honest updates can be heterogeneous, and a backdoor may preserve aggregate loss. Existing FL benchmarks largely use small vision or language tasks. Permissionless training updates therefore remain a critical E0–E1 gap; FFI gives them less authority than verified rollouts until a staged adversarial program succeeds.

### Governance

Project Tapestry proposes decentralized contribution, centralized technical integration, and consortium governance around a shared base model and sovereign derivatives [^tapestry]. Research on commons-governed AI and polycentric institutions offers a vocabulary for boundaries, decision rights, monitoring, sanctions, conflict resolution, and nested governance [^commons]. The institutional evidence is early. Distributed compute can coexist with concentrated ownership; technical decentralization alone changes network topology, while ownership and appropriation remain separate social relations.

## What remains unproven

- 100B+ dense or trillion-total-parameter sparse pretraining over heterogeneous public WANs;
- optimizer stability with large asynchronous quorums, non-IID data, and long-lived churn;
- Byzantine-resilient frontier-scale model-update acceptance;
- economical proof of training or general cryptographic inference verification;
- WAN-aware hierarchical MoE routing that improves end-to-end quality per dollar;
- permissionless experience markets with robust reward, privacy, and anti-collusion controls;
- governance that keeps model, data, compute, and surplus under durable shared control;
- a total-cost advantage after verification, redundancy, coordination, failures, and engineering labor.

[^diloco]: Douillard et al., “DiLoCo,” arXiv:2311.08105 (2023), https://arxiv.org/abs/2311.08105
[^opendiloco]: Jaghouar et al., “OpenDiLoCo,” arXiv:2407.07852 (2024), https://arxiv.org/abs/2407.07852
[^intellect1]: Jaghouar et al., “INTELLECT-1 Technical Report,” arXiv:2412.01152 (2024), https://arxiv.org/abs/2412.01152
[^diloco-scaling]: Charles et al., “Scaling Laws for DiLoCo,” arXiv:2503.09799 (2025), https://arxiv.org/abs/2503.09799
[^streaming]: Douillard et al., “Streaming DiLoCo,” arXiv:2501.18512 (2025), https://arxiv.org/abs/2501.18512
[^ddiloco]: Douillard et al., “Decoupled DiLoCo,” arXiv:2604.21428 (2026), https://arxiv.org/abs/2604.21428
[^heloco]: Al Asif et al., “HeLoCo,” arXiv:2606.00271 (2026), https://arxiv.org/abs/2606.00271
[^dipaco]: Douillard et al., “DiPaCo,” arXiv:2403.10616 (2024), https://arxiv.org/abs/2403.10616
[^swarm]: Ryabinin et al., “SWARM Parallelism,” ICML 2023, https://arxiv.org/abs/2301.11913
[^btm]: Li et al., “Branch-Train-Merge,” arXiv:2208.03306 (2022), https://arxiv.org/abs/2208.03306
[^ties]: Yadav et al., “TIES-Merging,” NeurIPS 2023, https://arxiv.org/abs/2306.01708
[^deepseekv3]: DeepSeek-AI, “DeepSeek-V3 Technical Report,” arXiv:2412.19437 (2024), https://arxiv.org/abs/2412.19437
[^intellect2]: Prime Intellect Team et al., “INTELLECT-2,” arXiv:2505.07291 (2025), https://arxiv.org/abs/2505.07291
[^intellect3]: Prime Intellect Team et al., “INTELLECT-3,” arXiv:2512.16144 (2025), https://arxiv.org/abs/2512.16144
[^areal]: Fu et al., “AReaL,” arXiv:2505.24298 (2025), https://arxiv.org/abs/2505.24298
[^petals]: Borzunov et al., “Petals,” arXiv:2209.01188 (2022), https://arxiv.org/abs/2209.01188
[^vllm]: vLLM documentation, https://docs.vllm.ai/en/stable/serving/parallelism_scaling/
[^sglang]: SGLang project, https://github.com/sgl-project/sglang
[^dynamo]: NVIDIA Dynamo, https://developer.nvidia.com/dynamo
[^llmd]: llm-d project, https://github.com/llm-d/llm-d
[^toploc]: Ong et al., “TOPLOC,” arXiv:2501.16007 (2025), https://arxiv.org/abs/2501.16007
[^pol]: Jia et al., “Proof-of-Learning,” arXiv:2103.05633 (2021), https://arxiv.org/abs/2103.05633
[^pol-broken]: Fang et al., “Proof-of-Learning is Currently More Broken Than You Think,” arXiv:2208.03567 (2022), https://arxiv.org/abs/2208.03567
[^zkllm]: Sun et al., “zkLLM,” arXiv:2404.16109 (2024), https://arxiv.org/abs/2404.16109
[^prov]: W3C, PROV-O, https://www.w3.org/TR/prov-o/
[^croissant]: MLCommons, Croissant 1.1, https://mlcommons.org/2026/02/croissant-1-1-standard/
[^spdx]: SPDX 3.0 specifications, https://spdx.dev/use/specifications/
[^cyclonedx]: CycloneDX ML-BOM, https://cyclonedx.org/capabilities/mlbom/
[^tapestry]: AI Alliance, Project Tapestry, https://thealliance.ai/projects/tapestry
[^commons]: “Commons-Governed Artificial Intelligence,” arXiv:2606.15466 (2026), https://arxiv.org/abs/2606.15466

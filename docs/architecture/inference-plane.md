# Federated inference plane

Inference is a scheduling and locality problem distinct from training. Current vLLM, SGLang, NVIDIA Dynamo, and llm-d systems demonstrate intra-datacenter parallelism, prefill/decode disaggregation, expert parallelism, and cache-aware routing; Petals demonstrates Internet pipeline inference. None makes tightly coupled tensor parallelism latency-insensitive across a general WAN.

## Service classes

| Class | Target | Placement | Privacy |
|---|---|---|---|
| Interactive | Low tail latency | One region/island, cache-local | Declared trusted region |
| Batch | Cost/throughput | Multi-region queues | Policy eligible |
| Rollout | Massive asynchronous sampling | Heterogeneous workers | Public or isolated envs |
| Private | Data minimization | Attested/trusted island or local edge | No external prompt logging |
| Long-running agent | Checkpointable progress | Stable island with failover | Per-tool policy |

## Routing

Capacity discovery publishes model/shard placement, quantization, context limits, supported kernels, queue, cache summaries, price/energy, trust, and failure history. The router prefers prefix/KV-cache locality and avoids splitting one request across WAN-coupled tensor stages. Prefill/decode disaggregation stays inside a measured region unless latency budgets explicitly allow cross-region transfer.

Speculative decoding may pair a local draft with a remote verifier only when expected accepted tokens exceed transfer and latency cost. Expert-parallel serving uses local high-bandwidth fabrics; global routing selects a replicated expert family before generation.

## Failure and SLOs

Requests carry deadlines, idempotency, retry safety, privacy class, and checkpointability. Interactive failures route to a compatible replica; agentic jobs resume from signed application state. Report time-to-first-token, inter-token latency, p50/p95/p99, useful tokens/s, error rate, cache hit rate, energy/token, and privacy-policy violations.

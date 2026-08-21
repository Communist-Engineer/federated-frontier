# Implementation candidates

| Layer | Candidates to evaluate | Selection criteria |
|---|---|---|
| Island training | PyTorch FSDP2/Distributed, Megatron-Core, DeepSpeed | model fit, kernel maturity, elastic/checkpoint semantics |
| Low communication | OpenDiLoCo, prime-diloco, Hivemind, DisTrO/Psyche artifacts | reproducibility, async support, exact telemetry, maintenance |
| RL | prime-rl, AReaL, OpenRLHF-style ecosystems | policy lag, verifier interfaces, heterogeneous serving |
| Inference | vLLM, SGLang, NVIDIA Dynamo, llm-d, Petals | cache locality, disaggregation, model support, WAN behavior |
| Island scheduler | Kubernetes, Slurm, Ray, SkyPilot, Nomad | operator autonomy, accelerator topology, preemption and adapters |
| Durable control | PostgreSQL, Temporal, NATS JetStream, Redpanda/Kafka | transaction/workflow/event semantics and operations |
| Identity | SPIFFE/SPIRE, cloud/cluster workload identity, vendor attestation | cross-domain federation, rotation, measured claims |
| Observability | OpenTelemetry, Prometheus-compatible metrics, Grafana | common schema, cardinality, cost, privacy |
| Artifacts | S3-compatible stores, OCI registries, content-addressed manifests | integrity, range/resume, lifecycle, regional cache |

No candidate is selected by this table. A choice needs requirements, a bounded proof, threat/operations analysis, and an ADR. Avoid rebuilding functioning upstream primitives; maintain federation-specific adapters and contracts.

# Heterogeneous hardware roles

Official/vendor specifications are capability ceilings; effective throughput must be measured with the project workload. Values are representative configurations as of the research cutoff.

| Hardware | Memory/bandwidth | Relevant fabric/precision | Likely federation role |
|---|---|---|---|
| NVIDIA H100 SXM | 80 GB HBM3, ~3.35 TB/s | NVLink ~900 GB/s; BF16/FP16/FP8 | trusted training islands |
| H200 SXM | 141 GB HBM3e, ~4.8 TB/s | NVLink generation; FP8/BF16 | larger contexts/models and RL |
| B200/DGX B200 | 180 GB-class GPU; DGX 1.44 TB/8 GPUs | NVLink domain; FP4/FP8/BF16 | high-end dense/MoE islands |
| GB200/GB300 NVL systems | multi-TB rack-scale HBM | rack NVLink domain | tightly coupled frontier island, not WAN node |
| Rubin generation | 288 GB HBM4 and ~22 TB/s vendor roadmap figures | next NVLink; new low precision | future candidate; independently benchmark when available |
| AMD MI325X | 256 GB, ~6 TB/s | Infinity Fabric; BF16/FP16/FP8 | high-memory training/inference cohort |
| AMD MI350 series | 288 GB, ~8 TB/s | newer low precision | candidate production islands |
| Google TPU v6e / 7x | 32 GB/~1.64 TB/s; 192 GB/~7.37 TB/s | ICI; cloud-only analysis | coherent cloud islands where API permits |
| DGX Spark/GB10 | 128 GB unified, ~273 GB/s; 10/200Gb networking by interface | FP4 headline | minimum lab, small training, inference |
| RTX 4090/5090, RTX Pro | 24/32 GB consumer; 5090 ~1.79 TB/s | PCIe, no datacenter fabric; low precision | rollouts, eval, small branches; reliability caveats |
| Apple M4 Max | up to 128 GB unified, ~546 GB/s | Metal ecosystem | local inference/evaluation, memory-rich experiments |

Record ECC/RAS, power cap, thermal behavior, sustained kernel performance, driver stack, local storage, link topology, network, failure rate, electricity and price. Consumer and datacenter generations are not fungible. Quantization capability does not imply equivalent training support or numerical behavior.

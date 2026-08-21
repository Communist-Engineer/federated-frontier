# Model architecture for federation

## Research position

The first research model is a conventional dense decoder so optimization effects remain identifiable. The long-term hypothesis is a hierarchical modular/sparse model, but no public result establishes frontier-scale heterogeneous WAN MoE pretraining.

## Comparison

| Family | Federation advantage | Federation liability | Program use |
|---|---|---|---|
| Dense Transformer | Mature kernels and clear baselines | Synchronizes all parameters | 100M–7B research baseline |
| Sparse MoE | Active compute can grow slower than total capacity | Router balance, expert state, and checkpoint scale | Post-baseline local expert parallelism |
| Shared trunk + adapters/modules | Small independent artifacts and policy separation | Module interference and limited base improvement | Track A specialization |
| DiPaCo paths | Independent training paths and coarse communication | Composition/routing uncertainty | Experimental modular condition |
| State-space/hybrid | Potential long-context efficiency | Less mature distributed kernels and scaling evidence | Monitor and controlled variants |
| Recurrent-depth/latent reasoning | May trade parameters for inference compute | Training stability and verification immature | Long-horizon research only |

## Hierarchical sparse candidate

`R_global(task, topology, policy, load) → island or path` occurs once per task/sequence. Inside the selected island, `R_local(hidden_state) → experts` can operate per token over a high-bandwidth fabric. Experts carry placement, compatibility, lineage, specialization, and retirement metadata.

Global expert movement is a background lifecycle operation, not part of the inference critical path. Capacity may be replicated regionally. Router objectives must include quality, load, communication, policy, and failure risk; a pure load-balancing loss is insufficient.

## Compatibility invariants

Any mergeable module declares base checkpoint, tokenizer, architecture schema, tensor shapes, training objective, dataset policy, and evaluation suite. Modules with different representations are composed through an explicit learned interface or distillation, not arithmetic weight addition.

The federation may create an inductive bias toward semantically coarse modules and long-lived local competence. That is H3, not an established benefit.

# Experimental methodology

Experiments are preregistered through an approved execution plan. The experimental unit, randomization, stopping rule, exclusions, hypothesis, primary/secondary endpoints, and scale gate are fixed before outcome inspection.

## Reproducibility record

Every run records git commit, dirty-state policy, model/checkpoint hashes, tokenizer, dataset and mixture manifests/hashes, hyperparameters and seeds, software/container/driver versions, hardware and topology, network impairment profile, start/end times, logs, metrics, result artifacts, exceptions, and verification status. Exact reruns may be impossible across accelerators; reproducibility claims state permitted numerical tolerances.

## Comparisons

Control trained tokens, architecture, data-ordering policy, evaluation budget, and effective batch where scientifically appropriate. Report both token-matched and wall-clock-matched outcomes. Hyperparameter tuning budgets are equal or disclosed. Centralized/DDP baselines use the best reasonable configuration, not an intentionally weak strawman.

100M screening runs use at least three seeds for claims that advance. Larger experiments may use sequential screening followed by preregistered confirmation of finalists, with paired seeds/data order when practical. Publish uncertainty, negative results, system failures, and all material deviations.

## Network and failures

Impairments are named, versioned inputs: bandwidth, base latency, jitter distribution, loss, reordering where relevant, asymmetry, disconnection schedule, and shaping point. Validate actual throughput/RTT/loss. Inject process, node, island, control-plane, storage, and partition faults separately so containment can be attributed.

## Integrity

Evaluation harnesses are versioned and contamination reviewed. Results distinguish researcher-measured, independently replicated, and vendor-reported figures. Raw telemetry and derived tables remain connected by scripts or documented formulas once code exists.

# Observability

The common telemetry envelope includes experiment/job ID, island and worker pseudonymous identity, trust tier, software/container measurement, hardware class, model/dataset version, topology, network profile, lease epoch, and monotonic timestamps.

## Required signals

- Training: tokens/s, step/outer-step duration, MFU estimate and formula, loss, gradient/update norms, optimizer health, memory, power.
- Network: logical/transmitted bytes, bytes/token, RTT, throughput, jitter, loss, retransmit, queue and collective wait.
- Federation: join/leave, lease expiry, straggler time, quorum, staleness, partitions, recovery point/time.
- Verification: pass/fail/conflict, latency, redundant agreement, canary accuracy, estimated cost and confidence.
- Artifacts: cache hit, transfer retries, hash mismatch, lifecycle transition and signer.
- Economics: billable time, egress, storage, verification multiplier, accepted useful contribution.

OpenTelemetry-compatible traces/logs/metrics are preferred at component boundaries; Prometheus-compatible aggregates may back dashboards. Raw high-cardinality identifiers and content are access controlled. Logs never become a covert dataset or secret store.

Every published metric defines numerator, denominator, clock, exclusions, uncertainty, and source. MFU must state the theoretical FLOP convention. Cross-island clock offset is measured and recorded; causal ordering relies on job epochs and event IDs rather than wall clocks alone.

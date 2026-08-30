# Evidence artifacts

This directory will hold immutable or generated experiment evidence packages: manifests, checksums, small result tables, verification summaries, and links to content-addressed large artifacts. It must not contain restricted data, model secrets, or unreviewed binary dumps.

Each package names experiment ID, git commit, dataset/model manifests, hardware/topology/network profile, run IDs, derivation scripts, verification status, and the evidence-matrix entries it updates. Raw large telemetry belongs in governed object storage with hashes and retention policy.

No experiment has been executed in this research-foundation phase; the substantive evidence register is [docs/research/evidence-matrix.md](../../docs/research/evidence-matrix.md).

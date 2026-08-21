# Model security and responsible scaling

Model security spans theft prevention, dangerous-capability evaluation, access, release, monitoring, and incident response. Reference practice includes the NIST AI RMF Generative AI Profile, laboratory preparedness/responsible-scaling frameworks, and the International AI Safety Report; these are governance inputs, not proof of safety.

## Release levels

1. Research sandbox: small models/checkpoints and non-sensitive evaluations.
2. Trusted federation: controlled weights for eligible training islands.
3. Restricted API/service: capability access without general weight distribution.
4. Partner release: contractual and technical controls.
5. Public weights: irreversible release after documented benefit/risk decision.

Evaluations cover cyber misuse, biological/chemical assistance where applicable, autonomy and long-horizon agents, model self-exfiltration, persuasion/manipulation, privacy/memorization, safeguards, and domain-specific hazards. Thresholds must be set before high-risk runs and linked to access controls.

Federation creates a tension: replication and external ownership improve resilience and participation while increasing theft and proliferation paths. Transparent research does not require immediate unrestricted release of every frontier checkpoint. The governance body must state who controls each release and appeal.

Incident response includes detection, key/identity revocation, scheduler fencing, artifact quarantine, checkpoint rollback, evidence preservation, stakeholder notice, root-cause analysis, and safe re-entry. Exercises precede every major scale gate.

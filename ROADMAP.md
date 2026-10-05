# Roadmap

This roadmap describes intended order, not a delivery commitment. Scope may change as Windows telemetry is validated.

## Development — current

- Repository boundary, evidence vocabulary, privacy boundary and bilingual desktop foundation are in place.
- Private development builds include process identity metadata and lifecycle sampling; file version, local Authenticode, executable hash and redacted command line remain partial and need broader Windows validation.
- TCP endpoints and UDP local bindings are sampled. Optional elevated TCP counters, separate TCP/UDP user-ETW event-byte estimates, and DNS query-name collection exist with limited loopback/host validation; UDP remote peers and DNS name matches remain partial and DNS-to-process attribution is unavailable.
- Sensitive-path classification, protected-folder notifications, metadata-size snapshots and a default-off File ETW pipeline exist. Live File ETW and elevated TCP counter validation remain open.
- Production correlation, saved rules, ten deterministic development scenarios, local reports and selected persistence snapshots exist with the limits in the [capability matrix](docs/detection-capabilities.md). Simulations are not evidence of live collector coverage.

## Early development

- Validate process identity and lifecycle behavior on more supported Windows versions and protected-process cases.
- Validate optional TCP byte counters under an authorized elevated token and confirm source coverage.
- Validate File ETW and protected-folder notification coverage, permission behavior and load across supported Windows builds and filesystems.
- Continue improving DNS, UDP and short-lived connection visibility only where reliable process attribution can be demonstrated.

## Correlation

- Expand production evidence paths and validate correlation against controlled live telemetry.
- Keep deterministic development scenarios separate from collector events.
- Continue bounded queues, retention and event summaries under long-running and burst conditions.

## Extended observability

Evaluate credential and browser-profile metadata access, staging artifacts, archives, persistence and child-process context. Mark a capability supported only after implementation and repeatable validation on supported Windows versions.

## Release readiness

Provision protected release signing material, validate the signed updater flow and user-started recovery with signed Windows packages, finish visual/accessibility review and create the six approved showcase screenshots. Publish a signed Windows beta only after the release checklist passes.

There is no promised date. Payment and subscription are outside the initial functional release.

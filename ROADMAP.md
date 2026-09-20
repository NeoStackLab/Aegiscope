# Roadmap

This roadmap describes intended order, not a delivery commitment. Scope may change as Windows telemetry is validated.

## Development — current

- Repository boundary, evidence vocabulary, privacy boundary and bilingual desktop foundation are in place.
- Private development builds have partial sampled process lifecycle and TCP endpoint visibility.
- Publisher/signature identity, traffic bytes, DNS mapping and file access remain unimplemented; see the capability matrix.

## Early development

- Complete remaining process identity and lifecycle coverage.
- Validate the current sampled network endpoint view across supported Windows versions.
- Network destinations and qualified per-process traffic attribution.
- Sensitive-file access, aggregation and explicit platform limits.

## Correlation

- Explainable rules, incidents and observed/inferred/unknown evidence.
- Deterministic simulation scenarios for development and demos.
- Bounded queues, retention and event summaries.

## Extended observability

Evaluate credential and browser-profile metadata access, staging artifacts, archives, persistence and child-process context. Mark a capability supported only after implementation and repeatable validation on supported Windows versions.

## Release readiness

Build a private updater that validates trusted release metadata and versions, verifies checksum and code signing, and never executes an unverified binary. Publish a signed Windows beta only after release review.

There is no promised date. Payment and subscription are outside the initial functional release.

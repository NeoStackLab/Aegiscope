# Roadmap

This roadmap describes intended order, not a delivery commitment. Scope may change as Windows telemetry is validated.

## Foundation — current

- Separate public product materials from private source.
- Define evidence vocabulary, privacy boundaries and capability status.
- Design a bilingual, dark-first desktop experience.

## Early development

- Secure desktop shell and local storage.
- Process identity and lifecycle.
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

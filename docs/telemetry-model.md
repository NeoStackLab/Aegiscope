# Telemetry and Evidence Model

Aegiscope connects observations into a timeline without turning temporal association into proof of causation.

- **OBSERVED** — a normalized event directly supported by a collector, with source and confidence.
- **INFERRED** — a cautious rule-based interpretation supported by observed events in a bounded time window.
- **UNKNOWN** — a relevant fact the available telemetry cannot establish.

Example: observed access to many Git object paths, creation of a large local file, an external connection and associated outbound byte activity. The sequence may be consistent with staging followed by transfer. Whether Git content appeared in encrypted payloads remains unknown.

Every event should retain event time, process identity snapshot, source, confidence and stable ID. Aggregates keep counts/time bounds and link to underlying evidence. Collector gaps and dropped-event counters must be visible rather than treated as no activity.

The product does not inspect or decrypt HTTPS by default. A new cloud destination or large transfer is context, not proof of malicious intent.

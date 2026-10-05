# Telemetry and Evidence Model

Aegiscope connects observations into a timeline without turning temporal association into proof of causation.

- **OBSERVED** — a normalized event directly supported by a collector, with source and confidence.
- **INFERRED** — a cautious rule-based interpretation supported by observed events in a bounded time window.
- **UNKNOWN** — a relevant fact the available telemetry cannot establish.

Example: observed access to many Git object paths, a post-notification file-size snapshot, an external connection and either a per-connection TCP counter delta or a user-ETW event-byte estimate. The sequence may be consistent with local staging followed by transfer. A directory notification does not identify the writer, and the snapshot is not proof that the application created or overwrote the file. Event-byte estimates are not confirmed delivery. Whether Git content appeared in encrypted payloads remains unknown.

Every event should retain event time, process identity snapshot, source, confidence and stable ID. Aggregates keep counts/time bounds and link to underlying evidence. Collector gaps and dropped-event counters must be visible rather than treated as no activity.

The product does not inspect or decrypt HTTPS by default. A new cloud destination or large transfer is context, not proof of malicious intent.

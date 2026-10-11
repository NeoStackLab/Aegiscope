# Privacy Model

Aegiscope's default analysis model is local-first: collect only metadata needed for explainable behavior evidence, store it locally with bounded retention and do not upload behavioral history by default.

## Data minimization

- Prefer paths, categories, timestamps, process identity and aggregate byte counts over file contents.
- Never collect passwords, API token values, SSH private-key contents, browser cookies or credential contents.
- Treat paths, domains and command lines as potentially personal. Avoid command-line arguments unless needed; redact likely secrets.
- Keep raw high-volume evidence local and send summaries to the UI.

## User control

Settings should make each category and protected location explicit. Retention and deletion must be visible. When retention removes local records, Aegiscope asks SQLite to overwrite deleted ordinary-table content in the database pages. This reduces residual data in the closed database file but is not a forensic-erasure guarantee: older WAL frames may remain until checkpoint/close, and backups, system snapshots, swap and SSD remapping are outside Aegiscope's control. The main local database files have per-writer size ceilings; at a ceiling, new evidence may fail to save and the affected history may be incomplete. WAL files can temporarily exceed their post-checkpoint target if a reader delays checkpointing. A database already above its ceiling is preserved rather than automatically shrunk. Any optional diagnostics must state fields, purpose, destination and retention before consent.

## Product honesty

An access event proves only the operation supported by its source. Correlation can support an inference; it does not prove a file's content was transmitted. Unknowns stay visible.

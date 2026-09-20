# Privacy Model

Aegiscope's default analysis model is local-first: collect only metadata needed for explainable behavior evidence, store it locally with bounded retention and do not upload behavioral history by default.

## Data minimization

- Prefer paths, categories, timestamps, process identity and aggregate byte counts over file contents.
- Never collect passwords, API token values, SSH private-key contents, browser cookies or credential contents.
- Treat paths, domains and command lines as potentially personal. Avoid command-line arguments unless needed; redact likely secrets.
- Keep raw high-volume evidence local and send summaries to the UI.

## User control

Settings should make each category and protected location explicit. Retention and deletion must be visible. Any optional diagnostics must state fields, purpose, destination and retention before consent.

## Product honesty

An access event proves only the operation supported by its source. Correlation can support an inference; it does not prove a file's content was transmitted. Unknowns stay visible.

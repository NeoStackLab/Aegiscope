# Aegiscope

**See what your apps read, access and send.**

Aegiscope is an Application Privacy Observatory for Windows. It is being designed to connect sensitive local access, processing, network destinations and traffic into clear evidence.

> **Source code is currently private.** This public repository contains product information, documentation and release materials, not application source.

![Aegiscope privacy evidence flow](assets/privacy-flow.svg)

*Concept diagram only; it does not represent live telemetry.*

## The idea

An individual file read or network connection can be ordinary. Aegiscope is being built to help users see when events form a sequence worth reviewing:

```
Application → sensitive repository history access → large local artifact
            → external connection → significant outbound traffic
            → explainable privacy evidence
```

Important findings distinguish:

- **Observed** — directly supported by available telemetry.
- **Inferred** — a cautious interpretation of observed events.
- **Unknown** — what the telemetry cannot prove, such as the contents of encrypted HTTPS traffic.

Aegiscope will not claim a file was uploaded unless evidence establishes that fact.

## Status

Aegiscope is in development; **no production monitoring build or installer has been released**. The private Windows development build collects process identity metadata, samples process and connection state, and offers opt-in TCP/UDP event-byte estimates. A 250 ms process-lifecycle scan supplements the one-second full inventory in the desktop profile; both can miss short-lived or inaccessible processes. Controlled packaged tests on one Windows 10 Enterprise build passed bounded external IPv4 HTTP, HTTPS and UDP DNS requests through the Agent, IPC and local SQLite. Those tests validate selected paths on one machine only. TCP/UDP event-byte estimates are not confirmed payload or delivery totals, and optional per-connection TCP counters were denied under the current validation token.

Sensitive paths are classified from metadata, including source-code and credential-related locations, but Aegiscope does not read secret contents. The opt-in file ETW pipeline has not produced validated live file-access records under the current test token. Protected-folder notifications provide post-notification size snapshots without identifying the writer. A DNS answer-IP match may appear as a possible name based on a short time window; it does not attribute a query to an application, and DNS-to-process attribution is unsupported. Windows 11, service-mode collection, broader remote traffic and sustained-load coverage remain unvalidated. Correlation keeps observed facts separate from inference and unknown payload contents. See the [detection capability matrix](docs/detection-capabilities.md) for exact limits.

## Principles

- Local analysis by default; no behavioral-history upload by default.
- Prefer metadata. Do not collect secret values, browser cookies, passwords or private-key contents.
- Explain the evidence and its limits.
- Summarize high-volume activity rather than flooding the interface.
- English default with Simplified Chinese in the same interface.

## Documentation

[Architecture](docs/architecture.md) · [Detection capabilities](docs/detection-capabilities.md) · [Privacy model](docs/privacy-model.md) · [Telemetry model](docs/telemetry-model.md) · [FAQ](docs/faq.md) · [Security](SECURITY.md) · [Privacy notice](PRIVACY.md) · [Binary software license notice](BINARY-EULA.md)

## Releases

No installer is available yet. A future Windows release will include version notes and a SHA-256 checksum. The application source will remain in a separate private repository unless announced otherwise.

## Community

Use the issue templates to report a bug, suggest a feature or report a false positive. Remove usernames, private paths, tokens, repository names and other personal data before attaching logs or screenshots.

## License

This repository's materials do not license the Aegiscope application. The official downloadable/installed binary will be governed by [BINARY-EULA.md](BINARY-EULA.md), whose final terms must be published before distribution. There is intentionally no generic `LICENSE` that could imply the closed-source software is open source.

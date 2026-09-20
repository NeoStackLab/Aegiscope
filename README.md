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

Aegiscope is in **Phase 0: repository and architecture foundation**. No production monitoring build or installer is published. See the [detection capability matrix](docs/detection-capabilities.md).

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

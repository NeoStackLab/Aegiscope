# Architecture Overview

Aegiscope is planned as a Windows desktop application with a strict boundary between presentation and monitoring.

```
React renderer
    ↓ validated, allowlisted IPC
Electron main
    ↓ typed local protocol
Rust monitoring agent
    ↓
platform adapter → normalized events → correlation/evidence → SQLite
```

The Rust domain and correlation logic are independent of Electron. Windows collection belongs behind a platform adapter so future systems can map their observations into the same domain vocabulary.

A future service process may keep monitoring active while the desktop window is closed; it is not part of Phase 0. No kernel driver is planned for the foundation. Any low-level component would require a demonstrated capability gap and safety review.

The renderer is treated as potentially compromised. It receives only screen-specific data and cannot invoke arbitrary shell commands or collector operations. Production implementation details remain private.

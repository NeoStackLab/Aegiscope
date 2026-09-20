# Detection Capability Matrix

**Status: Phase 0.** No production monitoring collector is implemented. Planned mechanisms are investigation candidates, not supported product features.

| Capability | Current status | Boundary |
|---|---|---|
| Process start/stop and parent-child relationships | UNSUPPORTED | Domain design only; no collector. |
| Publisher, signature, hash and version | UNSUPPORTED | Not collected or validated. |
| Sensitive file access attribution | UNSUPPORTED | No collector. Windows audit events require suitable audit policy and object SACLs. |
| Git history mass access | UNSUPPORTED | Classifier and aggregation are design only. |
| Secret-value inspection | UNSUPPORTED | Intentionally excluded; intended model is metadata/path classification. |
| Network endpoint by process | UNSUPPORTED | No collector. WFP/ALE is an investigation candidate for connection authorization. |
| Per-process uploaded/downloaded bytes | UNSUPPORTED | No validated implementation; system-wide counters cannot be presented as per-process counts. |
| DNS name mapping | UNSUPPORTED | No collector; DNS-to-connection attribution can be ambiguous. |
| Persistence changes | UNSUPPORTED | No registry, service, task or startup-folder watcher. |
| Camera/microphone access attribution | UNSUPPORTED | No general product event feed implemented for arbitrary desktop processes. |
| Clipboard or screen capture attribution | UNSUPPORTED | No reliable monitor implemented. |
| Correlated privacy alerts | UNSUPPORTED | Rule model only; no event pipeline. |
| Block network action | UNSUPPORTED | No enforcement component; UI must not show a working block action. |
| Exact contents of encrypted HTTPS payloads | UNSUPPORTED | Not visible from connection metadata; decryption is not planned. |

## Candidate mechanisms to validate

ETW is a documented framework for consuming provider-defined application and kernel events; fields and availability depend on provider, OS version, permissions and event schema. Windows Security file-access events may require audit policy and matching SACLs. WFP offers application-aware filtering at ALE layers, but this does not establish payload contents or a validated per-process byte counter.

Validate attribution, event loss, privilege needs, overhead and interaction with Windows Firewall/security products on supported Windows 10/11 builds before changing status.

References: [ETW overview](https://learn.microsoft.com/en-us/windows/win32/etw/event-tracing-portal), [WFP overview](https://learn.microsoft.com/en-us/windows/win32/fwp/about-windows-filtering-platform), [ALE](https://learn.microsoft.com/en-us/windows/win32/fwp/application-layer-enforcement--ale-), [file access auditing](https://learn.microsoft.com/en-us/windows-server/identity/solution-guides/plan-for-file-access-auditing), [Privacy policy CSP](https://learn.microsoft.com/en-us/windows/client-management/mdm/policy-csp-Privacy).

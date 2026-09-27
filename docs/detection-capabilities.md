# Detection Capability Matrix

**Status: Development, Phase 4 in progress.** No production monitoring build is released. Current private Windows development builds include sampled process inventory, TCP connection metadata, UDP local bindings and a default-off sensitive-file ETW pipeline. These are development capabilities, not a production monitoring guarantee; the file ETW path has not been validated against live Windows records.

| Capability | Current status | Boundary |
|---|---|---|
| Running process inventory, PID, parent PID, name and reported start time | PARTIAL | Private Windows development build samples with a user-mode process API every two seconds and caps the snapshot at 1,024 processes. A complete process audit trail is not claimed. |
| Process start/stop changes | PARTIAL | Inferred by comparing complete snapshots. Short-lived processes can be missed; validated transitions are retained locally for up to 30 days and 100,000 rows. |
| Publisher, signature, hash and version | PARTIAL | The private development build reads local version resources, checks embedded Authenticode signatures without online revocation lookup, and hashes bounded local executable files. Protected paths and inaccessible, oversized or changing files can remain unavailable. Live Windows compatibility and trust edge cases need more validation. |
| Sensitive file access attribution | PARTIAL | A default-off System IO ETW metadata pipeline is connected to settings, bounded local summaries and a Sensitive Data view. It does not read file contents and has not been validated with live ETW records; permissions, attribution, event loss and path coverage remain open. Windows audit events require suitable audit policy and object SACLs. |
| Git history mass access | PARTIAL | The private development build can classify and aggregate Git-history path metadata through the opt-in file pipeline. No live Windows ETW validation has been completed; it does not establish that file contents were consumed. |
| Secret-value inspection | UNSUPPORTED | Intentionally excluded; intended model is metadata/path classification. |
| Current IPv4/IPv6 TCP endpoint metadata by PID | PARTIAL | Private Windows development build samples IP Helper owner-PID tables every two seconds, omits listeners and caps display at 2,048 rows. It is not a connection audit trail and can miss short-lived connections. Process name/path is joined by PID and can be incomplete or stale. |
| Current IPv4/IPv6 UDP local endpoint metadata by PID | PARTIAL | The private development build samples IP Helper owner-PID tables every two seconds and caps display at 2,048 rows. Windows can report PID 0 when ownership is unavailable. These are local bindings only, not remote peers or proof of datagram traffic; live visibility needs validation. |
| UDP remote peer by process | UNSUPPORTED | The documented owner-PID UDP table reports a local endpoint, not a remote peer. |
| Per-process uploaded/downloaded bytes | UNSUPPORTED | Not collected. System-wide counters are not used as process totals. |
| DNS name mapping | UNSUPPORTED | No DNS collector or validated connection attribution. |
| Persistence changes | UNSUPPORTED | No registry, service, task or startup-folder watcher. |
| Camera/microphone access attribution | UNSUPPORTED | No general product event feed implemented for arbitrary desktop processes. |
| Clipboard or screen capture attribution | UNSUPPORTED | No reliable monitor implemented. |
| Sensitive file read followed by a newly observed TCP endpoint | PARTIAL | The private development build has one conservative, low-confidence temporal co-occurrence rule. Its opt-in file source has not been validated live; a first-observed endpoint is not proof that a connection began after a read, and the alert does not claim an upload or payload contents. |
| Git history → large artifact → remote endpoint → outbound traffic | PARTIAL | A development-only simulation runs a high-confidence synthetic benchmark through the correlation engine. Production telemetry does not yet provide validated large-artifact events or per-process traffic byte counts, so this high-risk rule cannot fire from live product telemetry. |
| Block network action | UNSUPPORTED | No enforcement component; UI must not show a working block action. |
| Exact contents of encrypted HTTPS payloads | UNSUPPORTED | Not visible from connection metadata; decryption is not planned. |

## Candidate mechanisms to validate

ETW is a documented framework for consuming provider-defined application and kernel events; fields and availability depend on provider, OS version, permissions and event schema. Windows Security file-access events may require audit policy and matching SACLs. WFP offers application-aware filtering at ALE layers, but this does not establish payload contents or a validated per-process byte counter.

Validate attribution, event loss, privilege needs, overhead and interaction with Windows Firewall/security products on supported Windows 10/11 builds before changing status.

References: [ETW overview](https://learn.microsoft.com/en-us/windows/win32/etw/event-tracing-portal), [WFP overview](https://learn.microsoft.com/en-us/windows/win32/fwp/about-windows-filtering-platform), [ALE](https://learn.microsoft.com/en-us/windows/win32/fwp/application-layer-enforcement--ale-), [file access auditing](https://learn.microsoft.com/en-us/windows-server/identity/solution-guides/plan-for-file-access-auditing), [Privacy policy CSP](https://learn.microsoft.com/en-us/windows/client-management/mdm/policy-csp-Privacy).

Network references: [GetExtendedTcpTable](https://learn.microsoft.com/en-us/windows/win32/api/iphlpapi/nf-iphlpapi-getextendedtcptable), [TCP owner-PID rows](https://learn.microsoft.com/en-us/windows/win32/api/tcpmib/ns-tcpmib-mib_tcprow_owner_pid), [UDP owner-PID rows](https://learn.microsoft.com/en-us/windows/win32/api/udpmib/ns-udpmib-mib_udprow_owner_pid).

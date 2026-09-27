# FAQ

## Is Aegiscope antivirus software?

No. It is being designed as an Application Privacy Observatory that explains app behavior and evidence limits.

## Is it available?

No production monitor or installer has been published. Private development builds contain sampled process and endpoint inventory plus a default-off file metadata pipeline that has not been validated against live Windows ETW records. See the [capability matrix](detection-capabilities.md) for coverage and limits.

## Is the source open?

No. **Source code is currently private.** This repository publishes product information and planned capabilities.

## Does Aegiscope upload my files or history?

There is no production collector yet. The intended default is local analysis without behavioral-history upload. Any future optional sharing must be documented and consent-based.

## Can it prove an app uploaded a particular file?

Not from ordinary encrypted connection metadata. Access and traffic should be reported separately; payload contents remain unknown unless direct evidence exists.

## Will it block applications?

Not in Phase 0. A block action appears only if actual enforcement is implemented and tested.

## Which languages are planned?

English is the default; Simplified Chinese uses the same interface and design.

## How do I report a false positive?

Use the false-positive template. Sanitize paths, usernames, domains and private data first.

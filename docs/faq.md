# FAQ

## Is Aegiscope antivirus software?

No. It is being designed as an Application Privacy Observatory that explains app behavior and evidence limits.

## Is it available?

No production monitor or installer has been published. Private development builds include sampled process and endpoint inventory, selected local persistence snapshots, optional elevated TCP byte counters, opt-in DNS query names, protected-folder notifications and a default-off file ETW pipeline. Several sources have not been validated in live product monitoring; see the [capability matrix](detection-capabilities.md) for exact coverage and limits.

## Is the source open?

No. **Source code is currently private.** This repository publishes product information and planned capabilities.

## Does Aegiscope upload my files or history?

No production build has been released. Private development builds perform their current analysis locally; behavioral history is not uploaded by default. Any future optional sharing must be documented and consent-based.

## Can it prove an app uploaded a particular file?

Not from ordinary encrypted connection metadata. Access and traffic should be reported separately; payload contents remain unknown unless direct evidence exists.

## Will it block applications?

No. Network blocking is not implemented, so the product does not offer a working block action.

## Which languages are planned?

English is the default; Simplified Chinese uses the same interface and design.

## How do I report a false positive?

Use the false-positive template. Sanitize paths, usernames, domains and private data first.

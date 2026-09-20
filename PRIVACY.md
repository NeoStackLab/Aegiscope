# Privacy Notice

Aegiscope is being designed as a local-first Application Privacy Observatory. This describes intended behavior, not a claim that Phase 0 currently monitors a device.

## Intended defaults

- Analysis and event storage remain on the Windows device.
- Process history, paths, repository names, browser activity, documents and network history are not uploaded by default.
- Passwords, API token values, SSH private-key contents, browser cookies and credential contents are not collected.
- Any future diagnostic sharing must be optional, clearly explained and reviewable before sending.

## Possible metadata

A future monitor may use metadata such as process identity, paths/categories, timestamps, endpoints and byte counts where Windows provides reliable attribution. Paths and domains can themselves be personal information. Users should control categories, protected locations and retention.

Phase 0 has no production collector. Before collection ships, this notice must state fields, storage, retention, deletion and optional transfer.

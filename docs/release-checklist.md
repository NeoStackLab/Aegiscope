# Public Release Checklist

No installer is currently published.

- [ ] Confirm tag, version and notes against the private build.
- [ ] Verify both remotes; confirm only product materials are in this repository.
- [ ] Review installer provenance and code-signing status.
- [ ] Calculate SHA-256 from the final installer and verify it after upload.
- [ ] Confirm trusted update metadata, version, checksum and signature validation before installation.
- [ ] Inspect GitHub-generated source archives: documentation/assets only.
- [ ] Scan public files for secrets, endpoints, certificates, debug databases, user telemetry, source archives and internal configuration.
- [ ] Confirm screenshots and fixtures contain no real user data and label prototypes/demos.
- [ ] Publish release notes, installer and checksum together.
- [ ] Record verification result and rollback contact.

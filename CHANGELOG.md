# Changelog

No production release has been published.

## Unreleased

- Created separate public product and private engineering repositories.
- Added Phase 0 product, privacy and capability documentation.
- Added a concept-only privacy evidence illustration.
- Added bug, feature and false-positive issue templates.
- Private Windows development builds now include opt-in, bounded FileIo ETW, DNS, TCP/UDP user-ETW event-byte estimates, selected persistence snapshots, local correlation and eleven deterministic simulation scenarios. These sources remain partial and have explicit permission/coverage limits in the capability matrix; no production binary is released.
- Latest packaged acceptance (2026-10-15) verifies all nine screens in both locales, local saved-rule persistence across Agent restart, and selected loopback plus external IPv4 TCP/UDP evidence through the packaged Agent, IPC and disposable SQLite profile on one Windows 10 host. This is unsigned development-package evidence; event-byte estimates do not prove payload contents or delivery, and it does not validate File ETW, Windows 11, service mode or the complete Git-to-network chain.
- Added metadata-only recognition of current Windows Azure CLI MSAL cache paths to the private development classifier. The application does not inspect or decrypt cache contents; see the capability matrix.

Future release entries will include user-visible changes, known limitations, installer filename and SHA-256 checksum.

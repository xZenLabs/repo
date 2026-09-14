# v0.2.0

Hey folks! 👋 This release focuses on making the `[Refresh Cloud]` workflow smoother, tightens up a proxy-detection edge case, and adds a much beefier test suite behind the scenes. Thanks for using RemoteLibrary!

### Added
- **`[Refresh Cloud]` action entry** — a pinned row in the file browser lets you trigger a rescan without leaving the folder view or opening the menu.
- **Slow-scan notification** — when the WebDAV server doesn't support a single-request scan, RemoteLibrary now tells you it's falling back to a slower per-folder scan instead of silently taking longer.

### Fixed
- `[Refresh Cloud]` entry no longer crashes CoverBrowser (missing path) and now shows a friendly label there too.
- Reload dialog now paints before scanning starts, instead of appearing to hang.
- Proxy entries are now tagged with a `[Cloud]` suffix rather than a prefix, for consistent sorting/display.
- BookInfo/BookInfoManager proxy checks now require a real remote-map match, preventing false positives.

### Internal
- Added an end-to-end test harness that runs against a real WebDAV server, plus broader unit test coverage (reload/download failure modes, monkeypatch extensions, select-mode guards).
- Extracted scanner, provider-resolution, and remote-map lookup logic into their own modules; added a shared monkeypatch-install helper.
- Added CI workflows for tests and releases.
- Overhauled the README.

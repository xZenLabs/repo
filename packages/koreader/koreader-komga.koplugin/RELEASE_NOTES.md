# v2026.08.31.1 · 2026-08-31


### Fixed
- Large chapters (150 MB+) no longer fail on slow connections: downloads had a hard
  60-second total cap (KOReader's default), which killed every attempt (retries
  included) before big files could finish. There is now no total time limit by
  default; a stalled transfer (no data for 15 s) is still aborted and retried.

### Added
- **Komga → Settings → Download timeouts**: configure the stall timeout and an
  optional total time limit per download. Leave both empty for the defaults
  (15 s stall, no total limit).


### Commits
9b3e5e3 release: v2026.08.31.1
8485847 fix: no total download timeout by default; configurable timeouts in Settings

# v2026.08.31 · 2026-08-31


### Added
- Custom download folder, filename template, and per-series subfolder toggle, under
  **Komga → Settings** (#3). Templates combine `{series}`, `{title}`, and `{number}`
  (e.g. `{series}-{title}-{number}`); the default keeps the current `0001.cbz` names.

### Fixed
- Downloads and browsing now survive unstable connections (e.g. Kindle +
  Tailscale behind an HTTP proxy): transient failures (transport errors, 5xx,
  truncated responses) are retried up to 4 times with exponential backoff.
  Each retry shows an "attempt X of Y" notice that can be tapped to cancel,
  and partial files are removed before every retry.


### Commits
19c46d3 test: stub readerui for the path-chooser spec instead of loading FileManager
5bec305 release: v2026.08.31
2f3a249 feat: download-folder dialog with home default; refresh screenshots and docs
c5bb088 feat: custom download folder, filename template, per-series subfolder toggle
fdb48d5 feat(core): retry transient failures across the API on flaky connections
32543c1 docs: note plaintext API-key storage and its scope
80abd8b refactor(views): decompose the chapter picker onto pure modules; UX & i18n fixes
d41ba02 refactor(core): pure domain/API modules + robust, deterministic download pipeline

# v2026.06.22 · 2026-06-22


First public release.

### Added
- Connect to a Komga server with a base URL and API key, configured from
  **Komga → Settings** inside KOReader.
- Home hub with six ways to browse the library: **Reading** (books in progress),
  **Deck** (on deck), **Last Updated**, **Last Added Series**, **Collections**,
  and **All** (search the whole library by title).
- Series browser with a multi-select chapter picker: pick any combination of
  chapters and bulk-download them in one action.
- Downloads saved into per-series folders, so each series stays self-contained on
  the device.
- Reading progress syncs back to Komga through KOReader's own sync, no extra setup.
- UI strings reuse KOReader's existing translation catalog, so the plugin inherits
  KOReader's translations in every language it already supports (no catalog shipped).
- CalVer versioning with the source of truth in `_meta.lua`.
- Tag-based release pipeline that builds the installable `komga.koplugin/` zip and
  publishes the GitHub Release, gated on the full KOReader-frontend e2e suite.

### Commits
b1a766a ci: fix unit lua version and koreader-base cache key
6498c73 release: v2026.06.22
f118ff0 docs: short README + MkDocs documentation site with screenshots
d2551d9 feat: finalize i18n, comprehensive e2e suite, and release gating
f4e089d ci: CI workflows and CalVer release pipeline
5929b76 test: KOReader frontend integration harness
5faf908 test: unit tests and dev tooling (busted, luacheck, Makefile)
a3b6227 feat: browser UI and plugin entry point
8522d9d feat: Komga API client and response parsing
e9589e4 feat: core download logic and helpers
3eb5ae4 chore: add AGPL-3.0 license and .gitignore

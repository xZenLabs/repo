# v1.2.5 · 2026-11-12

## [v1.2.5] — 2026-11-12

### Fixed
- **Syncthing failed to start on firmware without a usable `nice`. **
  `start-syncthing` always ran `setsid nice -n 10 syncthing …`, so a firmware
  without a working `nice` (reported on Kobo software 6.0 beta, #11) aborted the
  launch. The launcher no longer wraps Syncthing in `nice`: Syncthing lowers its
  own priority at startup (`setLowPriority`, on by default; its worker process
  was measured at niceness 11, against 10 with the old `nice` wrapper). If
  `setLowPriority` is turned off in Syncthing, it now runs at normal priority.


**Full Changelog**: https://github.com/d0nizam/kosyncthing_plus.koplugin/compare/v1.2.4...v1.2.5

# v1.2.4 · 2026-11-08

## [v1.2.4] — 2026-11-08

### Fixed
- **Android remote mode could not connect while "Use HTTPS for GUI" was
  enabled.** The dialog only said "Could not connect", although the API key and
  port were correct. The TLS handshake succeeds, but on some KOReader/Android
  builds `ssl.https.request` rejects the connection with "hostname does not
  match certificate" even with `verify="none"`: Syncthing's generated GUI
  certificate has the CN `syncthing`, never `127.0.0.1`. The request now builds
  the TLS connection with `ssl.wrap` and lets `socket.http` parse the response,
  skipping only the hostname check. This is safe because the URL is always
  `https://127.0.0.1:<port>`; authentication stays the API key.
- **An http probe no longer "succeeds" through Syncthing's redirect.** On a TLS
  GUI, Syncthing answers plain http with `307` to https; following it could make
  the http probe pass and save the wrong scheme. Redirects are no longer
  followed.
- **A pasted API key with a trailing newline no longer breaks the request.**
  Whitespace is now stripped from the key (Syncthing answered such a request
  with `400`).

### Changed
- **The "Could not connect" dialog now shows why**, per scheme (for example
  `https: HTTP/1.1 403 Forbidden` or `https: request failed: connection
  refused`), and stays on screen longer.

**Full Changelog**: https://github.com/d0nizam/kosyncthing_plus.koplugin/compare/v1.2.3...v1.2.4

# v1.2.3 · 2026-11-01

## What's Changed
* Remove legacy support by @d0nizam in https://github.com/d0nizam/kosyncthing_plus.koplugin/pull/9


**Full Changelog**: https://github.com/d0nizam/kosyncthing_plus.koplugin/compare/v1.2.2...v1.2.3

# v1.2.2 · 2026-07-31

## What's Changed
* fix: use POSIX arithmetic in start-syncthing by @Philantrop in https://github.com/d0nizam/kosyncthing_plus.koplugin/pull/8

## New Contributors
* @Philantrop made their first contribution in https://github.com/d0nizam/kosyncthing_plus.koplugin/pull/8

**Full Changelog**: https://github.com/d0nizam/kosyncthing_plus.koplugin/compare/v1.2.1...v1.2.2

# v1.2.1 · 2026-07-23

## [v1.2.1] — 2026-07-23

### Fixed
- **Downloading the legacy binary could fail with "did not contain a valid Linux
  Syncthing binary".** A release archive holds three entries named `syncthing`,
  and the plugin picked whichever the filesystem happened to list first —
  sometimes one of the two helper scripts, which was then correctly rejected as
  not an executable. The legacy download was affected on every device; the
  ordinary binary update only when it fell back from system `tar`. The
  executable is now selected by its path inside the archive and extracted on its
  own. Verified against the v1.2.2, v1.27.12 and v2.x archives.
- **The old-kernel notice reappeared on almost every wake.** The hint pointing
  at Legacy mode was meant to show once, but nothing recorded that it had been
  shown, and `init()` runs on every plugin instantiation — each FileManager to
  Reader transition, and after resume. On an old-kernel device it therefore
  returned indefinitely, and being a delayed pop-up it landed on top of whatever
  was drawing at the time, including lock-screen plugins. It is now shown at
  most once, recorded only when it is actually displayed, and cleared by a
  factory reset. The standing information stays in the menu, which marks
  *Legacy Syncthing* whenever the kernel needs it.

### Changed
- Binary extraction now also falls back to system `tar` if `ffi/archiver` is
  unavailable, which keeps the legacy download working on older KOReader builds
  — the devices most likely to need it.
- Extraction failures now report the underlying reason, so a failed download can
  be diagnosed from the message instead of guessed at.

## What's Changed
* Enhance binary extraction by @d0nizam in https://github.com/d0nizam/kosyncthing_plus.koplugin/pull/6


**Full Changelog**: https://github.com/d0nizam/kosyncthing_plus.koplugin/compare/v1.2.0...v1.2.1

# v1.2.6 · 2026-11-13

## [v1.2.6] — 2026-11-13

### Fixed
- Fresh installations failed to generate the Syncthing configuration with Syncthing 2.x. The launcher passed --no-default-folder to syncthing generate, but this flag was removed in Syncthing 2.0. Since the launcher only generates the configuration when config.xml is missing, existing installations were unaffected. Removed the obsolete flag; Syncthing 2.x no longer creates a default folder on first startup.

**Full Changelog**: https://github.com/d0nizam/kosyncthing_plus.koplugin/compare/v1.2.5...v1.2.6

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

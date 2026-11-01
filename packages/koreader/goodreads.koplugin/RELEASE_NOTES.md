# v0.5.0 · 2026-11-01


### Added
- **Waiting to sync** in Settings: list queued progress/status updates, **Sync now**, **Retry failed**, **Clear failed**. Failed items stay after a few attempts instead of vanishing.
- Progress POST that still returns **404** after a CSRF refresh adds the book to
  **Currently reading** and retries once (unshelved book).
- Warning when auto-track opens a book whose exclusive shelf on the site is not
  Currently reading, with a one-tap fix.

### Changed
- Queue flush sends a few POSTs per pass so a long burst cannot freeze the reader;
  the rest drain on a timer. Sync and flush do not run at the same time.
- Background work after a Wi-Fi wait ignores the document if that book was closed
  or replaced.

### Fixed
- **Status removed** is no longer radio-selected when a linked book simply has no
  exclusive shelf yet (empty ≠ destroy).
- Finished / status toasts no longer fire twice after Book Status + returning to
  the file manager (Reader and FileManager both received the same event).

# v0.4.0 · 2026-09-24


### Added
- **Test connection** in Settings: `GET /review/list` checks that cookies still
  work and names WAF / expired session instead of a generic network error.
- Offline queue for progress and status. Automatic sync never turns Wi‑Fi on;
  queued writes flush when the device is online again (reconnect or Test
  connection). Closing a book while offline keeps the last percent.

### Changed
- CSRF is fetched from **`GET /review/list`** first (classic Rails, less WAF
  than the homepage). `GET /` is only a fallback.
- Progress POSTs send `authenticity_token` in the form body as well as
  `X-CSRF-Token`.
- Menu actions follow KOReader Network → Wi‑Fi enable action. Background
  auto-track / autolink do not toggle the radio.
- No Goodreads requests until session cookies are saved (no error spam on
  first open).

# v0.3.1 · 2026-09-14


### Fixed
- AWS WAF **HTTP 202** (`x-amzn-waf-action: challenge`) is no longer shown as
  “Network error: 202”. The plugin asks to refresh cookies, including
  `aws-waf-token`, the same way as an expired session.

# v0.3.0 · 2026-09-01


### Fixed
- Stale CSRF: cookie rotation now drops the cached token, and a POST that
  returns **404** (Goodreads’ usual response for a dead authenticity_token)
  retries once after `GET /`. Failed progress posts are throttled so they
  do not fire on every page turn.

# v0.2.0 · 2026-08-28


### Added
- Menu item **Update progress: N%** (and a gesture) to post the current percent
  to Goodreads on demand. Independent of auto-tracking and of **Sync reading
  progress**. Want to read is switched to Currently reading; Finished / DNF /
  ~100% still go through Change status.

### Fixed
- Switching to a custom exclusive shelf (e.g. Paused) no longer leaves a
  leftover Finished/DNF/`-2` in sidecar `status`. Lua omits `status = nil`;
  the write now UNSETs it. Update progress trusts `shelf` when it is set.
- Auto-track sets **Currently reading** as soon as the book is linked (and on
  the first pages). It no longer waits for 1% progress, so a
  new book is not left unshelved after autolink.
- After Kobo resume, do not show a blocking “no network” dialog while Wi-Fi
  is up but DHCP has not finished. Background sync waits for a real
  connection and retries once; a leftover network error is a 3s toast.

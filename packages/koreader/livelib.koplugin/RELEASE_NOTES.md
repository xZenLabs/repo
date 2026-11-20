# v0.7.2 · 2026-11-20


### Fixed
- No more **Livelib: No network connection** dialog when the device wakes with Wi‑Fi
  off or while the radio has no IP yet (auto-tracking waits for connectivity;
  background sync uses quiet API).

# v0.7.1 · 2026-11-01


### Fixed
- Finished / status toasts no longer fire twice after Book Status + returning to
  the file manager (Reader and FileManager both received the same event).
- Background work after a Wi-Fi wait does not use the document if that book was
  closed or replaced.

# v0.7.0 · 2026-09-27


### Added
- Offline quote queue: **Send to Livelib** without Wi-Fi stores the highlight in plugin settings and posts it on **Network connected** (or after cookies are saved). Each quote is kept separately (not coalesced).

# v0.6.0 · 2026-09-25


### Added
- Send a highlight to Livelib as a quote: **Send to Livelib** in the highlight dialog (linked books only). Uses the classic `/quote/save/{edition_id}` multipart endpoint (even if Beta API is on).

# v0.5.0 · 2026-09-24


### Added
- Autolink by Calibre/OPF identifiers `livelib` (`{id}-{slug}`) and `livelib-edition` (`{id}`): on open and from **Link book…** (on by default, same UX as Goodreads).
- Setting **Autolink by LIVELIB identifier**.

### Fixed
- Search results no longer crash on first paint: cover placeholders used an empty `CenterContainer` (`paintTo` on nil).

# v0.7.0


### Added
- Offline quote queue: **Send to Livelib** without Wi-Fi stores the highlight in plugin settings and posts it on **Network connected** (or after cookies are saved). Each quote is kept separately (not coalesced).

# v0.6.0


### Added
- Send a highlight to Livelib as a quote: **Send to Livelib** in the highlight dialog (linked books only). Uses the classic `/quote/save/{edition_id}` multipart endpoint (even if Beta API is on).

# v0.5.0


### Added
- Autolink by Calibre/OPF identifiers `livelib` (`{id}-{slug}`) and `livelib-edition` (`{id}`): on open and from **Link book…** (on by default, same UX as Goodreads).
- Setting **Autolink by LIVELIB identifier**.

### Fixed
- Search results no longer crash on first paint: cover placeholders used an empty `CenterContainer` (`paintTo` on nil).

# v0.4.0


### Added
- Search results show covers in a left slot; they load in the background after the list is shown (Hardcover-style, via Trapper subprocess so the UI stays usable).
- Author names in search results are **bold**.

### Changed
- Search results keep KOReader `Menu` chrome (title bar, back, paging, search icon) with custom rows for covers and author styling.
- Search results are a centered dialog (not fullscreen), with table-style separator lines between rows.

### Fixed
- Auto-track sets **Currently reading** as soon as the book is linked (and on the first pages). It no longer waits for 1% progress. Opening an unlinked book no longer burns the 2s ensure before search/link finishes.

# v0.3.4


### Fixed
- Auto-track sets **Currently reading** as soon as the book is linked (and on the first pages). It no longer waits for 1% progress.
  Opening an unlinked book no longer burns the 2s ensure before search/link finishes.

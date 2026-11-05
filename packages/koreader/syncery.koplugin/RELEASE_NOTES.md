# v1.2.5 · 2026-11-05

## What's Changed
* Fix cloud reachability after DDNS IP changes by @giubba88 in https://github.com/d0nizam/syncery.koplugin/pull/26

## New Contributors
* @giubba88 made their first contribution in https://github.com/d0nizam/syncery.koplugin/pull/26

**Full Changelog**: https://github.com/d0nizam/syncery.koplugin/compare/v1.2.4.1...v1.2.5

# v1.2.4.1 · 2026-08-19

## [v1.2.4.1] — 2026-08-19

## What's Changed
* i18n: Russian (ru) translation by @iav in https://github.com/d0nizam/syncery.koplugin/pull/23


**Full Changelog**: https://github.com/d0nizam/syncery.koplugin/compare/v1.2.4...v1.2.4.1

# v1.2.4 · 2026-08-14

## [v1.2.4] — 2026-08-14

### Fixed
- Cloud credentials now execute only through a private, session-scoped server
  copy. Dropbox access-token mutation can no longer overwrite Syncery or Cloud
  storage+ settings, and one bounded runtime is reused across Sync All instead
  of refreshing OAuth once per book.
- Cloud destinations selected below an account root now match the live server
  by routing identity (`type`, `name`, `address`) while preserving the selected
  folder as the runtime `url` override.
- Manifest listing, upload, download, and prefetch now use a narrow Cloud I/O
  facade that brackets `provider.base`, restores `show_unsupported`, validates
  remote Syncery filenames, and keeps raw provider objects out of sync logic.
- Reading Statistics and Vocabulary Builder now receive a pristine Dropbox
  refresh-token descriptor immediately before every periodic or manual DB sync.
  KOReader's in-place access-token mutation is no longer persisted and reused
  after expiry; repairing credentials for the same destination preserves the
  existing three-way-merge `.sync` state.

## What's Changed
* Dropbox fix by @d0nizam in https://github.com/d0nizam/syncery.koplugin/pull/22


**Full Changelog**: https://github.com/d0nizam/syncery.koplugin/compare/v1.2.3...v1.2.4

# v1.2.3 · 2026-07-24

## [v1.2.3] — 2026-07-24

### Changed
- **The "point out this book" prompts now say *which* book they mean.**
  When migrating storage modes, Syncery picks the book it wants you to
  locate — so it now names it ("Can't find *Title*. Point it out…")
  instead of asking you to point out one of N unnamed books and leaving
  you to guess. The "that file doesn't match" message names the book too,
  in every place the picker is used, since by then you've been through a
  file browser and the title is no longer on screen. Where *you* picked
  the book a moment earlier (Progress Browser, Annotation Browser), the
  opening prompt is unchanged — repeating the title there would just be
  noise.

# v1.2.2 · 2026-07-23

## [v1.2.2] — 2026-07-23

### Added
- **"Continue reading" in the Progress Browser.** Picking a book you don't
  currently have open now also offers to jump back to where *this* device
  itself last left off, alongside the existing per-device jumps. It covers
  the case where a book's local reading position was reset but its synced
  record wasn't — most often after deleting a book and downloading it again
  (reported in issue #16). Deliberately limited to books that aren't open:
  once a book is open, the live session overwrites that record, so there
  would be nothing left to return to.

**Full Changelog**: https://github.com/d0nizam/syncery.koplugin/compare/v1.2.1...v1.2.2

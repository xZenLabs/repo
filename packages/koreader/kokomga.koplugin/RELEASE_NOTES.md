# 3.2.0 · 2026-11-09

### Added
- **Per-Library Download Subfolders** ([#16](https://github.com/JimDBh/kokomga.koplugin/issues/16)):
  - New option (**Downloads & Storage → Separate Libraries into Subfolders**, off by default) that places downloaded books into a subfolder named after their Komga library (`<Download Dir>/<Library Name>/...`), combining cleanly with **Download into Series Subfolders** when both are enabled.
- **Only List Writers as Authors** ([#15](https://github.com/JimDBh/kokomga.koplugin/issues/15)):
  - New option (**Display & Appearance → Only list writers as authors**, off by default) that takes a book's author from Komga's Writer role only, instead of every role (penciller, inker, colorist, letterer, cover, editor, translator…). A book with no writer still shows all its authors. Applies to downloaded books' metadata, the browser's list view and Bookshelf; books downloaded before the change keep their author until downloaded again.

### Changed
- **Re-designed Settings Menu**:
  - Re-organized the plugin menu into logical submenus: **Komga Browser**, **Manual Match / Unlink Current Book** (when a document is open), **Server Setup**, **Downloads & Storage**, **Sync & Reading**, **Display & Appearance**, and **Cache**.
- A person credited in several roles is listed once as an author, not once per role.

### Fixed
- **Bookshelf Integration**:
  - Fixed badge and progress bar incoherence on Komga shelves where downloaded books lost their Komga source identity, causing page-count pills to overwrite the downloaded tick badge and local metadata refreshes to clobber Komga reading progress and series badges.
  - Reconciled Komga `readProgress` with local KOReader `.sdr` sidecars for downloaded books, updated cached shelf records immediately when progress is pushed or a document closes, and stopped unread books from showing a `0%` progress bar.
  - Removed conflicting book-level reading status badges from series folder cards.

# 3.1.0 · 2026-10-15

### Changed
- **Bookshelf Integration**:
  - Komga now joins [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) through its official shelf source API instead of hooking into Bookshelf's internals, so Komga shelves keep working across Bookshelf updates. Requires Bookshelf v5.4.0 or later; with an older Bookshelf, Komga shelves don't appear.
  - Komga's list, sort and filters are now set in Bookshelf's shelf editor (long-press a Komga shelf), where its "Server order" would be. Picking Komga as a shelf's source just asks which list to show.
  - Add Komga shelves from Bookshelf's shelf editor (**Source / grouping → Komga**). **Options → Add Komga Shelf to Bookshelf** has been removed.
  - Series show their cover in the shelf's folder style, and their badge counts books read out of the total (e.g. 8/12), like a local folder's.
- **Fewer Notices**:
  - "Saved" is shown only when nothing opens the book afterwards (Download & Open, the next-chapter prompt and Bookshelf open it instead).
  - Bulk downloads show one notice when they start and one when they finish, instead of two per book. A failure still shows.
  - No "Updated" notice after changing a setting (the menu shows the new value), and no "Checking server progress" notice before a manual pull's result.

### Fixed
- **Bookshelf Integration**:
  - A series or collection opened for the first time loads with its first page of covers behind one "Loading from Komga…" notice, instead of drawing empty, then without covers, then whole.
  - Returning from a book to a Komga series in Bookshelf no longer leaves the series empty.
  - Download & Open from a book's long-press dialog now opens the book once it has downloaded.

# 3.0.0 · 2026-09-25

### Added
- **Bookshelf Integration**:
  - Komga is now a shelf source in the [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) home screen plugin, showing All Series (default), Keep Reading, On Deck, Recently Read Series, Recently Added Series, Recently Added Books, One-Shots, or Collections. Add one from Bookshelf's shelf editor (**Source → Komga…**) or from **Options → Add Komga Shelf to Bookshelf**.
  - All Series pages from Komga as you browse, with Komga's sorting (title, recently added / updated / read, release date, book count) and filters (read status, library, publication status). Every other list can be filtered by read status. Each filter takes any combination of values.
  - Series and collections open as folders inside Bookshelf. Series show an unread / total badge when Bookshelf's folder badge is on, and fully read series are marked finished. Books show their Komga cover, summary (or their series' summary when a chapter has none), read state, and a tick once downloaded; tapping one that isn't downloaded offers to download it through kokomga, so progress sync and the next-chapter flow keep working.
  - Only book details and covers are fetched; pull down on a Komga shelf to refresh it from the server. Komga shelves display as covers.
- **Remove Finished Chapters**:
  - New option to keep only the last N chapters of a series (off by default). Moving to the next chapter quietly deletes older chapters of that series that are marked finished; their reading position, highlights, and notes are kept.
- **Localization (i18n)**:
  - Added Simplified Chinese, Traditional Chinese, Japanese, and Spanish translations for all new Bookshelf and chapter options.

### Changed
- **Offline Next-Chapter Transitions**:
  - kokomga now remembers each book's next book, so a downloaded next chapter opens at the end of a book even without a connection, and faster when online.
- **Komga Progress Option**:
  - "Use Komga server progress when available" now covers sending progress too, not only fetching it. When it is off, Komga books sync through KOReader's progress sync like any other book.

### Fixed
- **Progress Sync Error Message** (#13, thanks @PoebelPogge):
  - KOReader's progress sync now syncs a Komga book with Komga only, never with the KOSync server, where it failed with an error (e.g. HTTP 405) when that server isn't a KOSync server. KOReader still decides when to sync, connects to Wi-Fi for it (and disconnects again after a push on suspend), and reports the result. Komga books no longer need a KOSync account for this.

# 2.2.1 · 2026-09-24

Just fixed the version string in metadata.

# 2.2.0 · 2026-09-20

## [2.2.0] - 2026-09-20
### Added
- **Collections Browsing** (#9, thanks @Gunflame13):
  - Added a "Collections" entry to the home menu to browse Komga collections and drill into the series each one contains.
- **One-Shot Browsing** (#9, thanks @Gunflame13):
  - Added a "One-Shots" entry to the home menu listing every one-shot on the server, sorted alphabetically by displayed title.
  - Sorting is accent- and case-insensitive, and orders punctuation before digits before letters.
- **Disable Readest Sync for Komga Books**:
  - Added a setting (default off) that suppresses the Readest plugin's per-book sync for any book managed by kokomga, even when Readest auto-sync is enabled globally. Side-loaded books and Readest's own library-wide sync are unaffected.
- **Localization (i18n)**:
  - Added Simplified Chinese, Traditional Chinese, Japanese, and Spanish translations for all new collection, one-shot, and Readest options.

### Changed
- **One-Shot Download Location** (#9, thanks @Gunflame13):
  - One-shots now download to the root download folder instead of a per-series subfolder, since a one-shot's series contains only that book. One-shots downloaded before this change remain in their old series subfolder and are not migrated, so they may show as not downloaded.
- **Recently Added Books** (#9, thanks @Gunflame13):
  - Now sourced from Komga's `/api/v1/books/latest` endpoint instead of querying books sorted by creation date.
- **Home Menu Row Sizing** (#9, thanks @Gunflame13):
  - The home menu now sizes its rows to the number of entries it actually has, so the added entries stay on a single page, falling back to fewer rows on short screens.

### Fixed
- **Readest Cross-Document Progress Sync**:
  - Fixed the next chapter opening on its last page during automatic chapter transitions. The Readest plugin could apply the previous chapter's reading position to the newly opened chapter; because its apply path only moves forward and clamps an out-of-range page, every auto-advanced chapter jumped to the end, was marked finished, and pushed that position back to the Readest cloud.
  - Readest progress is now rejected when it arrives through a reader that is no longer the active one, or when both the file checksum and the page count disagree with the open document. Legitimate cross-device resumes are unaffected.
  - Readest's pending background pull and delayed push are now cancelled before switching documents.

# 3.0.0

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

# 2.2.1

Just fixed the version string in metadata.

# 2.2.0

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

# 2.1.0

### Added
- **Multi-Chapter Background Pre-Downloading**:
  - Configurable setting under options to auto-download the next N chapters/books in the background (setting to `0` disables it).
  - Runs sequentially in a background subprocess to avoid any UI lag or blocking during reading.
  - Added cooperative polling (1-second check interval) and standby lock management to prevent the device from entering sleep mode mid-download.
- **Skip End-of-Book Prompt**:
  - Added a setting to skip the end-of-book prompt and directly open the next book if it has already been pre-downloaded locally.
- **KOReader Action Registration**:
  - Registered the Komga Library Browser as a global KOReader action (`komga_browse`), enabling users to bind gesture shortcuts, key presses, or profiles to launch the browser directly from both the file manager and the reader.

### Fixed
- **Dispatcher Actions**:
  - Fixed the manual sync action (`komga_sync_now`) which had an incorrect `"none"` category and missing event method, ensuring it now correctly dispatches and triggers manual synchronization.
- **Home Screen Return Behavior**:
  - Aligned browser window stack properties and resolved settings menu stack retention to ensure closing the browser correctly returns to launcher/homescreen plugins (e.g. Simple UI) instead of showing the book file manager.

# 2.0.1

### Fixed
- **File Extension Handling**:
  - Fixed an issue where books ending with decimal volume or chapter numbers (e.g., `xxx-vol-12.5`) would be downloaded without their extensions, preventing KOReader from recognizing them.
  - Refined extension validation to check specifically for the expected extension when the media type is known, ensuring even mismatched metadata extensions are corrected (e.g., ensuring a `.cbz` file is always saved as `.cbz` even if named `.pdf` on the server).
  - Maintained general non-numeric extension validation for fallback cases when the media type is unknown.

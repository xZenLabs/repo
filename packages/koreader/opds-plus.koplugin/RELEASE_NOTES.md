# v1.3.1 · 2026-11-09

# OPDS Plus v1.3.1

A bug-fix release: you can now reach the rest of a long feed after jumping to the last page, downloads get a proper file extension and a sensible default folder, and each catalog page takes one request instead of two.

### Changed
- **One Request per Catalog Page**: Opening a catalog page used to ask the server for its headers and then for the page, so a server that builds the whole feed both times, like Calibre-Web, did the work twice. Each page is now a single request. A server that tags or dates its feeds answers "not modified" when the copy on the device is still current.

### Fixed
- **Rest of a Long Feed Unreachable**: Jumping to the last page with the end chevron or the page number dialog left the next page button greyed out, so the rest of a long feed, such as a Calibre-Web shelf, could only be reached by swiping. The next part of the feed is now fetched when you land there (Issue #100).
- **Downloads Without a File Extension**: A book whose download address had no extension, such as `/download/7`, or one KOReader can't open, such as `get.php`, was saved under that name and could not be opened. The extension of the chosen format is now added.
- **Download Folder When None Is Set**: Without a download folder chosen, books were saved to the last folder opened in the file browser, which on a first start is KOReader's hidden help folder. They now go to the home folder, as in KOReader's own OPDS browser.
- **Where to Set the Sync Folder**: Syncing without a sync folder now tells you where to set one: the menu at the top left of the list of catalogs, under **Set sync folder**.
- **Duplicate PDF Download Buttons**: A PDF link was sometimes added to a book twice, so the format list read "EPUB, PDF, PDF" and a book with a single PDF asked which format to download. This happened with arXiv's feeds.

### Notes
- If you never chose a download folder, new downloads now go to your home folder instead of the last folder you browsed. Tap **Choose folder** in the download dialog to pick another.

Full changelog:
https://github.com/greywolf1499/opds_plus.koplugin/blob/main/CHANGELOG.md

# v1.3.0 · 2026-11-09

# OPDS Plus v1.3.0

A feature release: custom HTTP headers for catalogs behind a gateway, series info, a default catalog, parallel cover downloads, keyboard and D-pad navigation and more, with fixes for covers after switching views and for books with several authors.

### Added
- **Custom HTTP Headers**: A catalog can send extra headers with its requests, such as the `CF-Access-Client-Id` and `CF-Access-Client-Secret` headers that a server behind Cloudflare Access (Zero Trust) asks for. Tap **Headers** when adding or editing a catalog and write one `Name: value` per line. They go with the catalog's feeds, covers, downloads and sync, and only to that catalog's own server. They are saved as plain text, like the password (Issue #94).
- **Series Info**: Books show their series and their number in it, such as "❖ Dune Chronicles #2", in list view and in the book info dialog. Read from the `SERIES:` line that Calibre and Calibre-Web put in the description, from `dc:series`, and from the collection metadata that Grimmory sends (Issue #70).
- **Description Saved with Downloads**: The description a catalog gives for a book is saved with the downloaded file as KOReader custom book metadata, so it shows in Book information. This covers single downloads, the download queue and sync. A description the book already has, or one you edited yourself, is never replaced (Issue #85).
- **Thumbnails on Navigation Entries**: Entries that only open a sub-catalog, such as a series in a comic server's feed, show their thumbnail in list and grid view when the server provides one (Issue #24).
- **Default Catalog**: Settings > Default Catalog picks the catalog that opens as soon as you browse catalogs. Back returns to the list of catalogs (Issue #89).
- **Parallel Cover Downloads**: Covers are downloaded in background processes, two at a time, so pages of covers fill in faster and a slow server no longer freezes the screen. Where a background process can't be started, covers are downloaded one at a time as before (PR #98).
- **Keyboard and D-pad Navigation**: Devices with hardware keys can browse without the touchscreen. Back walks up one catalog level, Home closes the browser, the D-pad moves the focus item by item (cell by cell in the grid), and Enter opens the focused item (PR #93).

### Changed
- Switching between list and grid view keeps you on the same item instead of reloading the catalog (PR #93).
- The page counter in the footer is KOReader's own button again (PR #93).
- Paging forward no longer asks the server for another page on every tap. The next page is requested when you are one screen from the end of what has been loaded (PR #92).

### Fixed
- Covers no longer turn into coloured noise after you switch between list and grid view and then page through or switch back.
- A book with more than one author lists all of them, such as "Robert Louis Stevenson, Lloyd Osbourne", in the list, the book info dialog and the file name, instead of only the last.

### Notes
- Parallel Cover Downloads, Thumbnails on Navigation Entries and Save Description with Downloads are on by default. Each can be turned off under Settings.
- A Force sync downloads books with several authors once more, under their new file names.

### Thanks
Special thanks to these contributors for their work in this release cycle:
- @iav (keyboard and D-pad navigation, switching views and fetching ahead, #92 and #93)
- @demrom (parallel cover downloads, #98)

Full changelog:
https://github.com/greywolf1499/opds_plus.koplugin/blob/main/CHANGELOG.md

# v1.2.1 · 2026-11-09

# OPDS Plus v1.2.1

A bug-fix release with cover cache, catalog compatibility and sync fixes since v1.2.0.

### Fixed
- Covers are cached on Kindle and other devices where KOReader runs from a relative directory (Issue #86, PR #87).
- Cached covers no longer miss and download again after LuaJIT switches from interpreted to compiled code (PR #97).
- Cover cache robustness: falls back to KOReader's data directory on versions without `getFullDataDir()`, creates relative cache directories in place, and writes covers atomically so an interrupted write cannot leave a truncated cover.
- Catalog URLs with a local hostname, such as `http://booktrove:8083/opds`, can be added (Issue #91, PR #95).
- Entries linked with the OPDS `crawlable` relation, like the Standard Ebooks "All Ebooks" feed, open instead of failing with "Cannot get catalog info from nil" (Issue #83).
- Listings no longer lose the entries after one with an empty `<content/>` tag (Issue #100).
- "Sync all catalogs" and "Force sync all catalogs" say when no catalog has "Sync catalog" ticked instead of reporting "Up to date!", and the gesture versions wait for the network like the menu entries (Issue #96).
- A sync that fails shows the error instead of leaving "Synchronizing lists…" on screen. Feeds with a link-less entry and Project Gutenberg style catalogs with a single-book sub-feed now sync (Issue #96).
- KOReader's plugin manager can delete OPDS Plus's settings and cover cache with "Disable plugin and delete settings" and "Delete plugin and settings". Downloaded books are kept (Issue #82).

### Changed
- Updated GitHub Actions dependencies for checkout and release publishing.

### Notes
- Covers cached by earlier versions are downloaded once more after updating, because the cache file naming changed.

### Thanks
Special thanks to these contributors for their work in this release cycle:
- @cardoso42 (Kindle cover cache, #87)
- @demrom (stable cover cache keys, #97)
- @439qi (local hostnames, #95)

Full changelog:
https://github.com/greywolf1499/opds_plus.koplugin/blob/main/CHANGELOG.md

# v1.2.0 · 2026-03-19

# OPDS Plus v1.2.0

This release includes merged PRs, issue resolutions, and new user-facing settings since v1.1.0.

> [!IMPORTANT]
> **Upgrade method for existing users:** This release is based on a complete plugin rewrite.
> To avoid stale files and update issues, **remove the old `opds_plus.koplugin` directory entirely**, then install the new release fresh.

### Added
- Book Info Dialog for at-a-glance book metadata with improved cover handling.
- Direct dispatcher actions for:
  - OPDS Plus: Sync all catalogs
  - OPDS Plus: Force sync all catalogs
- Cover pipeline improvements with disk-backed cache and lifecycle-safe image loading.
- New Cover Settings:
  - Prefer Large Covers (quality-first source selection)
  - Enable Cover Cache toggle
  - Advanced cache controls: max size, TTL, and manual cache clear

### Changed
- Refactored debug architecture to standardize logging through shared utilities.
- Extended state-manager usage across UI menu components.
- Removed obsolete/dead code and simplified some loader internals.
- Updated GitHub Actions dependencies for checkout and artifact workflows.

### Fixed
- Gesture registration failures (Issue #58).
- Duplicate PDF entries in results (Issue #57).
- Book info dialog stability issues, including filename capture timing and cover widget behavior.

### Thanks
Special thanks to these contributors for their work in this release cycle:
- Michael Cummings (@kodermike)
- Gavin Mogan (@halkeye)

### Documentation
- Added KOReader installation/upgrade path reference:
  https://github.com/koreader/koreader/wiki\#installationupgrading
- Updated README and CHANGELOG to cover major additions and settings for 1.2.0.

Full changelog:
https://github.com/greywolf1499/opds_plus.koplugin/blob/main/CHANGELOG.md

# v1.1.0 · 2025-11-18

# OPDS Plus v1.1.0 - Polish & Performance Release

This release focuses on polishing the user experience, fixing bugs discovered during real-world testing, and optimizing space utilization across all device sizes.

## 🎯 Highlights

### ✨ Better Text Display
- Titles and authors now show **ellipsis (…)** when truncated
- Smart word-aware truncation for cleaner breaks
- UTF-8 safe for international characters

### 📐 Optimized Layouts
- **List View**: Dynamically fits maximum items with minimal whitespace
- **Grid View**: Automatically maximizes rows based on screen height
- Works perfectly on small e-readers, tablets, and large desktop displays
- No more wasted space at the bottom of pages!

### 🐛 Bug Fixes
- Fixed release package containing nested directories
- Fixed crashes in Grid Layout and Border settings menus
- Fixed `%%` appearing in confirmation messages
- Fixed version display in About dialog
- Fixed text truncation crashes

### 🔧 Developer Features
- **Debug Mode Toggle**: Enable verbose logging when troubleshooting
- **Version Display**: Now shown in settings menu
- Cleaned up excessive logging for better performance

## 📦 Installation

1. Download `opds_plus.koplugin.zip` from assets below
2. Extract to your KOReader plugins directory:
   - **Linux/Mac**: `~/.config/koreader/plugins/`
   - **Android**: `/sdcard/koreader/plugins/`
   - **Kindle**: `/mnt/us/koreader/plugins/`
3. Restart KOReader
4. Access via: **File Manager → Menu → OPDS Plus Catalog**

## ⚙️ Settings

All settings accessible via: **OPDS Plus Catalog → Settings**

- **Display Mode**: Switch between List and Grid views
- **List View Settings**: Cover size presets (Compact/Regular/Large/Extra Large)
- **Grid View Settings**: Layout presets, borders, and styling
- **Font & Text**: Customize fonts, sizes, colors
- **Developer**: Toggle debug mode for troubleshooting

## 🔄 Upgrading from v1.0.0

Simply replace the plugin directory with the new version. All your settings and catalogs will be preserved.

## 🙏 Acknowledgments

Thanks to everyone (myself, so far) who tested v1.0.0 and provided feedback! This release addresses all reported issues and includes several UX improvements based on real-world usage.

---

**Full Changelog**: https://github.com/greywolf1499/opds_plus.koplugin/blob/main/CHANGELOG.md

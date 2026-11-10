# v1.4.0 · 2026-11-10

# OPDS Plus v1.4.0

OPDS Plus can now update itself: check for a new release, read what changed, and install it, or roll back, from **OPDS Plus Catalog → Settings → Updates**. Redirects are also handled safely for every request.

**Install this version by hand, as before.** From 1.4.0 on, OPDS Plus can update itself.

### Added
- **Updates from Within KOReader**: **OPDS Plus Catalog → Settings → Updates** has **Check for updates**, which shows the notes of a newer release and installs it after you tap **Install**. The download can be cancelled with a tap, and KOReader asks to restart once the new version is in place. **Skip this version** keeps the weekly check quiet about that release until a newer one comes out.
- **Weekly Update Check**: Once a week, when OPDS Plus is opened and the device is already online, it asks GitHub whether there is a newer release, and says so once with a short notice. It never turns Wi-Fi on, never installs anything by itself, and stays quiet when the check fails. Turn it off with **Automatic update check (weekly)**.
- **Roll Back**: The version an update replaced is kept, and **Roll back to previous version** puts it back. The newer one is kept in turn, so you can switch back.
- **Security Policy**: `SECURITY.md` explains how to report a vulnerability privately, and what OPDS Plus does and doesn't protect: saved passwords, catalog connections, and how updates are checked.

### Update Safety
- Updates come only from this repository's releases on GitHub, over HTTPS. The certificate is checked against KOReader's certificate bundle and must name the server it came from.
- The downloaded archive must match the size and SHA-256 checksum that GitHub publishes for it. Every file in it is checked before anything is unpacked, and the unpacked plugin must load and carry the version it claims before it replaces the installed one.
- The new version is unpacked next to the installed one and swapped in with two renames, so a failed update leaves the installed version as it was. A plugin folder that is a link or has a `.git` folder is treated as a development install and is not updated, unless you allow it in **Settings → Updates**.
- An update that needs a newer KOReader than yours is not installed.

### Changed
- **Release Archive**: The `opds_plus.koplugin.zip` of a release now holds only the files the plugin runs on. It no longer carries the repository's own files (`.gitignore`, `.luacheckrc`, `CONTRIBUTING.md` and `CODE_OF_CONDUCT.md`). It is built by `scripts/build_release.py`, and the tests run on the very archive that gets published.
- **Automated Tests**: A test suite that runs without KOReader (`scripts/test.sh`), and a check of the release archive, now run next to luacheck on every pull request and every push to `main`. See CONTRIBUTING.md.

### Fixed
- **Redirects**: A request that a server redirects is now followed by OPDS Plus itself instead of by KOReader's HTTP library, for catalog pages, covers, downloads, sync and Kavita page streaming. KOReader's library got four things wrong. A redirect to another place on the same server dropped the saved username and password, so a catalog page asked you to add credentials you had already saved, and covers and downloads were refused. A redirect to another server carried the catalog's custom headers (Issue #94), and the Kavita token, along with it; they now go only to the catalog's own server. A permanent redirect (HTTP 308) was not followed. And with "Use server filenames", looking up the name of a file whose download address redirects repeated the request as a full download instead of asking for the headers only, so the whole book could be fetched just to read its name.
- **Catalog Address Checks**: Adding or editing a catalog no longer turns down an address that is fine: one typed with an upper-case protocol such as `HTTPS://`, one whose host name has an underscore (common for Docker and NAS names), or one with an IPv6 address in brackets, though some servers may still turn away the request KOReader sends to an IPv6 address. Spaces around the address are dropped, since a pasted address often comes with one. A port that is not a number from 1 to 65535 is reported on the spot instead of failing later.
- **Editing a Catalog Keeps Its Sync Point**: Saving the edit dialog forgot where the last sync had stopped, so the next sync no longer said "Up to date!". It went through the whole feed again and ran into the books it had already downloaded. The sync point is kept now, unless you changed the address.
- **Sync File Types**: The file types to sync are matched without regard to case, so `EPUB, PDF` works, and so does a server whose links end in `.EPUB`. A field holding only spaces or commas filters nothing, instead of blocking every download.
- **Books Counted After a Sync**: When a sync came across books that were already on the device, the "books downloaded" message came out too low, by one for each of them.
- **Description Next to an Empty Content Tag**: A book entry with an empty `<content/>` tag as well as a `<summary>` showed no description. The summary is used now.
- **Search Without a Usable Description**: A catalog whose OpenSearch description can't be fetched or read no longer offers a search that only reloads the catalog.
- **Odd Feeds and Servers**: A character reference that is not a number, such as `&#xZZ;`, no longer fails the whole feed, and neither does a title that is an empty XHTML `<div/>`. A redirect without a `Location` header, from a faulty server or proxy, is reported like any other failed request instead of causing an error while opening a catalog or downloading a book. With "Use server filenames", a file name taken from a redirect no longer keeps the query string or the percent-escapes of the address, and a redirect to an address with no file name no longer gives a file called `.epub`. Downloading to a folder that can't be written to fails at once, with the reason, instead of after asking the server for the book.
- **Kavita Page Streaming**: When Kavita's reply to the progress request has no page number in it, page streaming starts from the first page instead of failing after the viewer has opened.

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

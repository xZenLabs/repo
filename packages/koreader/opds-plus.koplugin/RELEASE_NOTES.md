# v1.6.0 · 2026-11-11

**Update from within KOReader**: **OPDS Plus Catalog → Settings → Updates → Check for updates**, or install by hand.
Neighboring-cover prefetch and streaming progress writes are both **off by default**.
OAuth login and downloaded-book progress synchronization are not included.

### Added

- **Authentication Discovery**: Recognize OPDS authentication documents in protected responses or at a direct address, including advertised HTTP/Atom/OPDS 2 links. Show provider information, Basic field labels and unsupported-flow explanations in a scrollable viewer. Public catalogs keep their entries and offer an explicit information action. Linked discovery uses verified same-origin HTTPS without catalog credentials, custom headers or redirects. Existing Basic/self-signed catalogs are unchanged; OAuth login remains gated.
- **Opt-in Streaming Progress Sync**: A per-catalog **Sync streaming progress** option pulls and reconciles Kavita/Komga page-stream positions and coalesces changes to painted pages into background server writes. Ask on conflicts, honor rewinds, preserve pending local state across errors/close/suspend, and recheck before/after writes. Credentials, stream identity or page-count changes require fresh reconciliation. Explain provider completion/reset behavior and non-atomic server APIs before enabling. Downloaded books and generic streams remain outside this feature.
- **Neighboring Cover Prefetch**: An off-by-default Cover Settings option warms the disk cache for one neighboring display page while the current covers are ready and input is idle. It requires caching and parallel downloads, never decodes or draws speculative images, and cancels on navigation, dialogs and close. Thanks to @iav for the prefetch work proposed in issue #117.
- **User Guide**: The [wiki](https://github.com/greywolf1499/opds_plus.koplugin/wiki) explains installing and updating OPDS Plus, its views and settings, setting up Calibre-Web, Kavita and Komga, OPDS 2.0 catalogs, and what to do about each error message.

### Changed

- **Formatted Release Notes**: Render update notes with KOReader's native Markdown viewer, or its existing converter and HTML scroller on v2025.10. Preserve Install / Skip / Later, keyboard scrolling and complete long notes. If rendering fails, explain it and offer the original plain text; do not fetch remote images or open links in notes.
- **Cancellable Catalog Loading**: Fetch, parse and map catalogs in the background while keeping the current page visible. Tap or press a key to cancel without changing the listing or history. If background processes are unavailable, ask before loading in the foreground, where input will pause. Catalog caching, search and sequential feed-page fetching are preserved.
- **Screenshots**: The README shows the book details, the update dialog and an OPDS 2.0 catalog's shelves and facets, all taken from a mock catalog of public-domain classics.
- **Editor Diagnostics**: Add a reproducible LuaLS check with accurate Busted assertions and KOReader module resolution, without disabling production warnings.

### Fixed

- **Kavita Authentication Validation**: Reject malformed decoded API keys and progress tokens before they can become authentication-header values.
- **Kavita Feed Resume**: Normalize Kavita's zero-based feed cursor before showing the Resume page or opening the stream, including relative links behind reverse proxies. Keep completed chapters on their final page and leave standard PSE positions unchanged.
- **Authenticated Caches**: Partition feed validators and cached cover bytes by request authentication context, including credentials, their source origin and configured custom headers that redirects may use. Ignore old unscoped cover entries rather than showing another account's cached image. Keep same-context reuse and stale fallback; credentials are not written into cache names.
- **Catalog Credentials**: Keep usernames and passwords on their source catalog's scheme, host and port, including the first request to a feed link, cover, download or stream. Preserve destination-scoped custom headers and provider-owned tokens. Saved subcatalogs on another origin no longer inherit the source login. Older download-queue entries without a recorded origin withhold Basic credentials and explain how to re-add authenticated downloads.
- **Responsive Page Streaming**: Move image requests and fallback Kavita progress lookup into cancellable background workers. Keep the current image until its replacement is decoded; reject stale results and preserve painted-page progress on cancellation, failure, close and suspend. Bound requests with an overall watchdog and report unavailable workers instead of silently blocking in the foreground.
- **Streaming Resume**: Use standard PSE positions in both default stream actions and remember displayed pages locally, including rewinds. Validate page counts/choices and clamp stale positions; do not fetch page 1 before a resumed page or record failed/speculative requests. Use Kavita's read-only reader-image API rather than its progress-writing OPDS image endpoint. Keep up to 500 catalog/account-scoped local positions and flush on close/suspend; server synchronization requires the separate per-catalog opt-in.
- **Responsive Update Checks**: Move connectivity probes and release requests off the UI thread, retaining parent-side settings and notifications. Manual checks can be cancelled; automatic checks pass input through when interrupted and never wake Wi-Fi. Reject stale results, coalesce duplicate checks, bound stalled workers and cancel on suspend/close/install. Ask before any manual foreground fallback.
- **Series Descriptions**: Show a matching Calibre-style `SERIES:` metadata line only in the series field, not again in the description. Book details, download information and newly saved descriptions use the same cleanup. Keep rating/tags, prose, malformed or mismatched fields, and existing downloaded-book metadata unchanged.
- **Shared Cover Workers**: Visible and prefetched covers share a two-worker limit rather than starting two workers per batch. If subprocesses are unavailable, speculative warming is skipped instead of falling back to blocking network requests.
- **Decoded Cover Memory**: Keep an 8 MiB least-recently-used cover budget instead of retaining every visited page. Visible and dialog-borrowed images stay pinned, even when they exceed that budget. Release high-resolution dialog images and widget-scaled copies when their users close or are rebuilt.
- **Cover Loading and Keys**: Yield between cover decodes and widget updates, including cache hits and repeated cover URLs. Key and touch activity postpones expensive cover work without killing and restarting downloads. Thanks to @iav for the input-deferral work behind issue #117.
- **Closing Book Details**: Cancel a pending high-resolution cover when its dialog closes, instead of decoding it later or repainting a replacement dialog.
- **Invalid Book Addresses**: Empty download, cover and page-stream addresses report an error instead of crashing or opening a broken viewer. An invalid download address leaves any existing destination file untouched.
- **Update Validation**: If the staged version file becomes unreadable during validation, the update reports the failure and keeps the installed plugin instead of throwing a Lua error.
- **Kavita Resume**: Read complete JSON responses regardless of field order or network chunk boundaries. Invalid tokens and page numbers are reported without crashing, and generic page streams no longer attempt Kavita authentication.

# v1.5.0 · 2026-11-10

# OPDS Plus v1.5.0

OPDS Plus now reads OPDS 2.0 catalogs, such as Komga's, next to OPDS 1 ones, with nothing to set. Groups of books on a catalog's start page open as shelves, and the book details show the publisher, the publication date and the language.

**Update from within KOReader**: **OPDS Plus Catalog → Settings → Updates → Check for updates**, or install by hand as before.

### Added
- **OPDS 2.0 Catalogs**: Catalogs that serve OPDS 2.0 (JSON) feeds open like any other: navigation, groups, books with their authors, series, covers and downloads, facets, pagination and search. OPDS Plus tells the two formats apart by the feed itself, so there is nothing to set.
- **Shelves**: Groups of books that an OPDS 2.0 catalog shows on its start page without a link of their own (like the samples on test.opds.io) open as folders, next to the groups that have a link, with the number of books they hold. Search results that come only in such groups are still listed straight away.
- **More Book Details**: The book details dialog shows the publisher, the publication date and the language when the catalog gives them, from OPDS 2.0 feeds and from the Dublin Core elements of OPDS 1 feeds (Calibre-Web sends the language).

### Changed
- **Catalog Requests Ask for OPDS 2.0 First**: Catalog requests now say which formats OPDS Plus reads, OPDS 2.0 first and then OPDS 1, so a server that has both can send the newer one. A server that refuses such a request is asked again the old way, and a catalog's own **Accept** header (in its custom headers) still wins.
- **Clearer Message for a Web Page**: An address that leads to a web page (a login page, a web reader) now says that it is not an OPDS catalog, instead of showing an empty or broken list.

### Fixed
- Comic books that servers label `application/x-cbr`, `application/x-rar-compressed` or similar are offered for download as `.cbr`, and types with parameters (`application/epub+zip; charset=utf-8`) are recognized.

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

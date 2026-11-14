# v0.8.0 · 2026-11-14

Download up to **three loans at once** with **Download all**, and restart KOReader directly after a KOLibby update.

- Both **Download all** and **Download all on this card** now run up to three loans simultaneously. Each loan's EPUB resources or MP3 parts are downloaded sequentially.
- The progress dialog shows overall completion counts and progress for the active loans. Finished files are saved as each loan completes, and a failed title frees its slot so other loans can continue.
- **Cancel all** stops every active worker while keeping completed files and resumable resources. Retrying also recovers a completed file interrupted before its record was saved.
- Update completion now offers **Restart KOReader** and **Later**. On supported platforms the button restarts automatically; on Android and other platforms without automatic restart it closes KOReader so you can reopen it.
- Disconnecting KOLibby clears temporary credential handoffs left by interrupted batches. Workers omit unchanged credentials from these handoffs.

Validated with **236 portable tests**, **19 real-process concurrency checks on Android**, and **14 isolated Android update checks**. The restart button was also tapped in the Android emulator to confirm it closes the app. The concurrency and update checks use synthetic data; Kobo and Kindle still need hardware validation.

### Install

Use **Tools → KOLibby → Settings → Check for updates**, or extract **KOLibby-0.8.0.zip** below into KOReader's `plugins` folder, replacing the existing `KOLibby.koplugin` folder. Restart KOReader afterward. If updating from an older build, follow its existing restart instructions; the new restart button becomes available once this version is running.

Your Libby connection, settings and completed downloads are preserved. Use the attached plugin ZIP; GitHub's automatic source archives are for development.

# v0.7.2 · 2026-11-12

Fixes valid audiobook parts being reported as incomplete, including failures during **Download all**. Resolves [#1](https://github.com/kolibby/KOLibby.koplugin/issues/1).

Some complete MP3 responses have different byte counts from the publication manifest. KOLibby now validates the actual transfer instead of requiring an exact match to that estimate.

- Preserve HTTP transfer, MP3 frame and duration validation, and existing size limits.
- Record actual part sizes so interrupted downloads can reuse matching cached parts.
- Update progress totals to reflect actual downloaded sizes.

Validated with 223 portable tests, including a three-audiobook batch, resume and cache compatibility, and rejection of incomplete transfers or audio. Previously failing parts were also replayed successfully through validation and MP3 assembly, with independent size/duration checks.

### Install and retry

Use **Tools → KOLibby → Settings → Check for updates**, or extract **KOLibby-0.7.2.zip** below into KOReader's `plugins` folder, replacing the existing `KOLibby.koplugin` folder. Restart KOReader afterward, then run **Download all** again to retry unfinished loans.

Completed downloads are skipped, and matching cached parts are reused. Your Libby connection, settings and downloaded books are preserved.

Use the attached plugin ZIP; GitHub's automatic source archives are for development.

# v0.7.1 · 2026-11-09

Fixes a setup-code failure on Kindle and other installations where another KOReader plugin has already declared zlib's decompression functions.

- Prevent the `inflateInit2_` argument-type error from blocking Libby setup and compressed responses.
- Keep zlib usable by other plugins regardless of plugin load order.
- Expand regression checks to cover all four zlib stream functions and stream lifetime during garbage collection.

Validated with 214 portable tests and 204 compression/local HTTPS checks across three Kindle ARM runtimes in both plugin load orders. The original error was reproduced before the fix. Kindle validation used isolated user-mode ARM execution of KOReader 2026.07.1 binaries; hardware confirmation is still pending.

### Install

Use **Tools → KOLibby → Settings → Check for updates**, or extract **KOLibby-0.7.1.zip** into KOReader's `plugins` folder, replacing the existing `KOLibby.koplugin` folder. Restart KOReader afterward. Your Libby connection, settings and downloaded books are preserved.

Use the plugin ZIP; GitHub's automatic source archives are for development.

# v0.7.0 · 2026-11-08

KOLibby now integrates with [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin), and EPUB downloads include publisher descriptions when Libby supplies them.

- Add Bookshelf chips for **Loans** or **Holds**, across all library cards or one selected card.
- Browse cached covers and metadata, open downloaded EPUBs, and access KOLibby's download and available-hold borrowing controls from Bookshelf. Pull down to synchronize.
- Customize Bookshelf templates with `%kolibby_status`, `%kolibby_library` and `%kolibby_download`.
- Read publisher descriptions in EPUB metadata and in Bookshelf after download, with readable paragraphs and Unicode preserved.

Bookshelf is optional; KOLibby remains available under Tools. In a Bookshelf chip, choose **Source / grouping → KOLibby**, then select loans or holds and the library cards. Integration uses Bookshelf's Source API v1 and was tested with Bookshelf 6.3.3. See the [Bookshelf setup instructions](https://github.com/kolibby/KOLibby.koplugin#bookshelf-integration).

For an existing EPUB, choose **Download again / resume** to add its description. Existing files are not changed automatically, and Download all continues to skip completed downloads.

Validated with 214 portable tests, Android emulator integration checks and Clear7 device testing. Synthetic description EPUBs also pass EPUBCheck and Calibre metadata extraction.

### Install

Use **Tools → KOLibby → Settings → Check for updates**, or extract **KOLibby-0.7.0.zip** below into KOReader's `plugins` folder, replacing the existing `KOLibby.koplugin` folder. Restart KOReader afterward. Your Libby connection, settings and downloaded books are preserved.

Use the attached plugin ZIP; GitHub's automatic source archives are for development.

# v0.6.4 · 2026-11-08

Improves Kindle/Kobo portability and network diagnostics, with smoother background synchronization and download progress.

- Explain connection failures by cause, including DNS, timeouts, certificate problems and storage errors.
- Resolve relative KOReader data and download folders to absolute paths.
- Use FAT-compatible filenames for cached EPUB resources.
- Keep automatic synchronization and setup-code polling from being cancelled by page turns or other input.
- Reduce progress writes and refreshes on e-ink devices.
- Use KOReader-compatible TLS settings for Libby connections; GitHub update verification remains enabled. See the README's privacy section for details.

Validated with 184 portable tests and tested on Clear7 with KOReader for Android.

### Install

Use **Tools → KOLibby → Settings → Check for updates**, or extract **KOLibby-0.6.4.zip** below into KOReader's `plugins` folder, replacing the existing `KOLibby.koplugin` folder. Restart KOReader afterward. Connection settings and downloaded books are stored separately.

Use the attached plugin ZIP; GitHub's automatic source archives are for development.

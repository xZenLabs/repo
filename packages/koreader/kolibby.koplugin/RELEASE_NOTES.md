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

# v0.6.3 · 2026-11-08

Fixes KOLibby missing from the Tools menu on some KOReader installations, including reports from both manual and Storefront installs.

- Use KOReader's bundled filesystem module, with a fallback for older environments.
- Make the self-updater use the same filesystem backend.
- Add startup regression tests and verify menu registration and update installation in Android KOReader.

Thanks to the community for reporting the issue and sharing the fix.

### Installing the fix

If KOLibby is missing from your menu, download **KOLibby-0.6.3.zip** below, extract `KOLibby.koplugin` into KOReader's `plugins` folder, replacing the existing plugin folder, and restart KOReader. Your connection, settings and downloaded books are stored separately.

If your KOLibby menu already works, use **Tools → KOLibby → Settings → Check for updates**.

Use the plugin ZIP attached below; GitHub's automatic source archives are for development.

# v0.6.2 · 2026-11-07

KOLibby is a KOReader companion to the official Libby web, iOS and Android apps.

- Connect through Libby's device-copy flow and synchronize multiple library cards, loans and holds.
- Browse loans and holds with cover art, metadata and due dates.
- Download eligible ebooks as EPUBs and compatible audiobooks as a single MP3 with ID3v2.3 chapters, without re-encoding the audio.
- Use **Loans → Download all** to download eligible loans while skipping completed checkouts. Card-filtered Loans views limit the action to that card.
- Identify partner-library cards and their home card when that relationship is available.
- Borrow available holds and check for plugin updates from Settings.

### Install

Use **KOReader 2026.07.1 or newer**. Download `KOLibby-0.6.2.zip` below and extract it into KOReader's plugins directory so the path is `plugins/KOLibby.koplugin/main.lua`. Restart KOReader, then open **Tools → KOLibby**.

Android is the first tested platform. Kobo and Kindle still need hardware validation. Some fixed-layout EPUBs may not render correctly in KOReader, and PDF downloads are not supported.

See the [README](https://github.com/kolibby/KOLibby.koplugin/blob/v0.6.2/README.md) for setup and usage. A SHA-256 sidecar is provided for manual download verification.

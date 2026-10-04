# v1.3.0 · 2026-10-04

Suwayomi Client v1.3.0 adds Next chapter to KOReader's native finish flow and makes recent chapter discoveries easier to find in Library.

## Native Next chapter

At the end of a recognized Suwayomi chapter, the native finish popup now offers **Next chapter**. KOReader's configured automatic next-file action also follows Suwayomi chapter order, including when folder sorting is set to access or date.

- Select the next eligible chapter from the complete saved chapter list, respecting your saved scanlator filter. Completed chapters remain available for rereading.
- Verify the local archive before switching, then resume its native saved position. A missing or blocked successor keeps the current reader open with an explanation; Next never skips a missing successor or queues it for download.
- Use the saved list while offline. If it is stale, use **Refresh chapters** while connected to update it.
- Keep KOReader's normal completion settings, progress, and document-close behavior, including existing Auto-download and retention policies. **Go to Suwayomi** remains available in the reader menu.

## Library arrivals and unread counts

**Latest arrivals** is the default Library order. Rows now show **Server unread** and a **Found** date when known. Choose **Title** from the Library title menu for alphabetical order; the choice stays through category changes and refreshes during that Library session.

- Found dates describe server discovery, including imported older chapters. Arrival dates and server unread counts cover **all scanlators**; your reading filter still governs chapter selection.
- Server unread counts describe the server aggregate. Pending local read choices show **Sync pending** without changing that count or your local choices.
- Saved dates and counts remain available offline. Refreshing, retained information after failure, and a result that could not be saved have distinct status text.
- Older servers without arrival metadata retain a usable Library with Title ordering. Unknown dates and counts remain unknown.
- Library Refresh reloads known server information. It does not start source discovery or new downloads. Existing manga actions, first-unread reading, and saved-position resumption continue through their usual controls.

## Updating

### KOReader App Store

With the [KOReader App Store plugin](https://github.com/omer-faruq/appstore.koplugin), open **Tools > App Store**, select **Check plugin updates**, then **Check all updates**. Update `suwayomi.koplugin` and restart KOReader.

### Manual update

1. Download **`suwayomi.koplugin-v1.3.0.zip`** from the release assets, not GitHub's source archives.
2. Quit KOReader normally. Replace the existing `koreader/plugins/suwayomi.koplugin` folder, then relaunch. Keep your KOReader settings and downloaded chapters.

After updating, open **Search > Suwayomi**. Refresh Library while connected to load discovery dates/counts, and refresh chapter lists when needed for sequential navigation. Existing archives and reading progress are preserved.

**Full changelog:** [v1.2.1...v1.3.0](https://github.com/LK4D4/suwayomi.koplugin/compare/v1.2.1...v1.3.0)

# v1.2.1 · 2026-09-27

Suwayomi Client v1.2.1 fixes chapter browsing and read-state regressions affecting older downloads, makes failed verification saves recoverable, and adds selectable Browse layouts. Updating from v1.2.0 is recommended.

## Reliability fixes

- Restore download and Auto-download controls for current-server chapters when older, unassociated archives appear in the same list. Uncertain archives keep their safe local actions without gaining permission for server sync or deletion.
- Restore the full chapter list and **Refresh chapters** after **Go to Suwayomi** from older downloads, while retaining offline fallback and reading progress.
- Preserve explicit pending **Unread** choices over stale completed-file metadata, including when an archive's old path is missing or the download directory changes.
- Explain when archive verification finishes but its result cannot be saved. Release the occupied verification state and allow a safe explicit retry; uncertain storage remains protected instead of reporting false success.
- Explain expired chapter controls after a background refresh, including an ineffective **Auto-download Off**, and let you reopen current controls without replaying an old command.
- Return to **All manga** when Refresh confirms that the selected Library category was deleted.

## Browse layouts

Choose **List**, **Cover with text**, or **Cover only** from the Browse footer's view menu. The choice is saved, the visible manga stays in view when switching, and pagination continues across layouts. **List** remains the default.

## Updating

### KOReader App Store

With the [KOReader App Store plugin](https://github.com/omer-faruq/appstore.koplugin), open **Tools > App Store**, select **Check plugin updates**, then **Check all updates**. Update `suwayomi.koplugin` and restart KOReader.

### Manual update

1. Download **`suwayomi.koplugin-v1.2.1.zip`** from the release assets, not GitHub's source archives.
2. Quit KOReader normally. Replace the existing `koreader/plugins/suwayomi.koplugin` folder, then relaunch. Keep your KOReader settings and downloaded chapters.

After updating, open **Search > Suwayomi** while connected and refresh affected chapter lists. Existing local archives and reading progress are preserved. Unknown-origin archives do not acquire a server association merely by opening them.

Older queued jobs with an unknown server origin still cannot **Retry**. Use **Downloads > Clear failed**, reopen the manga on the intended server, and queue the chapter again. **Clear failed** removes failed jobs in bulk and keeps records linked to local archives.

**Full changelog:** [v1.2.0...v1.2.1](https://github.com/LK4D4/suwayomi.koplugin/compare/v1.2.0...v1.2.1)

# v1.2.0 · 2026-09-24

Suwayomi Client v1.2.0 adds saved Library and chapter lists for offline browsing, opens Library directly, and strengthens download and reading-state safety when connections change or saves fail.

## Highlights

### Browse and read offline

- Library and chapter lists save automatically as you browse. Saved lists appear immediately while the server refreshes; downloaded chapters open without waiting for the server.
- Keep browsing saved lists when the server is unavailable, without repeated background connection-error popups. Explicit **Refresh** and **Refresh chapters** still report failures, as do failed saves.
- Resume downloaded chapters with KOReader's saved reading progress and use **Go to Suwayomi** to return to their chapter list offline.
- Complete server results replace saved lists, including removed manga or chapters and empty results, without deleting downloaded files or reading progress.

### Reach Library faster

**Search > Suwayomi** now opens Library using your category-picker preference. The title-bar menu offers **Library** and **Suwayomi home**; Home keeps **Browse**, **Downloads**, **Sync**, and **Settings** available. Back from the Library root exits the plugin.

### Clearer download controls

Use **Download next** for a one-time batch or **Auto-download** to keep the first unread chapters available. **Delete after reading** and **Delete when marked read** name the separate cleanup settings. Download help explains their completion rules and limits. These controls affect device-local CBZ files.

## Reliability fixes

- Keep queued downloads, retries, and redownloads tied to their recorded server. Changing the connection cannot silently fetch a same-ID chapter from another server. Restore the original connection before retrying affected jobs.
- Keep pending read/unread changes tied to their verified server and preserve saved choices when a refresh or read-state save fails.
- Display successfully refreshed chapter lists even when later reconciliation cannot be saved. Report the storage error and preserve local archives and confirmed reading state.
- Preserve reading progress for local files whose server association is not yet verified, and repair offline chapter actions and unread shortcuts.

## Updating

### KOReader App Store

If you use the [KOReader App Store plugin](https://github.com/omer-faruq/appstore.koplugin), open **Tools > App Store**, select **Check plugin updates**, and run **Check all updates**. Select `suwayomi.koplugin`, update it, then restart KOReader.

### Manual update

1. Download **`suwayomi.koplugin-v1.2.0.zip`** from the assets below, not GitHub's source archives.
2. Quit KOReader normally. Replace the existing plugin folder under `koreader/plugins/`, then relaunch. Keep your KOReader settings and downloaded chapters.

After either update route, open **Search > Suwayomi** while connected and browse the manga you want available offline. Library and chapter lists build through normal browsing; this does not download chapter contents automatically.

If a chapter list has never been loaded, it may have no saved information. Recorded downloads can supply fallback rows. Recovered files with no known server connection offer **Open** and **Verify download**; server sync, downloading, and deletion remain unavailable for those rows.

If an older queued job reports an unknown server origin, **Retry** cannot resume it. Use **Downloads > Clear failed**, reopen the manga on the intended server, and queue the chapter again. **Clear failed** removes failed jobs in bulk and keeps records linked to local archives.

**Full changelog:** https://github.com/LK4D4/suwayomi.koplugin/compare/v1.1.1...v1.2.0

# v1.1.1 · 2026-09-10

Suwayomi Client v1.1.1 fixes a regression in v1.1.0 that prevented Basic Auth connections over HTTPS, including connections that were already configured.

## Fixed

- Fix **“Could not reach the Suwayomi server: redirect not supported”** when using Basic Auth over HTTPS. The plugin passed an unsupported option to KOReader's HTTPS client, which rejected the request before contacting the server. This error did not mean the server was redirecting the connection.
- Restore HTTPS requests for connection tests, library access, covers, chapter pages, and chapter archive downloads. Simple Login and UI Login retain their existing redirect restrictions.

## Verification improvements

- Add a regression test that exercises the real LuaSec request-option validation for Basic Auth queries, images, and archives.
- Add an optional HTTPS sandbox with a private localhost certificate and authenticated readiness checks. The repaired Basic Auth workflow was verified in real KOReader, including rejected credentials, successful connection, chapter download, opening, and return navigation. The fix was also confirmed on an Android device with existing Basic Auth settings.

## Updating

1. Download **`suwayomi.koplugin-v1.1.1.zip`** from the assets below, not GitHub's source archives.
2. Quit KOReader normally. Replace the existing plugin under `koreader/plugins/`, then relaunch KOReader. Keep your KOReader settings and downloaded chapters.
3. Run **Settings > Connection > Test connection** in Suwayomi.

**Keep your existing HTTPS URL and Basic Auth credentials.** No server change, authentication-method change, or setup reset is needed. This hotfix does not change settings, downloads, or reading-state behavior.

**Full changelog:** https://github.com/LK4D4/suwayomi.koplugin/compare/v1.1.0...v1.1.1

# v1.1.0 · 2026-09-10

Suwayomi Client v1.1.0 adds Simple Login and UI Login support, makes offline downloads more resilient, and improves how reading progress and local chapter cleanup work together.

## Highlights

### Connect with all three authentication methods

Choose **Basic Auth**, **Simple Login**, or **UI Login** in the setup wizard or connection settings to match your Suwayomi server. Simple Login and UI Login reconnect using your saved credentials; session cookies and JWT tokens stay in memory rather than being saved to disk. UI Login can refresh a rejected access token without interrupting your workflow.

### Keep your next chapters ready

**Download ahead** now saves refill work and recovers it after a KOReader restart. Finishing a chapter and closing it, or manually marking chapters as read, can refill your reading buffer even when the chapter list is not open. The menu shows the saved buffer size, with clearer refill status and Retry/Stop controls.

When you enable Download ahead, the plugin can offer KOReader's **Always mark as finished** setting. This is optional and applies to **all KOReader documents**, not only manga. Declining it leaves Download ahead enabled; manual read marking still works.

### More resilient background downloads

- Retry temporary network failures with bounded retries, and recover unfinished download jobs after restarting KOReader.
- Keep downloads running as you move between menus and the reader. Waiting retries and stopping workers no longer unnecessarily hold up other downloads.
- Show clearer failure details and preserve retry status. Use **Verify download** to check a suspect archive and **Redownload** to replace a damaged copy.
- Preserve completed-download bookkeeping when cancellation races with a finished transfer.

## Reading and library fixes

- Load complete chapter lists for large series, rather than making bulk actions depend on an incomplete list. Download actions disclose their limit of **50 new chapters per action**.
- Follow KOReader's finished status for automatic read completion. Reaching the last page alone no longer marks a chapter as read.
- Preserve KOReader reading metadata, including backup-only metadata, when changing read state or removing a local archive after manual read marking.
- Make finished-chapter cleanup durable across restarts and retry failed removals. Protect open or replaced archives, and revoke pending manual removal when the server marks a chapter unread again.
- Save plugin state atomically and report failed writes instead of silently losing queue or reading changes.
- Fix stale chapter actions, submenu Back navigation, saved scanlator-filter recovery, and oversized status dialogs. Reduce routine notification popups.

## Translations

Russian, Ukrainian, and Simplified Chinese now cover all current plugin strings. Download controls, refill status, and automatic-finish prompts have clearer localized text.

## Updating and getting started

1. Download **`suwayomi.koplugin-v1.1.0.zip`** from the assets below. Use this plugin ZIP, not GitHub's automatically generated source archives.
2. Replace the existing `suwayomi.koplugin` folder under `koreader/plugins/`, then restart KOReader. Keep your KOReader settings and downloaded chapters.
3. Open **Search > Suwayomi**. If needed, select your server's authentication method under **Settings > Connection > Login information**, then run **Test connection**.

Existing Basic Auth connections do not need to switch methods. If a download fails because of authentication, correct the saved credentials and retry the download explicitly.

**Security:** Use HTTPS when connecting over a network. HTTP exposes credentials and session tokens. Changing saved credentials does not cancel downloads that are already running.

**Download scope:** All plugin downloads and removal policies affect device-local CBZ files. The plugin does not queue or delete server downloads. For faster transfers, predownload chapters through Suwayomi's WebUI; the plugin can copy a complete server archive instead of fetching each page separately.

**Full changelog:** https://github.com/LK4D4/suwayomi.koplugin/compare/v1.0.6...v1.1.0

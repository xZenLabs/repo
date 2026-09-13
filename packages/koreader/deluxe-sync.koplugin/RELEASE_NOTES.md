# v0.2.0.0


Deluxe-Sync 0.2.0.0 is a major roll-up release containing all improvements made since the public 0.1.2 release. Standard KOSync progress syncing remains compatible with ordinary KOSync servers; the additional features below are used only when a server advertises support for them.

### Books, progress, and multi-device syncing

- Added per-server document matching choices. **Binary** matching remains the default, while **Filename** matching can be selected for libraries where the same book file differs between devices.
- Added a much richer **Synced Books** browser for compatible servers, including list/grid layouts, book covers, record details, and easier navigation of the remote library.
- Added **Logical Books** linking so alternate copies or formats of the same title can be grouped as one book without deleting or replacing their original sync records. Links can be inspected and undone later.
- When linking books, Deluxe-Sync now lets you choose which copy supplies the initial shared reading position instead of assuming that the newest record is the correct one. The furthest stored position is recommended by default.
- Added richer reading positions for compatible servers, including a portable percentage plus real KOReader page/page-count hints and XPointer data when available. This makes progress transfer between linked editions safer while exact same-file sync still uses KOReader's native position.
- Added durable device registration for compatible servers using KOReader's device identity, model/platform, KOReader version, and Deluxe-Sync version while keeping the existing Deluxe device ID compatible.

### Highlights, reading history, and Vocabulary Builder

- Added optional synchronization of KOReader **highlights, notes, and bookmarks** on compatible servers. Edits and deletions converge between devices, including protection against stale offline copies silently restoring an annotation that was deleted elsewhere.
- Added optional, read-only upload of KOReader **Reading Statistics**. Existing `statistics.sqlite3` history can be imported in resumable batches, later uploads are incremental, and Deluxe-Sync never writes to KOReader's live statistics database.
- Added optional **Vocabulary Builder** synchronization for compatible servers. Deluxe-Sync reads KOReader's vocabulary database in read-only mode and sends only new, changed, or deleted vocabulary records after the first sync.
- Vocabulary **Reading Context** is a separate opt-in choice because it can include surrounding book passages or highlighted text. It cannot be enabled unless Vocabulary Builder sharing is also enabled.

### Backups and moving Deluxe-Sync to another reader

- Added optional per-device **KOReader Settings Backup** for compatible servers. Backups use a core-only, fail-closed settings list and exclude credentials, device identity, third-party plugin data, caches, timestamps, current navigation/session state, frontlight/night-mode state, and other volatile values.
- Settings backups are checksum-deduplicated so normal reading activity does not create unnecessary snapshots. If a remembered server snapshot was deleted, Deluxe-Sync now detects that and recreates the backup automatically.
- Same-device settings restores always require confirmation on the reader and are revalidated immediately before applying, so a request that was deleted or cancelled on the server cannot be restored from stale local data.
- Added optional **Deluxe-Sync Config Backup** for moving the plugin to another reader. It can restore configured server URLs, usernames, Deluxe-Sync preferences, and the saved authentication needed to reconnect to the same existing accounts and already-synced progress.
- Config migration is explicitly confirmed on the destination reader and targeted to that reader. The destination keeps its own device identity and local sync caches rather than pretending to be the old device.

### Privacy and data-sharing controls

- Added a per-server **Data Sharing** review so enhanced data is no longer treated as implicitly enabled. Reading progress remains the required core sync service; Book Metadata, Annotations, Reading Statistics, KOReader Settings Backup, Deluxe-Sync Config Backup, Vocabulary Builder, and Vocabulary Reading Context can be controlled separately.
- Existing server configurations that predate the privacy controls fail closed for the new enhanced-data categories and are presented for review rather than silently sharing additional data.
- Deluxe-Sync warns before enabling Config Backup because it includes saved authentication keys, and separately warns before enabling Vocabulary Reading Context because book excerpts may be stored on the server.
- Restoring a Deluxe-Sync configuration does not silently grant new data-sharing consent on the destination reader.
- Standard KOSync servers continue to receive only the compatible KOSync data they support; unsupported enhanced features do not send extra requests.

### Reliability and recovery

- Failed transient progress pushes now use a persisted background retry schedule of 30 seconds, 2 minutes, 5 minutes, 15 minutes, 30 minutes, and 60 minutes. After the sixth background attempt, automatic retry pauses without discarding the queued progress.
- Retry processing no longer depends on Auto-Sync Documents being enabled when the network reconnects. Authentication failures are intentionally not retried automatically; a manual retry, newer push, or later reconnect can resume eligible queued work.
- Enhanced server capabilities are refreshed on every network reconnect, and pending restore requests are checked before optional background-data synchronization.
- Hardened settings-backup convergence so interrupted presence checks/uploads cannot permanently block future backups, and deleted server snapshots are treated as authoritative instead of trusting stale local state.
- Fixed server Recovery/Delete callbacks so they no longer shadow KOReader's translation helper before translated confirmation text is built.

### Server setup and interface

- Server editing now uses a centered **Authenticate / Sign in** action that validates the current draft credentials, saves them only after successful authentication, and refreshes server capabilities in the same flow.
- Simplified the server edit page by removing duplicate Synced Books and enable/disable actions, shortening the server address label to **URL**, truncating long displayed URLs, and condensing action rows for e-reader screens.
- Added clearer capability reporting so supported enhanced features can be reviewed per server.
- Refreshed the README screenshot gallery to match the current Deluxe-Sync interface.

### Updating from 0.1.2

- The built-in updater supports a direct upgrade from the public **0.1.2** release to **0.2.0.0**.
- Deluxe-Sync now uses four-part release versions. The updater accepts both the older three-part format and the new four-part format, including `v`-prefixed GitHub release tags.
- **Auto-Sync Documents remains OFF by default** unless the user enables it.

# v0.1.2


### Added

- Added KOReader gesture/dispatcher actions for Deluxe-Sync Auto-Sync On/Off, Auto-Sync Toggle, Push Progress to All, and Pull Progress from All.
- Added gesture-safe availability checks and user-facing feedback when syncing is unavailable because the plugin is not ready, preview mode is active, or no sync server is enabled.

### Changed

- Bumped Deluxe-Sync to version 0.1.2.
- Updated the in-plugin updater to accept both current three-part `x.y.z` versions and future four-part `w.x.y.z` versions, including `v`-prefixed GitHub release tags.
- Normalized legacy three-part versions as `0.x.y.z` for comparisons so future four-part releases sort predictably.
- Updated README version synchronization and GitHub release validation to accept both supported version formats.
- Documented the new KOReader gesture actions and their safe multi-server behavior in the README.
- Updated the release workflow so the matching changelog section is used as the GitHub release notes.

### Tests

- Added Dispatcher registration regression coverage.
- Added updater comparison coverage for three-part, four-part, prefixed, mixed-format, and invalid version strings.

# v0.1.1

**Full Changelog**: https://github.com/jadehawk/deluxe-sync.koplugin/compare/v0.1.0...v0.1.1

# v0.1.0

# Deluxe-Sync v0.1.0

First public release of Deluxe-Sync, a KOReader plugin for synchronizing reading progress across multiple independent KOSync-compatible servers.

## Highlights

- Multiple server profiles with independent URL, account, enable/disable state, and detected capabilities.
- Standard KOReader KOSync registration, authentication, push, and pull compatibility.
- Push the current reading position to every enabled server.
- Consolidated multi-server Pull Results with differing positions sorted newest-first and identical positions grouped together.
- Independent automatic behavior for newer and older remote states: **Silently**, **Prompt**, or **Never**.
- **Auto-Sync Documents defaults OFF**, matching KOReader built-in Progress Sync. When enabled, Deluxe-Sync can pull on document ready/resume and push on suspend/close.
- Per-server retry queues for offline and transient failures, including a queue viewer, generic failure reasons, and manual retry. Queues belonging to disabled or deleted servers are discarded. A server reaching 20 queued updates is automatically disabled and its queue is cleared.
- Safe remote-position review and preview. Deluxe-Sync preserves the exact local position while previewing and suppresses its own sync activity until the preview is accepted or cancelled.
- Server Details capability card showing enabled state, remote library support, and account recovery support.
- Generic user-facing connection/authentication errors while raw transport details remain available in diagnostic logging.

## Enhanced server support

Deluxe-Sync remains compatible with standard KOSync servers while detecting optional enhanced capabilities.

- Optional metadata extension containing filename, title, and authors, with automatic fallback to the standard KOSync payload when unsupported.
- Optional remote document listing and remote-library browsing.
- Local library matching uses binary checksum matches first, then filename and title/author matching.
- Remote library results are grouped into metadata-available and metadata-unavailable sections and can be inspected without changing reading position.
- Optional account recovery with stored recovery email, time-limited six-digit email code, password reset, and verification of the replacement credential before it is saved.

## Complimentary Techy-Notes server

On first start with no configured servers, Deluxe-Sync offers the complimentary **Techy-Notes.com** server at https://sync.techy-notes.com or lets the user configure a custom KOSync server.

The Techy-Notes server supports standard KOSync progress syncing plus metadata, remote library listing, and account recovery. Choosing it does not automatically enable Auto-Sync Documents.

## Updates and diagnostics

- Built-in GitHub update checking with automatic once-per-session checks, manual checks, per-version skip persistence, staged replacement, and restart prompt.
- Plugin-owned runtime data under settings/deluxe-sync/.
- Diagnostic logging is available from the plugin and can be disabled by the user.

## Installation

Download **deluxe-sync.koplugin.zip** from the assets below, extract it, copy the complete deluxe-sync.koplugin folder into KOReader plugins, and restart KOReader.

Project: https://github.com/jadehawk/deluxe-sync.koplugin
Techy Notes: https://techy-notes.com
YouTube: https://youtube.com/@jadehawk
Buy Me a Coffee: https://buymeacoffee.com/jadehawk

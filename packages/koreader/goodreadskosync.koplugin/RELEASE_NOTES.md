# v1.12.0

﻿## Goodreads KO Sync 1.12.0

### Changed
- **Internal refactor only — no behaviour change.** A single reusable Goodreads API module, a dedicated sync controller, and shared tasks / menu / notes modules. This makes the code easier to maintain as Goodreads changes.

No analytics and no telemetry.

# v1.11.5

﻿## Goodreads KO Sync 1.11.5

### Fixed
- **Automatic syncs (open/close/reconnect) no longer abort** when you tap the screen; the queue flush now runs to completion.
- **Automatic open/reconnect syncs show a toast** when they send a queued item.
- **Sync now works with no book open** and respects sticky Read / Did Not Finish.
- **Notes to Goodreads** are saved offline and posted automatically when you reconnect.
- CSRF token is fetched/refreshed correctly (fixes the earlier write failures).

### Changed
- Toasts show just the book/action detail (no plugin-name prefix).
- **Browse shelves** is temporarily hidden from the menu.
- Optional **Diagnostic logging** in Settings (off by default).

### Notes
- **Relaxed** syncs on open, close and reconnect (no periodic timer).
- No analytics and no telemetry.

# v1.11.3

﻿## Goodreads KO Sync 1.11.3

### Fixed
- **Syncing works again** (progress, shelf, rating, remove). Goodreads rotates its CSRF token; the plugin was reusing the one from login, so every write was rejected with 404. It now fetches a fresh token before each write.

### Included since 1.10.1
- **Diagnostic logging** option in Settings (off by default) for troubleshooting.
- **Smaller toasts.**
- **Shelves are cached** after the first load; refresh only when you ask.
- Shelf book lists show each book's **author** with row separators.
- The **update prompt shows release notes**.

### Notes
- **Relaxed** syncs on open, close and reconnect (no periodic timer).
- No analytics and no telemetry.

# v1.10.1

﻿## Goodreads KO Sync 1.10.1

### Fixed
- **No more duplicate reading updates for the same percent.** A queued progress send now records its success, so the next sync (open/resume/reconnect) does not push the same percent again.

Automatic syncs still never turn Wi-Fi on by themselves. No analytics and no telemetry.

# v1.10.0

﻿## Goodreads KO Sync 1.10.0

### Changed
1. The plugin is now named **Goodreads KO Sync** (the "(unofficial)" suffix is gone from the menu).
2. New installs default to the **Relaxed** sync preset (least battery use); existing installs keep their chosen preset.

Automatic syncs still never turn Wi-Fi on by themselves. No analytics and no telemetry.

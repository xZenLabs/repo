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

# v1.9.3

﻿## Goodreads Sync 1.9.3

- Minor changes.

Automatic syncs still never turn Wi-Fi on by themselves. No analytics and no telemetry.

# v1.9.2

﻿## Goodreads Sync 1.9.2

### Fixed
1. **Settings no longer crashes KOReader.**
2. **No duplicate progress:** if Goodreads already has your current percent, closing the book no longer pushes the same value again.
3. **Shelves are cached:** after the first **Load from Goodreads**, the shelf list and the books you open are stored on the device, so the browser opens instantly and only re-fetches when you tap **Refresh from Goodreads**.

### Changed
4. **Shelf book lists** now show each book's **author** on the right, with clear row separators.
5. **The update prompt shows release notes:** when a new version is available you see these notes before choosing **Update**; installing downloads, verifies (SHA-256), and asks for a restart.

### Notes
- Automatic syncs still never turn Wi-Fi on by themselves.
- No analytics and no telemetry.

# v1.9.1

**Full Changelog**: https://github.com/gkgangavarapu/goodreadskosync/compare/v1.9.0...v1.9.1

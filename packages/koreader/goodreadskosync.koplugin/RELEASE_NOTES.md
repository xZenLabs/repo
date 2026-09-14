# v1.6.4

## goodreadskosync v1.6.4

### Fixed

- Crash when changing a sync preset (a loop variable named `_` shadowed the translation function inside the callback).
- Crash in **Waiting to sync** when there were failed operations (same cause).
- Hardened the link-failure dialogs (nil identity) and the background-task fallback (errors no longer propagate) so an unexpected failure can't crash KOReader.

# v1.6.3

## goodreadskosync v1.6.3

### Changed

- Default sync preset is now **Medium** (open/close + a checkpoint every 15 minutes).
- Selecting a sync preset now shows a brief confirmation of what it does.
- When a book can't be linked automatically, a window offers to enter its Goodreads ID or ISBN (with a short how-to) and an **Ask me in an hour** option.

### Fixed

- Turning Wi-Fi on when prompted now runs the requested action automatically (Sync now, Check for updates, sign-in, Test connection, search) instead of needing another tap.
- Closing a book (or reconnecting) no longer shows "Offline changes synced" when online; the toast now names the book.

# v1.6.2

## goodreadskosync v1.6.2

### Fixed

- Choosing a sync preset now also turns open/close syncing on, so the event triggers always work (previously a legacy setting could keep them disabled).

### Changed

- README documents what triggers a sync under each preset.

# v1.6.1

## goodreadskosync v1.6.1

### Changed

- Update checks now run about once a day (previously once a week). When a newer version exists you get a single "Update now?" prompt per day until you update.
- Notifications are now prefixed with "Goodreads Sync:" and name the book, so it is clear what happened and where it came from. Wording is shorter and more specific throughout.

# v1.6.0

## goodreadskosync v1.6.0 — stable

A stable release that consolidates the major update round.

### Added

- **Sync presets** — one choice (Fastest default, Faster, Medium, Relaxed) sets all sync timing and tracking.
- **Mark new books as Currently Reading** (on by default).
- Reliable on-device sign-in, including an on-device prompt for extra verification and automatic retries on flaky connections.
- Gentle background notifications (offline saves and flushes, linking, Currently Reading, and sync failures).
- Install from **KOReader Storefront** (or from Releases).

### Changed

- Automatic syncs no longer turn Wi-Fi on; they use the connection when it is available and otherwise queue. Only an explicit **Sync now** asks to turn Wi-Fi on.
- The Account menu reflects the sign-in state (Log in when signed out, Log out when signed in).
- Remote shelf reads are cached; routine syncs stay quick.

### Fixed

- Login no longer reports false bot/CAPTCHA failures or shows vanishing popups.
- Reading offline is never stranded: progress is pushed as soon as the connection returns.
- Opening a new book offline no longer prompts for Wi-Fi; it links automatically once online.

### Removed

- The non-working "Open on Goodreads" button.
- The individual sync settings (replaced by presets).

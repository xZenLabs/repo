# v1.2.0 · 2026-11-11

## Email to KOReader 1.2.0

### New
- **Choose what to download.** Check Inbox now lists the books waiting in your mailbox, one line each. Tick the ones you want; the others stay unread for next time.
- **Share one mailbox between devices.** Switch on "Keep downloaded emails unread" in the Check Inbox window and every device gets the book. Each device remembers what it already fetched, so nothing downloads twice.
- **Mail folder / Gmail label setting.** Point the plugin at a folder such as `Books` instead of the inbox (#9).

### Fixed
- **Plugin missing from the Tools menu** on recent KOReader versions: the plugin now ships the required `_meta.lua` (#15).
- **Books from Calibre, Calibre-Web Automated and Grimmory not recognised** (#7, #10): sturdier handling of attachment headers and file names.
- **Corrupted books after a dropped connection** (#13): a partial download is now discarded, an error is shown, and the email stays unread so the next check retries.
- **Passwords containing `"` or `\`** now work, and a failed login shows the mail server's reason.
- **"Downloaded 0 books" on Kobo and PocketBook**: the default download folder is now KOReader's home folder instead of a Kindle-only path, and an unwritable folder shows an error.

### Changed
- Emails without a matching attachment are no longer downloaded or marked as read, so the plugin is safe to use on a normal inbox.
- Connection errors now show the IPv4 and IPv6 results separately.
- The gesture / profile action downloads every book without showing the selection window.

### Upgrading
Replace the plugin folder and keep your `config.lua`. The folder must be named `emailtokoreader.koplugin`. You can delete the old `manifest.lua` and `metadata.lua` if they are still in the folder.

# v1.1.1 · 2025-11-14

## Email to KOReader v1.1.1

### Fixes
- Added version field to manifest.lua for KOReader Updates Manager compatibility
- Improved fallback path logic using a cleaner preference chain
- Fixed crash in Settings dialog caused by calling MultiInputDialog:getFields() on the class instead of the instance (now uses settings_dialog:getFields())
- Fixed issue where settings sometimes did not save due to incorrect field retrieval
- Improved reliability of download path validation with clearer logging
- General stability improvements for saving configuration and writing files

### Improvements
- Removed unnecessary pcall() wrappers for modules always available in KOReader
- Cleaner and more consistent fallback path assignment
- Improved settings persistence code
- Minor code cleanup, formatting fixes, and internal optimizations

# v1.1.0 · 2025-11-03

## Email to KOReader v1.1.0

### New
- Cyrillic and Unicode filename support (RFC 2047/2231 decoding)
- Automatic Cyrillic→Latin transliteration for filename compatibility
- Smart fallback path (user home → KOReader home directory)
- "View Download Path" menu item

### Fixes
- Write error handling and detailed error messages
- Directory creation on-demand
- Path validation improvements

### Improvements
- Multi-line email header support
- Enhanced logging and user notifications

# v1.0.0 · 2025-11-02

### Initial release with:

- IMAP email integration
- Multi-file download support
- Large file handling (up to 3.5MB)
- In-app configuration
- Debug mode
- Auto-refresh file browser
- Gmail app password support

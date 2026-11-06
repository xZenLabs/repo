# 26.11.6 · 2026-11-06

## What's New

* **Book backups**: You can now include your actual ebook files in backups alongside your reading progress and settings. Choose between backing up books you are actively reading (*In-Progress*), your entire library, or specific folders.
* **Persistent manual backup settings**: Component selections and individual item choices in manual backups are now remembered across sessions, so you don't have to reconfigure them each time you back up.
* **Multiple book folders**: You can now set up multiple book directories in *Settings* (such as secondary libraries, research papers, or external SD cards) so reading progress and book files across all of them are preserved.
* **Show hidden folders in file picker**: Added a toggle in the folder browser to show or hide dot folders, making it easy to select directories like `.koreader` or custom hidden backup paths.
* **Snooze scheduled reminders**: When an automated backup reminder appears while you're reading, you can now snooze it for *1 hour*, *4 hours*, or *1 day* to be reminded later.

**Full Changelog**: https://github.com/ultimatejimmy/backup.koplugin/compare/26.10.23...26.11.6

# 26.10.23 · 2026-10-23

## What's New

### Scheduled Backup Reminders
You can now set regular reminders so your device backups stay up to date without getting in the way of your reading:
- **Flexible schedules**: Choose reminders for *Every 3 Days*, *Weekly*, *Every 2 Weeks*, or *Monthly*.
- **No background freezes**: Compressing files takes real processing power on e-ink hardware. Instead of running silently in the background and freezing your page turns mid-sentence, the plugin checks if a backup is due and shows a polite reminder.
- **Three clear choices**:
  - **Backup Now**: Runs a one-tap backup right away with the standard progress bar.
  - **Later**: Snoozes the reminder for 24 hours so you can keep reading undisturbed.
  - **Open Settings**: Takes you straight to backup settings if you want to make adjustments.
- **Custom component selection**: Pick exactly what goes into your backups. Keep them fast and light with just your settings and reading stats, or include your full collection of fonts, screensavers, and user plugins.
- **Automatic cloud upload**: Backups can automatically upload to your configured cloud storage whenever Wi-Fi is active.

### Nested Cloud Folder Support
You can now organize your cloud backups into subfolders (such as `mine/koreader kindle/backup`):
- **Automatic folder navigation**: Instead of treating slashes as part of a single folder name, the plugin automatically creates and navigates the nested folder hierarchy for you.
- **Broad cloud support**: Works across all cloud integrations, including Google Drive, Microsoft OneDrive, Dropbox, WebDAV, FTP, and SFTP.
- **Smart path cleaning**: The folder setting cleans up leading, trailing, and duplicate slashes, and seamlessly handles both forward slashes (`/`) and Windows backslashes (`\`).

### Improvements & Fixes
- **E-ink display tuning**: Updated the refresh logic on the loading toast to be smoother and gentler on e-ink screens.

**Full Changelog**: https://github.com/ultimatejimmy/backup.koplugin/compare/26.10.8...26.10.23

# 26.10.8 · 2026-10-08

### What's New

* **Cloud Backup Providers:** You can now back up and sync directly with popular cloud storage services:
  * Google Drive
  * Microsoft OneDrive
  * Dropbox
  * FTP / SFTP
  * WebDAV
* **Browser Beam Option:** Added support to easily beam backups to your web browser.
* **Icon Backup:** Added a new setting to include custom icons in your backup archives.
* **More Granular Menus:** Updated the backup creation and restore menus so you have finer control over exactly what gets saved or restored.
* **Interface Improvements:** Cleaned up the layout and structure across the board, along with a refreshed settings user experience to make navigation smoother.

**Full Changelog**: https://github.com/ultimatejimmy/backup.koplugin/compare/26.9.28.3...26.10.8

# 26.9.28.3 · 2026-09-29

- make beam logic from low memory devices reliable/efficient

**Full Changelog**: https://github.com/ultimatejimmy/backup.koplugin/compare/26.9.28.2...26.9.28.3

# 26.9.28.2 · 2026-09-28

Various bugfixes

**Full Changelog**: https://github.com/ultimatejimmy/backup.koplugin/compare/26.9.28.1...26.9.28.2

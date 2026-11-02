# 26.11.2-beta · 2026-11-02

- Show hidden folders in the file picker
- add snooze feature
- add option to backup books


**Full Changelog**: https://github.com/ultimatejimmy/backup.koplugin/compare/26.10.29-beta...26.11.2-beta

# 26.10.29-beta · 2026-10-29

- Settings from manual backups now persist
- You can now select multiple books folders in the settings

**Full Changelog**: https://github.com/ultimatejimmy/backup.koplugin/compare/26.10.23...26.10.29-beta

# 26.10.22-beta · 2026-10-22

### What's New

* **Nested Remote Folder Support**: You can now organize your cloud backups into subfolders (such as `mine/koreader kindle/backup`). Instead of treating the slashes as part of a single folder name, the plugin will now automatically create and navigate the entire folder structure for you.
* **Broad Cloud Compatibility**: Full nested directory support works across all cloud integrations, including Google Drive, Microsoft OneDrive, Dropbox, WebDAV, FTP, and SFTP.
* **Smart Path Cleaning**: The remote folder setting now automatically cleans up leading, trailing, and duplicate slashes, and seamlessly handles both forward slashes (`/`) and Windows backslashes (`\`).

**Full Changelog**: https://github.com/ultimatejimmy/backup.koplugin/compare/26.10.21-beta...26.10.22-beta

# 26.10.21-beta · 2026-10-22

update eink refresh logic on loading toast

**Full Changelog**: https://github.com/ultimatejimmy/backup.koplugin/compare/26.10.16-beta...26.10.21-beta

# 26.10.16-beta · 2026-10-16

### What's new

* **Scheduled Backup Reminders**: You can now set reminders to back up your setup regularly. Choose between *Every 3 Days*, *Weekly*, *Every 2 Weeks*, or *Monthly*.
* **Thoughtful Timing (No Freeze)**: Compressing backups on e-ink hardware takes real processing power. Instead of silently running in the background and freezing your page turns mid-sentence, the plugin checks if a backup is due and shows a polite reminder.
* **Three Clear Choices**:
  * **Backup Now**: Starts a one-tap backup right away with the standard progress bar.
  * **Later**: Snoozes the reminder for 24 hours so you can keep reading undisturbed.
  * **Open Settings**: Jumps straight into your backup schedule settings if you want to tweak things.
* **Custom Component Selection**: You can choose exactly what goes into your scheduled backups. Keep them fast and light with just your reading stats and settings, or include your full collection of fonts, screensavers, and user plugins.
* **Automatic Cloud Upload**: If you already have cloud storage configured (Google Drive, WebDAV, Dropbox, OneDrive, FTP, or SFTP), you can have your scheduled or regular backups automatically upload to the cloud whenever Wi-Fi is active.

**Full Changelog**: https://github.com/ultimatejimmy/backup.koplugin/compare/26.10.8...26.10.16-beta

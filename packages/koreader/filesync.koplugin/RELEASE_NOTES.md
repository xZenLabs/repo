# v1.9.1

- Installs from before v1.7.0 that still saved port 8080 now move to port 80, so http://filesync.local works with no ":8080" suffix. A port you set by hand is left alone. (#51)
- On devices that cannot use port 80, the "needs root access" message now appears once per port instead of on every start. (#51)

# v1.9.0

- The server is now reachable at http://filesync.local, so there is no IP to type. Rename it in the plugin menu. Works on macOS, iOS and Windows; Linux needs avahi; Android needs the IP. (#47)
- Folders can now be uploaded from the web UI, with a Choose Folder button or by dropping one on the page. (#41)
- Fixed: folders with a leading or trailing space could be listed but not opened on 2024+ Kindles. Failed opens now say why. (#46)

# v1.8.0

- KOReader's *Delete plugin and settings* / *Disable plugin and delete settings* menu entries now work for FileSync: the plugin's settings are removed along with it, and the file server is stopped cleanly before the restart. (#25)
- Stopping the file server no longer quits KOReader on Android (and macOS/SDL), where the app cannot restart itself. The screen is refreshed instead. The updater's *Restart now* button had the same problem and now asks you to reopen KOReader manually. (#34)

# v1.7.0

- File server toggle is now available as a Simple UI quick action, so the server can be started and stopped without opening the plugin menu. (#36)
- Hidden files and folders are now shown in the web UI when safe mode is off. (#32)
- Default port is now 80, so the server can be reached by typing just the device IP with no ':port' suffix. Existing users keep their saved port. (#27)
- Ports below 1024 are now accepted, with automatic fallback to 8080 when the privileged bind fails (Android/desktop, where KOReader isn't root). (#27)
- QR code screen now works on non-touch devices: The screen is fully keyboard-navigable. (#31)
- README is now more generic about supported devices. (#30)
- Synced all translation catalogs with the codebase. (#38)

# v1.6.0

- Start server flow now triggers KOReader's standard "Turn on Wi-Fi?" prompt instead of bailing with a warning when WiFi is off; server starts automatically once connected. Same flow applies to the update check. (#23)
- Web UI now opens in the KOReader home folder by default. (#22)

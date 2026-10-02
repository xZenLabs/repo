# v1.11.0 · 2026-09-27

## In-browser text editor

- New **Edit** button in the web UI opens text and config files in a full-screen editor with syntax highlighting for 30+ languages (Lua, JSON, YAML, Markdown, shell, Python, and more). Save in place with the Save button or `Ctrl+S`.
- Files up to 256 KB are editable. Binary files are detected and stay download-only.
- Backup files such as `bookshelf.lua.old` and `notes.lua~` are recognised by their base type.
- Safe mode stays strictly read-only: the Save button is hidden and saves are refused server-side.
- Editor UI strings are machine-translated for the 10 supported languages. Corrections welcome.

Thanks to @imsudip for the contribution (#43, closes #42).

# v1.10.0 · 2026-09-19

- Fixes issue stopping server freezes Kobo devices

# v1.9.1 · 2026-09-17

- Installs from before v1.7.0 that still saved port 8080 now move to port 80, so http://filesync.local works with no ":8080" suffix. A port you set by hand is left alone. (#51)
- On devices that cannot use port 80, the "needs root access" message now appears once per port instead of on every start. (#51)

# v1.9.0 · 2026-09-17

- The server is now reachable at http://filesync.local, so there is no IP to type. Rename it in the plugin menu. Works on macOS, iOS and Windows; Linux needs avahi; Android needs the IP. (#47)
- Folders can now be uploaded from the web UI, with a Choose Folder button or by dropping one on the page. (#41)
- Fixed: folders with a leading or trailing space could be listed but not opened on 2024+ Kindles. Failed opens now say why. (#46)

# v1.8.0 · 2026-08-23

- KOReader's *Delete plugin and settings* / *Disable plugin and delete settings* menu entries now work for FileSync: the plugin's settings are removed along with it, and the file server is stopped cleanly before the restart. (#25)
- Stopping the file server no longer quits KOReader on Android (and macOS/SDL), where the app cannot restart itself. The screen is refreshed instead. The updater's *Restart now* button had the same problem and now asks you to reopen KOReader manually. (#34)

# v1.0.15 · 2026-10-27

**Updates**
- Settings > **Updates**, at the top of Settings: Check for updates, Update from, Install a version, Optional apps, Check automatically and Undo a plugin update, all on one page.
- While an update installs, the Kindle shows how far it is: the download, then each plugin checked and installed in turn. It keeps answering meanwhile, so there's no need to restart it.
- **Install a version** lists the repo's branches after its releases. A branch installs the code as it is now; Check for updates then looks for newer commits on it.
- **Optional apps**: extra apps you can add, kept out of the main install. Install, update or remove them from Settings > Updates, or from the web page. Installed ones are updated with the rest.
- Set up your Kindle has an **Updates** step after Wi-Fi: where updates are, whether a new version is out, and the optional apps.

**New optional apps**
- **FlashForge**: your FlashForge 3D printer over Wi-Fi: the print, temperatures, pause and cancel, the light, a camera picture, and starting a recent file.
- **Pangolin**: your Pangolin server's sites, resources and clients: what's online, each resource's health, and turning resources and clients on or off.

**Settings**
- Settings opens in groups: Getting started, Settings, Accounts, Reading, Home, Writing and Tools. Hold a row to move it, put it in another group or hide it; hold a group's name to rename, move or delete it. Layout switches to One list. Hidden rows are still found by search (hold one there to show it again).

**Web server**
- **HTTPS**, off to start with: the Kindle makes its own certificate (browsers warn about it once), or paste or upload yours on System > HTTPS. A certificate that can't be used leaves the page on plain HTTP, and the Kindle says why. Both certificates go in a backup only with Include keys and sign-ins.
- System > **Update from GitHub**: type a repo and pick a release or branch to install, with its optional apps.
- Installing a zip shows how far it is (the upload, then each plugin), on the page and on the Kindle; after KOReader restarts, the page comes back by itself.

**Notes**
- Tapping a crossword's number refreshes only the outlines and the clue card, not the whole page.

The release now has a zip for each optional app (kindle-flashforge.zip, kindle-pangolin.zip) next to kindle-plugins.zip.

# v1.0.14 · 2026-10-26

**SSH**
- A host that doesn't answer is tried again at its next check, not every minute. After 3 checks in a row without an answer, its checks pause ("Checks paused" on the SSH page and its page) until you open it or tap ⟳ and it answers.

**Other Kindles**
- Everything here was built and tested on a Kindle Scribe. For another Kindle with KOReader, point your AI coding agent at this repo: AGENTS.md now has a "Not a Kindle Scribe?" section that has it ask about your device, go through every Scribe-specific part, and offer choices for a Kindle without a pen (leave out Notes and Crosswords, typed notes, or typed crosswords). The README's Installing section points there.

The guide PDF is updated.

# v1.0.13 · 2026-10-26

**Launcher updates**
- What's new: after an update, its notes show once when KOReader starts again.
- Update available: until a newer release is installed, the launcher's Settings tile says so.
- Install a version (Settings > Launcher): pick any release, an older one too.

**SSH**
- ⋮ > Lock now: every PIN (SSH's own and the hosts') asked again at once.
- A command's output pop-up opens where you last dragged it.

**Diagnostics**
- The diagnostics file has a longer history of KOReader's log: the last hours, kept across restarts, without the lines for every touch and redraw.

The guide PDF is updated.

# v1.0.12 · 2026-10-26

**Launcher**
- Updates from GitHub: Settings > Launcher > Check for updates shows the version installed, looks for a newer release, shows its notes and installs it with Update (the old version kept for Undo a plugin update, then a restart). When you're up to date it offers Reinstall.
- Update from: the repo updates come from (this one to start with; another owner/repo to follow a fork).
- Check automatically (on to start with): once a day, only while already on Wi-Fi, a notification when there's a newer release.
- From this release on, the Kindle knows which version it has. Coming from an earlier one, it shows Version not known and offers the update.

**SSH**
- An optional app PIN (SSH settings > Set an app PIN), asked when SSH opens and before a host or command opened from outside it. A host's own PIN still asks too.

**Fixes**
- Installing a zip (the web page's Update plugins, and the new updater) keeps the Syncthing program runnable.

The guide PDF is updated.

# v1.0.11 · 2026-10-26

**SSH**
- A command's output (quick commands, saved commands, Run a command) opens in a pop-up over the host's page: drag it by its title bar, tap ✕ or outside it to close it. Its buttons: Copy all, Explain and Summarize (with an AI set up), Run again, Live session (on the same host) and Full screen (the output on a full page, with Find). Hold a quick command for Run full screen.
- SSH settings has Text size for the live session (10 to 24; the next session opens with it). The output's text follows it too.

The guide PDF is updated.

This release was built and published by GitHub Actions.

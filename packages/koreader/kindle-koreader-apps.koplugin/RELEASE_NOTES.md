# v1.0.16 · 2026-11-07

**New optional apps**
- **pfSense**: your pfSense firewall over its REST API package: gateways, interfaces, services (start, stop, restart), devices from DHCP and the ARP table with Wake-on-LAN, static mappings and DNS overrides, firewall rules on or off, aliases, NAT, VPNs (WireGuard, OpenVPN, IPsec), certificates' expiry with ACME renew, packages, logs, and reboot.
- **NextDNS**: your NextDNS profile: today's queries and what was blocked, the query log (filtered, searched, or one device's), the denylist and allowlist, the security, privacy and parental control switches, and whether this Kindle uses NextDNS.

**Launcher**
- **App lock** (Settings > Launcher > App lock): a passcode or password before the apps you choose. They stay unlocked until the Kindle sleeps. SSH's own app PIN becomes part of it.
- **Message time** (Settings > Launcher): how long short messages and Undo stay on screen, in every app.
- **Page bar** (Settings > Launcher): what's at the foot of a page with more than one page: numbered parts, parts and Next, or words.
- **Continue reading** can be turned off. It skips a deleted book, and opens the Library when there's no book to continue.
- Shortcuts for **SSH hosts** and **crosswords**, from Add shortcut or from the app itself (hold a host in SSH, or Today's crossword in Crosswords).
- **Help** (⋮) is rewritten for today's apps, with a link to the user guide.
- **Fonts** in three tabs (Your fonts, Get more, Settings). Get more browses all of Google Fonts.
- Settings has an **Optional apps** group.

**Updates**
- Each optional app shows its version and **Up to date** or **Update available**, with **Update**, **Reinstall** and **Remove**. **Update all** when two or more have an update.
- **Show test versions**: test versions appear in Select version, and Check for updates finds them too.
- An optional app that can't be updated with the rest says so in a notification.
- Shorter, plainer text throughout.

**FlashForge**
- While printing, change the **speed**, **Z offset** and **fans**.
- The Camera page has **Camera on**, **Camera off** and **Light**, and can **refresh automatically** (every 2 seconds to 5 minutes).
- Settings > **SHOW** hides the light, camera, air filter or fans for a printer that doesn't have them.
- **Monitor prints** (Settings) reads the printer in the background while the Kindle is awake, so notifications come with FlashForge closed. New notifications: **Print paused** and **Print hasn't moved in 20 min**.

**SSH**
- **Use a key** (Edit host): adds the key to the host for you and switches the host to it.
- **Connect through** another host (Edit host), for a device you can only reach through another one.
- **Reconnect** when a live session ends.
- **Wake** waits for the host to answer, then reads its status.
- **Ask before running**, for a saved command (hold it).
- **Save** on the full output page keeps the output as a text file in Downloads.
- The live session's buttons are an icon row, leaving more room for the terminal.
- The web page's SSH tab has SSH settings and each host's groups, checks, MAC address, stats, sensors, alerts and quick commands.

**To Do**
- **Keep rows in place**: rows stay where they are after Done, a star or a new date, until you leave the list. A sort button (↕) puts them in order again.
- A **Completed** row at the end of a list, with its count, opens the done tasks (with **Not done**).
- **Skip to current** shows only for a repeating task that's overdue.
- The web page's settings match the Kindle's.

**Home Assistant**
- Locks and sensors show when they last changed ("Changed 12 min ago").
- **Keep rows in place** for Activity.
- Routines as quick buttons, in search and as a gesture. Search opens a device.
- Its own part in the web page's backup.

**Notes and Crosswords**
- **Handwritten notes on highlights**: Write a note in the highlight menu opens a pad, and the note's mark opens it again. Holding the pen's side button while selecting makes the highlight and opens the pad.
- Crosswords: **Swap grid and clues**, a **Random puzzle** button, and new puzzles when Wi-Fi comes on.
- Notes no longer jumps into the last crossword when it opens. **Open the last notebook** is off to start with.
- More Notes and Crosswords settings on the web page, and their entries in the bell.

**Library and Wikipedia**
- Library: **Keep rows in place** after a status change.
- Library and Wikipedia settings on the web page, and their books and saved articles in the page's search.
- Wikipedia quick buttons.

**Syncthing**
- Notifications for stuck syncs and conflicting files (a switch turns them off).
- A running icon by the clock, **Turn off when up to date**, and **Sync now, then turn off**.
- Search opens a folder or device. The web page has the port and web GUI password.
- Syncthing v2.1.7 (was v2.1.2).

**Web server**
- **Keep the Kindle awake** while it runs, and **Stop when idle**.
- System > **Updates** as on the Kindle, with the optional apps.
- The **Fonts** tab, notifications on Home, and the Launcher tab's App lock, Message time and new shortcuts.

**Fixes**
- To Do: the hold menu's buttons answer taps again.
- Notes and Crosswords: Wi-Fi is checked the right way (they no longer think the Kindle is offline when it's connected).
- The web page keeps a deleted Notes page for 30 days, as the Kindle does.
- pfSense: the logs open again, and interfaces that are on no longer show as Disabled.
- Pangolin and SSH: no grey boxes where an icon was missing.
- SSH: a gesture for a deleted command says so in the apps' own message box.
- Web page: text always goes in as plain text, never as HTML.
- GitHub workflows run with read-only access.

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

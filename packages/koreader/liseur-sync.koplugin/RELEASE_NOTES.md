# plugin-0.13 · 2026-11-08

The KOReader plugin, packaged for KOReader's App Store or a manual install.

Unzip into KOReader's `plugins/` directory and restart KOReader.
See [koreader-plugin/README.md](https://github.com/chmouel/liseur-sync/blob/main/koreader-plugin/README.md) for setup and token permissions.

## Changes

- ci(koplugin): release the plugin ZIP on every koreader-plugin change (3fe769e)
- fix: still offer another device's place after a first upload (96808cb)
- fix: keep every reading position when servers or devices disagree (f61fdfc)
- fix: never drop the furthest point read or a stale download (85443c0)
- fix: keep reading progress and downloads safe in the KOReader plugin (b7e9bc7)
- feat: Improve book details and sync error notifications (660aa52)
- feat: Verify SHA-256 hash when reusing downloaded books (35df79b)
- fix: Improve file identification and error handling for KOReader plugin (9dd73cf)
- fix(koplugin): open the local screens without Wi-Fi (a9a7bd8)
- fix(koplugin): keep the token, the session and the menu honest (b0666b3)
- fix(koplugin): stop shadowing gettext inside book-detail lines (02c1561)
- fix(koplugin): learn who the token is on first use (13c29d4)
- feat(koplugin): add a KOReader client for the native API (5f2bbfe)

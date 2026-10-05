# v0.5.5 · 2026-08-10

# v0.5.4 · 2026-08-10

# v0.5.2 · 2026-08-10

# v0.5.1 · 2026-08-10

Bugfix release. The 0.5.0 in-app updater could not download the release asset on-device because verified TLS wasn't preserved across GitHub's cross-host redirect. 0.5.1 follows the redirect manually with a verified connection per hop, runs the download in a cancellable subprocess so the UI never freezes, and reports the underlying reason if a download ever fails. If you're on 0.5.0, update via Check for updates or re-copy the folder.

# v0.5.0 · 2026-08-10

## KO Catchup 0.5.0

### In-app updates over Wi-Fi
**Tools → KO Catchup → Settings → Check for updates** now fetches the latest release and installs it in place — no more USB copying. Your settings and cached recaps are preserved.

Built security-first, since this installs code:
- **Verified TLS only** — downloads are refused unless the connection can be verified (KOReader ships a CA bundle on all real devices); no "proceed anyway" prompt
- **Integrity-checked** against the release's published sha256 checksum before anything is installed
- **Safe install** — your working version is never touched until a complete, validated copy is staged; an interrupted or failed update leaves the installed plugin intact, and USB remains the fallback

### Install / update
First time: unzip and copy `kocatchup.koplugin` into KOReader's `plugins` folder, restart. After that, use Check for updates.

# v2.0.0 · 2026-09-26

📦 **Also available in the Storefront plugin** — open Tools → Storefront, search "CrossDrop", and tap Install. No manual file copying needed.

## CrossDrop 2.0.0

### New Features
- **Instructions page** - A dedicated instructions page accessible from the Connections tab, with a scrollable guide and back navigation
- **visibleTextOffset sync** - Precise read-position restore using the same ParagraphStreamer logic as CrossPoint's KoSync (spine + visibleTextOffset in progress.bin)
- **New crossdrop_visible.lua module** - Faithful port of CrossPoint's ProgressMapper/ParagraphStreamer (XPath parsing, visible-codepoint counting, entity resolution, zip/inflate)

### UI Improvements
- **4-tab dashboard** - Connections, Send A File, Collections, Delete Files (all inline, no modals)
- **Instructions button** on Connections landing page opens full guide with back navigation
- **Row label update**: "Set WiFi IP (may change)" makes the dynamic-vs-fixed distinction clear
- **Guide text updated** - Steps 4 & 7 clarified to distinguish dynamic IP vs router-fixed Stored Devices
- **Scrollable guide** - Instructions page uses InputContainer for scrolling on small screens

### Code Quality
- **Widget dedup** - Extracted separator(), caption(), menuRow() into shared crossdrop_widgets.lua
- **Deduped position sync** - Single maybeSyncPosition() method used by both batch and standalone sends
- **Lua scoping fix** - visibleModule() lazy loader now declared before getCrossPointPosition()
- **All 470 tests pass** - Harness guards lazy-load, byte-identical deployments

### Fixes
- Lua scoping bug where visibleModule() was nil in getCrossPointPosition() due to declaration order
- Guide text no longer overflows off-screen (scrollable Instructions page)
- Row label now indicates which IP method is dynamic vs fixed

### Version
Bumped from 1.6.0 to 2.0.0 (single source of truth in _meta.lua)

# v1.6.0 · 2026-09-20

**What's new in 1.6.0**

**Cleaned-up UI — everything now stays inside its tab.** Picking files, choosing the destination folder, and deleting all happen right below the tab bar. No more full-screen screens stacking over the dashboard; the header and tabs never leave the screen.

**Every tab has a home page.** Tapping the active tab again takes you straight back to that tab's landing page, so you can always find your way back out of the deeper menus.

**Nicer button taps.** The tap flash now fills the whole button instead of a patchy blob, and buttons keep their rounded shape after being pressed.

**Also in this release:** a more visible new app icon, icons on the tab bar, and the usual round of stability fixes. Full automated test suite green (310 checks).

# v1.5.0 · 2026-09-18

# CrossDrop 1.5.0

Duplicate detection — CrossDrop now knows when a book is already on your
Xteink reader and flags it before you ever tap send.

- **See it before you pick.** Every time you open Send A File, CrossDrop scans
  the reader's entire card and marks each book that's already there with
  "On reader" right on its row.
- **Never walked past.** Selecting a book that's already on the reader pauses
  on a "Send anyway / Don't send" confirm — so a re-send is always a
  deliberate choice, never an accident.
- **It knows a *re-send* from a *new copy*.** A match means the same file size
  and a name that keys alike — case and re-typed separators don't matter
  ("The_Name_of_the_Wind.epub" matches "The Name of the Wind.EPUB"). An
  updated or edited copy with a different size is *not* flagged, because that
  is exactly the fix you'd want to send.
- **Covered on every route.** The one-tap "Currently open" send rescans and
  guards the duplicate too, and each scan is fresh — a book you sent moments
  ago is already recognized the moment you reopen the picker.

**Install:** unzip, copy `crossdrop.koplugin/` into KOReader's `plugins/`
folder and restart KOReader — or update straight from **Storefront**.

# v1.4.3 · 2026-09-18

# CrossDrop 1.4.3

Kobo connectivity hardening — hopefully fixes the Wi-Fi probe/send hangs
users were hitting on KOReader-managed radios (Kobo).

- `NetworkMgr:runWhenConnected` now gates every send/check entry point:
  when Wi-Fi is down the link is brought up *before* probing, so the
  plugin never probes a dead interface and reads a false "Offline".
  Kindle/Android are unaffected (their fast path is synchronous and
  identical to 1.4.1).
- `UIManager:preventStandby` (pcall-guarded) held across the full probe
  and file-transfer flow so autosuspend can't tear the link mid-send.
- Probe timeout mapped to socketutil's "timed out" string so a stuck
  probe never shows a raw numeric code.
- Probe retries once (3 s then 6 s) with per-attempt logging instead of
  failing instantly on the first attempt.
- Single-ops (`rawBody` / `deleteEntry`) fail fast with a clear "Wi-Fi is
  off" message instead of attempting a doomed probe when the radio is down.

**Install:** unzip, copy `crossdrop.koplugin/` into KOReader's `plugins/`
folder, restart KOReader — or install/update from **Storefront**.

# v1.4.1 · 2026-09-18

# CrossDrop 1.4.1

Code hygiene for the 1.4.0 feature set — no behavior changes.

- Removed the unused MOBI/FB2 title parsers (the file list is
  CrossPoint-only now — they were unreachable).
- Last "book" wording replaced ("File sent" toast, "Scanning for files…",
  setup guide).
- Repository cleanup: stale version-history comments stripped, AGENTS.md
  rewritten around the current build (trees, refresh discipline, reader
  protocol facts, additive Storefront releases).

**Install:** unzip, copy `crossdrop.koplugin/` into KOReader's `plugins/`
folder, restart KOReader — or install/update from **Storefront**.

# OrbitUI for KOReader

**A customizable Home screen and a visual library, together in one KOReader plugin.**

OrbitUI combines **[SimpleUI](https://github.com/doctorhetfield-cmd/simpleui.koplugin)
by [doctorhetfield-cmd](https://github.com/doctorhetfield-cmd)** and
**[Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin)
by [AndyHazz](https://github.com/AndyHazz)**, with their contributors' work.
These projects are the foundation of OrbitUI, not just inspiration: their code,
interfaces and features are included and adapted here. Please support and credit
the original creators.

**[Download OrbitUI](https://github.com/komadorirobin/orbitui.koplugin/releases)**
| [Install](#installation)
| [Switch from SimpleUI / Bookshelf](#already-using-simpleui-or-bookshelf)
| [Feature guide](docs/FEATURES.md)
| [Report a problem](https://github.com/komadorirobin/orbitui.koplugin/issues)

> **OrbitUI replaces the standalone SimpleUI and Bookshelf plugins.**
> You do not need to install either one first. If you already use one or both,
> disable them and restart KOReader before installing OrbitUI. Never run them
> alongside OrbitUI. Keep their files and settings for backup and rollback.

## Screenshots

| Reading dashboard | Book shelves | Manga series |
| --- | --- | --- |
| [![Reading dashboard with reading progress, goals and paginated book rows](docs/screenshots/reading-dashboard.jpg)](docs/screenshots/reading-dashboard.jpg) | [![Physical bookshelf view with book covers and a framed-print ornament](docs/screenshots/book-shelves.jpg)](docs/screenshots/book-shelves.jpg) | [![Manga series boxes with MAL star ratings, read-volume counts and a motorcycle ornament](docs/screenshots/manga-series.jpg)](docs/screenshots/manga-series.jpg) |

Click a screenshot to view it full-size. This is an example **customized setup**,
not a fixed default: choose your own wallpaper, navigation buttons, sections and
layout. Ornaments are optional add-ons. The manga star ratings come from the
separate [MyAnimeList Manga Sync plugin](https://github.com/komadorirobin/myanimelist.koplugin).

## Why combine them?

SimpleUI provides a modular Home screen, reading statistics and navigation bars.
Bookshelf provides a visual library with shelves, covers, lists, series, book
details and themes. OrbitUI connects those experiences: go from your Home page
to a shelf, open the same book-detail panel from either place, pin shelves to
Home and search your library through one interface.

The aim is a coherent reading interface with **one installation, one settings
hub and one update channel**, while retaining the flexibility of both projects.
It is not a new reading engine, a replacement for KOReader itself, or an official
release by either upstream author.

## What you get

| Part | What it provides |
| --- | --- |
| **SimpleUI foundation** | Modular Home and Custom Screens, reading statistics/goals, navigation and quick actions, wallpapers and layout customization. |
| **Bookshelf foundation** | Visual shelves, cover grids and lists, book details, filtering/grouping, series boxes, themes and ornaments. |
| **Shared OrbitUI interface** | Connected Home/library navigation, shared book details and scoped search, shelf rows or carousels pinned to Home, and unified settings. |
| **Your own library structure** | Name and configure sections, folders, shelves and bottom-bar buttons. No required fiction/manga split or hard-coded personal folder setup. |
| **Optional Reading dashboard** | Continue reading, statistics, goals and book rows, with configurable cards, headings and sources. Choose greyscale, colour accents or tinted cards; each book row has arrows and swipe navigation. |
| **Shelf refinements** | Per-shelf cover size and captions, optional above-cover labels, Hardcover/Paperback/Kanzenban bindings, and aspect-preserving series covers with naturally sized spines. |
| **Optional ornament add-ons** | Browse, install and update packs inside OrbitUI, separately from plugin updates. Author/series matching is the default; random placement is also available. |
| **One update channel** | Verified full-plugin OTA updates with restart activation and code rollback. Embedded SimpleUI and Bookshelf do not update separately. |

These are additions and integration choices on top of substantial upstream
functionality, not a claim that OrbitUI invented the Home screen, library,
series boxes, themes or ornament system. [The feature guide](docs/FEATURES.md)
explains the extra controls and where to find them.

### Local books first, online services optional

You can use OrbitUI with ordinary local books, KOReader collections, local
reading goals and no online account. BookOrbit, Hardcover and MyAnimeList are
optional integrations, not requirements.

BookOrbit synchronization, MyAnimeList and Patch Manager remain separate
plugins where used. OrbitUI does not replace them, download your whole server
library or introduce a new synchronization engine.

### Choose the look

Keep each shelf's own settings, choose **Classic OrbitUI** for face-out books
and compact series boxes, or choose **Minimal bookshelf** without ornaments.
The Home layout is configured separately.

Ornaments are **not bundled or automatically installed** on a fresh setup.
Install only the packs you want through **OrbitUI settings > Add-ons >
Ornament add-ons**. Existing artwork is retained. Packs have their own credits
and licenses, including some noncommercial licenses; they are not all covered
by the code license. See [add-on instructions](docs/ADDONS.md).

## Installation

**Requirements:** KOReader **v2025.08 or newer**; v2026.03 or newer is recommended
by Bookshelf. Keep KOReader's **Cover browser** plugin enabled. Beta 18 is a
prerelease, not a promise of compatibility with every device or user patch.

1. **Back up first.** Keep a copy of your KOReader settings, user patches,
   custom artwork and working plugins. Preserve book sidecars/reading data
   separately too. See [backup details](docs/MIGRATION.md#what-is-preserved).
2. **If SimpleUI or Bookshelf is installed, disable it in KOReader's plugin
   manager and restart KOReader.** Disable both if you have both. Do not delete
   their settings or plugin folders.
3. Download **`orbitui.koplugin.zip`** from the
   [Beta 18 release](https://github.com/komadorirobin/orbitui.koplugin/releases/tag/v0.1.0-beta.18).
   Do **not** use **Code > Download ZIP** or GitHub's **Source code** archives.
4. Fully exit KOReader. Extract the ZIP and copy its **`orbitui.koplugin`**
   folder into your KOReader **`plugins/`** directory.
5. Start KOReader. Enable OrbitUI in the plugin manager and restart if needed.
   On a fresh setup, the guide helps you choose folders, a start screen and
   bottom-bar buttons. Nothing in the guide is applied until you confirm.
6. Open **Tools > OrbitUI > OrbitUI settings** to customize it. Existing
   SimpleUI/Bookshelf users keep their configuration rather than receiving an
   automatic setup prompt; open **Setup guide** manually when wanted.

Typical plugin locations (use the location of your actual KOReader installation):

| Device | Plugins directory |
| --- | --- |
| Kobo | `.adds/koreader/plugins/` |
| Kindle | `koreader/plugins/` |
| PocketBook | `applications/koreader/plugins/` |
| Android | `koreader/plugins/` in internal storage |

The resulting path must be **`plugins/orbitui.koplugin/main.lua`**, not
`plugins/orbitui.koplugin/orbitui.koplugin/main.lua`. Do not install the folders
under `components/` as separate plugins.

**Already using OrbitUI?** Use **Tools > OrbitUI > Uppdatera OrbitUI**
(the updater's current label), enable preview releases, update and restart.
Do not install SimpleUI or Bookshelf updates inside OrbitUI. For manual updates
of an existing OTA installation, read [the recovery guide](docs/OTA.md) first.

### Installing through a community app store

OrbitUI is discoverable by KOReader app stores through its GitHub repository
name and the `koreader-plugin` topic. These stores are independent projects;
being listed does not mean that their maintainers have reviewed or endorsed
OrbitUI. Their local catalogs may need refreshing.

**[AppStore by omer-faruq](https://github.com/omer-faruq/appstore.koplugin):**
after the backup and predecessor-disable steps above, find
`komadorirobin/orbitui.koplugin`. In its download options, choose
**Other releases...**, uncheck **Filter pre-releases**, select
**v0.1.0-beta.18**, then select **`orbitui.koplugin.zip`**. Restart KOReader
after installation. Preview builds are not returned by GitHub's "latest stable release"
endpoint, so the default latest-release lookup may report that none exists.
Do not choose **Direct download from repo**, **Source code**, the checksum
file, or the add-on-only **ornaments-1** release.

**[Storefront by ultimatejimmy](https://github.com/ultimatejimmy/storefront.koplugin):**
use **26.10.20 or newer**, which includes the
[embedded-plugin detection fix](https://github.com/ultimatejimmy/storefront.koplugin/releases/tag/26.10.20).
Find `komadorirobin/orbitui.koplugin` and choose **v0.1.0-beta.18** and
**`orbitui.koplugin.zip`** from its versions/releases options if the cached
catalog still shows an older beta. Disable the predecessor plugins first as
described above. Older affected installers (including **26.10.17-beta2**) can
mistake embedded SimpleUI for the outer plugin and overwrite `simpleui.koplugin`;
use the manual ZIP instructions rather than those versions.

These instructions concern **first installation**. For subsequent OrbitUI
updates, **OrbitUI's own updater remains the recommended path**. Install Beta 2 or later
through it first: Beta 1 and earlier cannot detect an externally overwritten root
while an older OTA version remains active.

Beta 2 adds verified import of subsequently installed, newer external **release
ZIPs**, preserving the active OTA snapshot for rollback. An extra restart is
required to adopt the verified snapshot. Storefront also needs its own installer
fix as described above, and real-device testing of the external-import flow is
still pending. See [external-update compatibility](docs/OTA.md#external-updates-beta-2-and-later).

In-app ornaments are managed separately under **OrbitUI settings > Add-ons**.
Their [distribution repository](https://github.com/komadorirobin/orbitui-addons)
is separate from plugin releases. Existing packs and settings are preserved;
older catalog downloads remain available for previous OrbitUI versions.

## Already using SimpleUI or Bookshelf?

**Your existing data is not intentionally wiped or moved.** OrbitUI reuses
SimpleUI's settings and recognizes both the older and current Bookshelf settings
locations. It reads existing ornament folders in place. Normal preference edits
use the selected existing stores, rather than a separate one-time imported copy.

Before its first component startup, OrbitUI also makes a **limited settings
snapshot** in `settings/orbitui/before-first-run/`. A failed snapshot blocks
startup. This is **not a full backup**: ornament images, wallpapers, books,
sidecars, databases and other plugins' settings are not copied by that snapshot.

If both old and new Bookshelf settings files exist, the older flat location
wins to protect existing OrbitUI installations. The other copy is left untouched,
not merged. Read [the migration guide](docs/MIGRATION.md) before proceeding if
you have two different configurations.

Existing Home pages and configured integrations are retained. OrbitUI-specific
options and later upstream setting formats may not be understood by older
standalone versions. Visual behavior can differ; custom patches are not
guaranteed compatible. For rollback, **disable OrbitUI and restart before
re-enabling your old plugins**. Never restore stale reading-progress files just
to undo a UI change.

## Beta status and feedback

**0.1.0-beta.18** fixes status taps being intercepted by Home's top menu,
applies the quick-control opt-in immediately and keeps unanchored quick-control
dialogs native so tabs, Close and Wi-Fi actions can respond. Existing custom
gestures and modal/lifecycle safety remain. No new upstream import or hardware
light driver is included; the optional Bigme compatibility userpatch is separate.
See [Beta 18 notes](docs/OTA.md#orbitui-010-beta18) for English/Swedish details.
Physical Boox/Bigme input and system-return retesting remains required.

**0.1.0-beta.17** adds large bilingual settings-category cards and shared
light/Wi-Fi/battery/time quick controls. Open **OrbitUI settings > Navigation &
interface > Quick controls**; status-field taps are opt-in and the same action
can be added to a bar without replacing saved buttons. Supported light controls
use native ranges; Android Wi-Fi opens system settings. The reviewed October 30
upstream changes also add optional grid quick actions, six-column book rows,
menu hiding, page-turn statistics and Tiny Critter options. Existing profiles,
safe-mode covers, fast reader return and external integrations are retained.
See [Beta 17 notes](docs/OTA.md#orbitui-010-beta17) for SV/EN controls, upgrade/
rollback details and outstanding physical-device checks. No new upstream import
is performed by this release, and no measured device-speed claim is made.

**0.1.0-beta.16** adds demand-driven Reading dashboard data, optional Adaptive
memory / Responsive profiles, local performance reports and a bilingual
Home/Bookshelf quick guide. Existing behaviour remains the default. The runtime
package is smaller without dropping languages, images or licenses, and verified
obsolete update-code snapshots can be cleaned after healthy startup while
factory/current/rollback and user data remain protected. See [Beta 16 notes](docs/OTA.md#orbitui-010-beta16)
for controls, tradeoffs and remaining physical-device checks. No new upstream
import or measured device-speed claim is included.

**0.1.0-beta.10** integrates **Bookshelf 6.0.2**: explicit metadata refresh
now discards stale batch rows so books/covers can be re-extracted, colour-cover
shadows stay clipped, status updates use the measured strip and clock ticks
avoid refreshing beneath other windows. Micro-modules gain public book actions
and keyboard access to their fullscreen editor. SimpleUI and the working
Home/Bookshelf navigation fixes are retained. No automatic rescan or data reset.
See [the Beta 10 notes](docs/releases/0.1.0-beta.10.md); physical cover/repaint/
module-key and broader Bigme checks remain open.

**0.1.0-beta.9** makes **Bookshelf** a direct navigation action and a removable
default button on new setups. Existing bars are kept: open **OrbitUI settings >
Bookshelf navigation** to enable it and choose a profile, or long-press the
Bookshelf button. Each library section can also be added as its own button;
profiles retain their independent folders and chips. Missing old `prose`/`comics`
targets now explain the problem instead of silently doing nothing. No settings
reset or custom dispatcher action is required. See
[the Beta 9 notes](docs/releases/0.1.0-beta.9.md).

**0.1.0-beta.8** fixes the missing `Blitbuffer` import in Home's shared screen
engine. This caused `sui_screen_engine.lua:288` to fail while loading Home,
including after Beta 7. New tests load the entire engine without ambient globals,
then exercise Home and Custom Screen opening with native rendering stubbed.
Update and restart; no settings reset is needed. Physical-device retesting is
still required. See [the Beta 8 notes](docs/releases/0.1.0-beta.8.md).

**0.1.0-beta.7** fixes a reproduced first-run Home crash caused by a missing
logger import. Home load/open failures now show the actual error and log its
traceback instead of only reporting that Home is unavailable. Failed partial
Home windows are closed without resetting settings or scheduling an automatic
retry. This is not confirmation that every reported Android native crash is
resolved; physical-device retesting remains required. See
[the Beta 7 notes](docs/releases/0.1.0-beta.7.md).

**0.1.0-beta.6** integrates reviewed **Bookshelf 6.0.0** and newer **SimpleUI 3.0**
Git commits. Bookshelf adds a micro-module layout editor, Shelf/Ornament modules
among books, pinned ornaments, per-card colours, Highlights in book details and
persistent derived caches. Its editor is separate from SimpleUI's Home/Bento
editor. SimpleUI adds a shared daily-statistics ledger and display fixes.

Existing Home/Bento layouts, scoped shelves, series-box bindings and cover
proportions, author/series ornaments and optional external integrations are
retained. SimpleUI's real Git history now accounts for the previously reviewed
3.0 ZIP; provenance remains documented in [the upstream workflow](docs/UPSTREAM.md).
See [the Beta 6 notes](docs/releases/0.1.0-beta.6.md) for upgrade and rollback details.

The existing reader setup, upgrades and ornament menu were tried on the
maintainer's device before Beta 1. Automated tests cover Lua and LuaJIT,
integration, packaging and the OTA installer, including external-update
snapshots and rollback. The new module migrations/editor, pinning, Highlights,
colours/underlay restoration and external-plugin interactions still need physical
Bigme testing. Cache changes are not a measured device speedup. This remains a
prerelease, not an exhaustive device/fresh-install compatibility certification.

Please report your device, KOReader version, OrbitUI version and steps to
reproduce a problem in [OrbitUI issues](https://github.com/komadorirobin/orbitui.koplugin/issues).
Report integration problems here first, not as presumed bugs in SimpleUI or
Bookshelf. Redact tokens, account details and private paths from logs; do not
upload settings backups.

## Credits and licenses

- **SimpleUI:** [doctorhetfield-cmd and contributors](https://github.com/doctorhetfield-cmd/simpleui.koplugin),
  [GPL-3.0 license](components/simpleui/LICENSE). The original MIT notice is
  [retained](components/simpleui/LICENSE-MIT-ORIGINAL.txt) for previously imported code.
- **Bookshelf:** [AndyHazz and contributors](https://github.com/AndyHazz/bookshelf.koplugin),
  [AGPL-3.0 license](components/bookshelf/LICENSE).
- **OrbitUI integration and customizations:** [komadorirobin](https://github.com/komadorirobin),
  [AGPL-3.0](LICENSE). This is an independent project, not an upstream endorsement.
- **Icons and artwork:** their original creators retain credit and separate
  licenses. See [icon credits](docs/ICONS.md) and each ornament pack's
  **Credits and licenses**. Free download does not make every asset public domain.

Both component licenses, notices and imported Git histories are retained.
Beta 9 integrates Bookshelf **6.0.0** and SimpleUI **3.0**; exact imported and
reviewed upstream revisions are recorded in [sources.json](sources.json).
Upstream updates are reviewed and merged, not automatically installed.

## Development

Run `sh scripts/test.sh` and `LUA=luajit sh scripts/test.sh`, then
`sh scripts/check-translations.sh`. Build a runtime ZIP from a clean committed
revision with `sh scripts/package.sh`.

Integration code lives in `core/` and `adapters/`; the original components live
under `components/`. See the [project context](docs/PROJECT_CONTEXT.md),
[integration contracts](docs/INTEGRATION_CONTRACTS.md),
[upstream workflow](docs/UPSTREAM.md), [merge history](docs/MERGE_LOG.md),
[testing](docs/TESTING.md) and [OTA/recovery](docs/OTA.md).
The upstream watcher reports changes only; it never merges or publishes.

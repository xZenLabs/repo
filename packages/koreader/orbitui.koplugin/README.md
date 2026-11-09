# OrbitUI for KOReader

**Make your library feel like yours.** A customizable Home screen, visual
bookshelves and a connected reading workflow — together in one KOReader plugin.

OrbitUI brings together **[SimpleUI](https://github.com/doctorhetfield-cmd/simpleui.koplugin)
by [doctorhetfield-cmd](https://github.com/doctorhetfield-cmd)** and
**[Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin)
by [AndyHazz](https://github.com/AndyHazz)**, with their contributors' work.
Their code, interfaces and features are OrbitUI's foundation, not just
inspiration. OrbitUI adds a shared workflow and its own optional features on
top. Please support and credit the original creators.

**[Download stable 1.1.0](https://github.com/komadorirobin/orbitui.koplugin/releases/tag/v1.1.0)**
| [Installation](#installation)
| [What OrbitUI adds](#what-orbitui-adds)
| [Feature guide](docs/FEATURES.md)
| [Report a problem](https://github.com/komadorirobin/orbitui.koplugin/issues)

**Trying the next version?** [1.2.0-beta.1](https://github.com/komadorirobin/orbitui.koplugin/releases/tag/v1.2.0-beta.1)
integrates Bookshelf 6.4.1: lighter cover/metadata work, optional book-size and
series-box styles, and Decades browsing. It preserves OrbitUI's sections, Home,
tags and integrations. New-device/layout/performance checks are still pending;
**1.1.0 remains the stable release**. See the release notes before switching.

> **OrbitUI replaces the standalone SimpleUI and Bookshelf plugins.**
> Neither is required separately. If either is installed, disable it and restart
> KOReader before installing OrbitUI. Never run them alongside OrbitUI. Keep
> their files and settings for backup and rollback.

## A look around

| Reading dashboard | Book shelves | Manga series |
| --- | --- | --- |
| [![Reading dashboard with reading progress, goals and paginated book rows](docs/screenshots/reading-dashboard.jpg)](docs/screenshots/reading-dashboard.jpg) | [![Physical bookshelf view with book covers and a framed-print ornament](docs/screenshots/book-shelves.jpg)](docs/screenshots/book-shelves.jpg) | [![Manga series boxes with MAL ratings, read-volume counts and an ornament](docs/screenshots/manga-series.jpg)](docs/screenshots/manga-series.jpg) |

Click a screenshot to view it full-size. These show a **customized setup**, not
a fixed default. Choose your own sections, wallpaper, navigation and layout.
Ornaments are optional add-ons; manga ratings use the separate
[MyAnimeList Manga Sync plugin](https://github.com/komadorirobin/myanimelist.koplugin).

## What OrbitUI adds

SimpleUI supplies the modular Home, statistics and navigation; Bookshelf supplies
the visual library, book details, themes and ornament system. OrbitUI connects
them, then adds ways to organize and explore your books that are not part of
either standalone project's default setup.

- **One connected interface.** Move between Home and your library with a shared
  bottom bar, book-detail panels, scoped search and a settings hub. Pin a shelf
  to Home as a book row or carousel.
- **A Reading dashboard you can build on.** Combine Continue reading, progress,
  statistics, goals and paginated book rows. Add compatible plugin cards,
  shortcuts or BookOrbit shelf cards; arrange and size them independently.
- **Tags that lead somewhere.** Find local EPUBs with the same tag, switch
  between **Series / Volumes**, and turn combinations of tags into smart shelf
  chips. Results take you to a book's shelf preview, not straight into reading.
- **Your own library sections.** Give novels, manga, comics or any other library
  independent folders, names, shelf chips and navigation buttons. No required
  fiction/manga split or personal folder structure.
- **Optional BookOrbit connections.** Local and server-backed Want to Read
  modules, shelf/smartscope cards, online tags and guarded reading-status import.
  Each has clear controls; ordinary local books work without an account.
- **A reading companion beside your book.** The optional **Currently reading +
  Silverfish** card combines your active companion with the book cover, title
  and progress. It is an extra choice, not a replacement for Continue reading.
- **Shelf details with character.** Classic OrbitUI and Minimal bookshelf
  presets, per-shelf captions and bindings, proportion-preserving series covers,
  optional MAL badges and separately installable ornament packs.
- **Practical controls and updates.** Custom Android-app shortcuts, shared quick
  controls, optional performance profiles and whole-plugin verified OTA updates
  with code rollback.

These are OrbitUI additions and integration choices, not a claim that OrbitUI
invented modular Home screens, shelves, series boxes, themes or ornaments.
[The feature guide](docs/FEATURES.md) explains the controls and their boundaries.

## Explore by tags, not just folders

Open a book's **Tags** tab to browse its embedded EPUB tags. Tap a tag to find
other matching books across your configured local libraries — entirely offline,
without BookOrbit or a server patch. This uses embedded **`bookorbit:tags`**
metadata; ordinary EPUB subjects remain Bookshelf's genres, not a duplicate
tag source.

For manga, **Series / Volumes** tabs let you discover a series without scrolling
past every volume. Selecting a series highlights its first locally indexed
available volume on the shelf; standalone and metadata-incomplete books remain
visible. Tapping a result shows the cover and description without opening the
reader. Long-press still opens book details.

Long-press a local tag to create a named **smart chip**. Combine up to 16 exact
tags using **AND / OR**, scoped to one library or all local libraries. A chip
uses cached tags; refreshing its matches reads missing or changed files. Pin
it to Home just like another supported shelf. No book is moved or edited.

For a complete initial pass or after bulk retagging, use **OrbitUI settings →
Bookshelf → Tags and indexing**:

- **Update tag index** reads new/changed files and retries failures.
- **Reread all EPUB tags…** confirms a fresh read of the configured EPUBs.
- Pause and continue across restarts; sleep or closing the page pauses the job
  and preserves completed reads. Keep KOReader open on the page while indexing.

Indexing has no 400-file limit. Individual tag result/chip views show at most
400 matches and disclose **400+** when capped; an incomplete index is labelled.
Library roots and configured scan depth determine coverage.

## Make Home useful to you

The optional **Reading dashboard** adds a Home page without replacing your
existing pages. Choose its cards, headings, colours, order and row sources:
local To Be Read, new books, history, collections, saved shelves or BookOrbit.
Each book row has its own paging arrows and swipe navigation.

Use **+ → Add module…** or **Cards and content** for compatible SimpleUI and
Bookshelf plugin cards or action shortcuts. Added cards have independent sizes
and positions; extra content gets dashboard pages rather than ever-smaller
text. Removing a card removes its placement, not the plugin or its data.
Third-party cards still depend on their own plugin and supported APIs.

**Get more modules…** opens a small curated **Module library**, initially with
the pinned official **Silverfish 2.0.0** release. Installation requires explicit
confirmation and restart. Existing plugin folders are never overwritten;
updates/removal stay manual. A compatibility badge describes the reviewed
version and adapter tests, not a guarantee that arbitrary later versions or
every device are safe. [Catalog and trust details](docs/ADDONS.md).

With Silverfish installed and enabled, add **Currently reading + Silverfish**
as another module: companion on the left, reading information in the middle,
book cover on the right. Tap the companion to open Silverfish, or the book to
resume reading. OrbitUI uses its public APIs without copying creature artwork,
changing saves or maintaining a Silverfish fork. Continue reading stays intact.

On Android, long-press **Android apps → Apps** to add, remove, rename and reorder
shortcuts to installed apps. More apps get page arrows; removing a shortcut does
not uninstall the app. An optional **Settings shortcut → Developer options**
destination is saved separately. Discovery runs only when adding apps, not
every time Home is drawn.

## Find your place faster

Shared **Search OrbitUI** can target all libraries, a configured section or a
supported current shelf. Optional **Word suggestions** complete words from
already cached local titles, authors and series. They do not scan EPUBs or call
the network as you type; cold-cache coverage can be incomplete.

The optional per-view **Alphabet strip** lets you tap or drag through the
current supported sort/filter. It uses spare right-margin space and keeps
Å/Ä/Ö distinct. Enable it through **footer counter ▾ → Sort, filter & view →
Alphabet strip**. Unsupported layouts/sorts hide it rather than jumping to
unrelated books. Both the strip and word suggestions are off by default.

## BookOrbit, when you want it

Use **OrbitUI settings → Integrations → BookOrbit** for the master switch and
individual controls. Disabling OrbitUI's integrations preserves source choices,
layouts and cached data; it does **not** turn off the separate BookOrbit
plugin's own reading-progress sync.

| Feature | What it needs / does |
| --- | --- |
| **Want to read [Local]** | KOReader's local To Be Read collection. No account or network. |
| **Want to read [BookOrbit]** | The connected BookOrbit plugin; matches its server list to local files. No extras server patch or downloads. |
| **BookOrbit shelf / smartscope cards** | A connected plugin/server with native catalog and background APIs. Add multiple sources through dashboard **+ → BookOrbit shelves and smartscopes**. Exact linked files already on the device only; cached-first refresh, no new extras patch. |
| **Manual Want to Read actions** | Explicit add/remove actions for a linked book. These change the server list/status, unlike passive cards. |
| **Online tags** | A compatible optional server tag API extension. Explicit load/refresh; matches linked local books, not server-only books. Offline EPUB tags need none of this. |
| **Import reading status — experimental** | Off by default. Requires the separate **read-statuses v1** server extension. GET-only import for linked local books; not reading-position sync or a second automatic remote writer. |
| **Undo accidental opening** | A separate device patch and version-compatible server extension. Not bundled with or enabled by OrbitUI. |
| **Hardcover single-writer compatibility** | A separate optional device patch lets BookOrbit remain the automatic Hardcover writer while retaining Hardcover linking/edition/metadata tools. |

Local and BookOrbit Want to Read are **separate modules**, never silently
substituted for one another. Shelf/smartscope rules run on the server; cards
show cached results first and refresh visible cards asynchronously, at most
every 15 minutes. They do not download missing books or write reading status.

Status import protects open books, pending undo and newer/ambiguous local
changes. It does not reset unread books, replace reading positions/history or
resolve conflicts automatically. **Status check details** explains skipped
counts; filename examples remain session-local and are not uploaded.

[BookOrbit Extras](https://github.com/komadorirobin/bookorbit-extras) contains
the separately installable patches/server extensions, exact supported server
bases and English/Swedish instructions. An administrator must build, test and
deploy compatible server changes. **An OrbitUI update never deploys them.**
An extension for one exact BookOrbit release is not a promise of compatibility
with all newer releases. Do not remove undo support while an opening is protected.

BookOrbit sync, Hardcover, MyAnimeList and Patch Manager remain separate plugins
where used. OrbitUI does not replace them or introduce a new automatic sync
engine. Local books, tags, collections and local reading goals need no account.

## Choose the look — keep your setup

Follow each shelf's own preferences, choose **Classic OrbitUI** for face-out
books and compact eligible series boxes, or **Minimal bookshelf** without
ornaments. Presets do not reset Home, wallpaper, icons or saved shelf choices.
Configure per-shelf cover size, captions/placement, book binding and series
title plates. Bindings include Hardcover, Paperback and Kanzenban/large format;
series-specific overrides and naturally sized spines preserve cover proportions.
These are visual treatments, not changes to book metadata.

Optional **MyAnimeList** integration adds cached community ratings to linked
manga boxes. Shared icon pickers add Material Symbols Rounded, Solar and Tabler
choices, including Solar Colour/Mono artwork. [Icon credits](docs/ICONS.md).

**Add-ons → Ornament add-ons** offers separately downloadable packs — Manga,
Japan, Ukiyo-e Gallery, Modernists, Authors and Authors II — with previews and
their own updates. Match author/series ornaments to books, or choose random
placement. Supported pieces have enlarged information cards in Swedish/English.
No packs are automatically installed on a fresh setup; existing artwork stays.
Artwork licenses differ, including some noncommercial terms; they are not all
covered by the code license. [Add-on instructions and credits](docs/ADDONS.md).

Shared quick controls provide supported native light controls, Wi-Fi, battery
and time actions. Status-field taps are opt-in; Android Wi-Fi opens system
settings. Hardware light-driver fixes, where needed, remain separate patches.
Optional **Adaptive memory / Responsive** profiles trade cache/preloading for
memory or responsiveness without changing image quality or saved cache budgets.
Local performance reports help diagnose slow views; they are not a universal
device-speed promise.

## Installation

**Requirements:** KOReader **v2025.08 or newer**; **v2026.03 or newer** is
recommended by Bookshelf. Keep KOReader's **Cover browser** plugin enabled.

1. **Back up first:** settings, working plugins, patches, custom artwork and
   book sidecars/reading data. [What to preserve](docs/MIGRATION.md#what-is-preserved).
2. Disable standalone **SimpleUI and Bookshelf**, if installed, and restart
   KOReader. Keep their files and settings for rollback.
3. Download **`orbitui.koplugin.zip`** from the
   [stable 1.1.0 release](https://github.com/komadorirobin/orbitui.koplugin/releases/tag/v1.1.0).
   Do not use **Code → Download ZIP**, **Source code**, checksum files or an
   ornament-only release.
4. Fully exit KOReader. Extract the ZIP and copy **`orbitui.koplugin`** into
   its **`plugins/`** directory.
5. Start KOReader, enable OrbitUI if needed and restart. On a fresh setup, the
   optional guide reviews folders, start screen, navigation buttons and preset
   before applying anything. Existing users keep their configuration.
6. Open **Tools → OrbitUI → OrbitUI settings** to make it yours.

| Device | Typical plugins directory |
| --- | --- |
| Kobo | `.adds/koreader/plugins/` |
| Kindle | `koreader/plugins/` |
| PocketBook | `applications/koreader/plugins/` |
| Android | `koreader/plugins/` in internal storage |

Use your actual KOReader installation's location. The result must be
**`plugins/orbitui.koplugin/main.lua`**, not a doubly nested folder. Do not
install the folders under `components/` as separate plugins.

**Already using OrbitUI?** Its **Uppdatera OrbitUI** menu is the recommended
update path. Choose **stable** for releases or opt into **preview** for betas,
update, then restart. Embedded SimpleUI/Bookshelf never update independently.
Updates verify the full package and support restart activation/code rollback;
code rollback does not restore stale reading-progress files.
[OTA and manual recovery](docs/OTA.md).

### Already using SimpleUI or Bookshelf?

OrbitUI reuses the existing settings and recognizes old/current Bookshelf
locations; ornament folders are read in place. If both settings locations
exist, the older flat location takes priority and the other is left untouched,
not automatically merged. Read [the migration guide](docs/MIGRATION.md) first
if those copies differ.

Before first component startup, a limited snapshot goes into
`settings/orbitui/before-first-run/`; a failed snapshot blocks startup. This is
**not a full backup** of books, sidecars, databases, artwork or other plugins.
Older standalone versions may not understand newer settings. To switch back,
disable OrbitUI and restart before re-enabling the old plugins. Never run both.

### Community app stores

Independent stores can find **`komadorirobin/orbitui.koplugin`**. Choose the
**v1.1.0** release and **`orbitui.koplugin.zip`**, not a repository/source ZIP
or an add-on release. Their listing is not an endorsement or compatibility
certification; refresh a stale catalog or install manually.

For [Storefront](https://github.com/ultimatejimmy/storefront.koplugin), use
**26.10.20 or newer**: older affected installers can mistake embedded SimpleUI
for the outer plugin. [AppStore](https://github.com/omer-faruq/appstore.koplugin)
also offers release selection. Disable predecessor plugins before either
installation. For subsequent updates, prefer OrbitUI's own updater; consult
[external-update recovery](docs/OTA.md#external-updates-beta-2-and-later) before
manually overwriting an existing OTA installation.

## Stable 1.1 and what's next

**1.1.0** promotes the user-accepted beta.12 runtime unchanged. Its highlights
include series-level tag results, the alphabet strip, optional word suggestions,
cover reuse, plugin/module-library support, BookOrbit shelf/smartscope cards and
Currently reading + Silverfish. Continue reading, saved placements and data stay
intact. Bookshelf 6.4 changes belong to the separate **1.2 preview cycle**, not
the frozen 1.1 release. [Release notes and history](docs/OTA.md#orbitui-110).

**Svenska:** OrbitUI samlar Hem och bokhyllan i ett plugin, med bland annat
Läsöversikt, egna bibliotekssektioner, lokala taggar/smarta taggchip, Serier/
Volymer, bokstavslist, valfria pluginmoduler och Läser just nu + Silverfish.
BookOrbit är frivilligt: Vill läsa [Lokalt] och Vill läsa [BookOrbit] är skilda
källor, och hyllor/smartscopes kan visas som egna kort. Vissa onlinefunktioner
kräver separata tillägg; vanliga lokala böcker och EPUB-taggar gör det inte.
Stabil 1.1 behåller den godkända beta.12-koden. Upstream-nyheter provas i 1.2-beta.

Automated Lua/LuaJIT, native-fixture, packaging and update/rollback checks
complement user testing. Stable does not certify every device, third-party
patch, optional integration or recovery scenario. Some optional features remain
experimental as marked. [Test evidence and remaining checks](docs/TESTING.md).

Report your device, KOReader/OrbitUI versions and reproduction steps in
[OrbitUI issues](https://github.com/komadorirobin/orbitui.koplugin/issues),
including integration problems, rather than presuming an upstream bug.
Redact tokens, account details and private paths; do not upload settings backups.

## Credits and licenses

- **SimpleUI:** [doctorhetfield-cmd and contributors](https://github.com/doctorhetfield-cmd/simpleui.koplugin),
  [GPL-3.0 license](components/simpleui/LICENSE). The original MIT notice is
  [retained](components/simpleui/LICENSE-MIT-ORIGINAL.txt) for previously imported code.
- **Bookshelf:** [AndyHazz and contributors](https://github.com/AndyHazz/bookshelf.koplugin),
  [AGPL-3.0 license](components/bookshelf/LICENSE).
- **OrbitUI integration and customizations:** [komadorirobin](https://github.com/komadorirobin),
  [AGPL-3.0](LICENSE). Independent project, not an upstream endorsement.
- **Icons and artwork:** original creators retain credit and separate licenses.
  See [icon credits](docs/ICONS.md) and each pack's **Credits and licenses**.
  Free download does not make every asset public domain.

Both component licenses, notices and imported Git histories are retained.
[sources.json](sources.json) records the exact imported/reviewed revisions;
release numbers are not source pins. Updates are reviewed, never auto-merged.

## Development

Run `sh scripts/test.sh`, `LUA=luajit sh scripts/test.sh` and
`sh scripts/check-translations.sh`. Build the runtime ZIP from a clean committed
revision using `sh scripts/package.sh`.

Integration code lives in `core/` and `adapters/`; component sources live under
`components/`. See [project context](docs/PROJECT_CONTEXT.md),
[integration contracts](docs/INTEGRATION_CONTRACTS.md),
[upstream workflow](docs/UPSTREAM.md), [merge history](docs/MERGE_LOG.md),
[testing](docs/TESTING.md) and [OTA/recovery](docs/OTA.md).
Upstream monitoring reports changes only; it never merges or publishes.

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

**1.0.0-rc.2 — release candidate, not stable 1.0.** Feature freeze continues.
Fixes the reproduced tag-search/index dialog retirement bug: Close remains
usable, sleep pauses work without automatic restart, and completed tag reads
are kept. Tag-result title taps now select the book on its real shelf with its
cover/description instead of opening the reader; long-press still opens details.
Existing Home/Manga, profiles, artwork and optional integrations remain. No
upstream import, reading-data migration, sync change or server deployment.
Use the **preview channel** and restart KOReader after updating. Physical
Bigme/Boox sleep/wake, complete large-library indexing, shelf-reveal presentation
and on-device update/recovery checks remain open.
[RC scope and test plan](docs/OTA.md#orbitui-100-rc2).

**Svenska: 1.0.0-rc.2 är en testkandidat, inte stabil 1.0.** Funktionsfrysen
fortsätter. Fixar den återskapade låsningen i taggsökning/indexering: Stäng
fungerar även när vyn blivit inaktuell, vila pausar utan automatisk återstart
och redan lästa taggar behålls. Titeltryck i taggträffar markerar nu boken i rätt
bokhylla med omslag/beskrivning i stället för att öppna läsvyn. Långtryck öppnar
fortfarande bokdetaljer. Hem/Manga, profiler, bilder och integrationer behålls;
ingen upstream-merge, läsdatamigrering, synkändring eller serverdriftsättning.
Uppdatera via **förhandskanalen** och starta om KOReader. Fysiska Bigme/Boox-
tester av vila/uppvakning, full indexering, markerad bok och uppdatering/
återställning återstår.

You can use OrbitUI with ordinary local books, KOReader collections, local
reading goals and no online account. BookOrbit, Hardcover and MyAnimeList are
optional integrations, not requirements.

BookOrbit synchronization, MyAnimeList and Patch Manager remain separate
plugins where used. OrbitUI does not replace them, download your whole server
library or introduce a new synchronization engine.

### Android apps (Beta 26)

Long-press the **Android apps** module (previously **App Launcher**) and open
**Apps > Add app…** to choose a launcher app installed on the device. Tap a
selected app in that list to rename it, move it before/after a named neighbour,
or remove its shortcut. Removing a shortcut does not uninstall the Android app.
The numbered list shows the current order; extra apps get page arrows rather
than being squeezed into one row. Choices are saved locally for this device
and shared by this module's Home/custom pages. No account or server is needed.

Existing enabled modules retain the six legacy shortcuts until edited. A
newly enabled module starts empty; tap its **Add Android apps…** placeholder
to configure it. An explicitly emptied list stays empty after restart. Normal
SimpleUI module long-press settings still apply. If Android does not expose an
app in the picker, **Add by package name…** remains available. App discovery
runs only when you ask to add an app, never during Home painting. The list is
bounded to 128 selected apps. The separate Settings destination choice stays
saved even if you remove and re-add the Settings shortcut.

**Svenska:** Långtryck på **Android-appar** (tidigare **App Launcher**) och välj
**Appar > Lägg till app…**. Tryck på en vald app för att byta namn, flytta den
före/efter en namngiven granne eller ta bort genvägen. Android-appen avinstalleras
inte. Numreringen visar ordningen och fler appar får sidpilar. Valen sparas
lokalt på enheten och delas mellan modulens Hem- och anpassade sidor.
Befintliga aktiva moduler behåller sina val; nya börjar tomma. Tryck på
**Lägg till Android-appar…** i en tom modul för att konfigurera den. En tömd
lista förblir tom efter omstart. Vanliga SimpleUI-inställningar för långtryck
gäller. **Lägg till med paketnamn…** finns om en app saknas i Androids lista.
Målet för Inställningar-ikonen behålls även när genvägen tas bort och läggs till
igen. Funktionen ingår i Beta 26.

### Optional BookOrbit features

**Beta 28 (experimental):** **Integrations > BookOrbit > Import reading
status from BookOrbit** adds an off-by-default, deferred GET-only importer for
saved device matches. Automatic attempts are throttled to 15 minutes; Update
now and the last successful check are available in the same page. Requires
the separate `read-statuses v1` extension for exact BookOrbit 3.6.0, now
published in [BookOrbit Extras 0.3.0](https://github.com/komadorirobin/bookorbit-extras/releases/tag/v0.3.0).
An administrator must install it separately; the OrbitUI beta alone cannot
enable it on an unextended server. The separately reviewed Littex installation
has server support, but this does not change the client's off-by-default choice.
No EPUB indexing, cover work, downloads or new remote writer. Open/parked
books, pending Undo and newer/ambiguous same-day local changes are protected.
Unread/Want to Read do not reset local reading. Position, history, ratings and
reviews stay unchanged. Unchanged canonical statuses need no sidecar I/O;
changed statuses are published in slices, with caches refreshed on normal
navigation rather than forcing a heavy Manga rebuild. Conflicts/ambiguous
metadata copies are skipped, not resolved automatically. Bigme timing/UI
acceptance remains pending; headless tests are not device measurements.
RC1 adds **Status check details** with separate reasons/counts and up to 50
session-only filename examples. Only counts persist; nothing is uploaded and
no status overwrite protection is relaxed. Old reports require a new check
for reasons; they cannot retrospectively explain previous skipped totals.

**Beta 28 (experimentellt):** Under **Integrationer > BookOrbit > Hämta lässtatus
från BookOrbit** finns en avstängd bakgrundsfunktion för redan kopplade böcker.
Den kontrollerar status högst var 15:e minut efter att Hem/hyllan visas, med
manuell uppdatering och tid för senaste lyckade kontroll. Kräver det nya
servertillägget `read-statuses v1`, publicerat i
[BookOrbit Extras 0.3.0](https://github.com/komadorirobin/bookorbit-extras/releases/tag/v0.3.0).
Det separat granskade Littex-bygget är driftsatt; på andra servrar måste
administratören installera tillägget. Enbart OrbitUI-uppdateringen ger inte
serverstödet och funktionen aktiveras aldrig automatiskt. Ingen indexering,
omslagshämtning eller ny skrivare till server/Hardcover. Öppna böcker, väntande
ångring och nyare/osäkra ändringar samma dag skyddas. Position och historik
ändras inte. Oförändrad status kräver ingen läsning av lokala bokinställningar.
Visningen uppdateras vid vanlig navigering, utan en framtvingad tung
Manga-ombyggnad. Mätning och visuell kontroll på Bigmen återstår.
RC1 lägger till **Detaljer om statuskontrollen** med separata orsaker/antal och
högst 50 tillfälliga filnamnsexempel. Bara antalen sparas, ingenting laddas upp
och inget skydd luckras upp. Kör en ny kontroll för orsaker; äldre totalsiffror
kan inte delas upp i efterhand.

**Beta 27 — smart offline tag chips:** long-press a local
EPUB tag in the book's **Tags** tab to create a named smart chip in an existing
library. Combine up to 16 exact tags with **AND** or **OR**, within that library
or all local libraries. Opening a chip checks cached tags only; the **Indexed**
footer is not a claim of complete indexing. Swipe down or use **Update tag
matches…** in its settings to read missing/changed EPUB tags, with progressive
results and Stop. The first 400 matches are shown; a capped chip says **400+**.
Chips retain normal rename/order/remove and Home-pinning controls. No book is
copied, moved or edited, and no BookOrbit account/server patch is needed.

**Svenska, Beta 27 — smarta lokala taggchip:** långtryck på en
lokal EPUB-tagg i bokens **Tags/Taggar**-flik för att skapa ett namngivet chip.
Kombinera högst 16 exakta taggar med **OCH/ELLER** i valt bibliotek eller alla
lokala bibliotek. Chipet visar **Indexerade** träffar utan att automatiskt läsa
alla EPUB-filer. Svep nedåt eller välj **Uppdatera taggträffar…** för att läsa
saknade/ändrade taggar. Sökningen kan stoppas; gränsen är 400 träffar och markeras
med **400+**. Vanliga chipinställningar och visning på Hem fungerar även här.
Inga böcker flyttas/redigeras och inget BookOrbit-konto eller servertillägg krävs.

**Index all EPUB tags:** open **OrbitUI settings > Bookshelf > Tags and
indexing**. **Update tag index** reads new/changed files and retries failures;
**Reread all EPUB tags…** confirms a fresh read of every configured EPUB, useful
after bulk retagging. Unlike a search result list, this job has **no 400-file
limit**. Pause/Continue works across KOReader restarts; closing the page pauses
the job and keeps completed reads. Resume rediscovers the inventory and
revalidates file stamps, so its current-pass counter restarts without discarding
successful same-run reads. Keep KOReader open on this page while indexing;
pause before replacing EPUBs. It uses configured library roots and scan depth,
not every EPUB elsewhere on the device. Read/reused/failed counts distinguish
unreadable files from untagged books. Tag searches/chips still show at most 400
matches (400+ is disclosed); indexing more books does not remove that view cap.

**Indexera alla EPUB-taggar:** öppna **OrbitUI-inställningar > Bookshelf >
Taggar och indexering**. **Uppdatera taggindex** läser nya/ändrade filer och
försöker igen med misslyckade. **Läs om alla EPUB-taggar…** startar efter
bekräftelse en ny omläsning av alla konfigurerade EPUB-filer — lämpligt när du
har taggat om hela biblioteket. Indexeringen har **ingen gräns på 400 filer**.
Du kan pausa och fortsätta efter omstart; stängning pausar och behåller färdiga
läsningar. Fortsätt räknar om det aktuella beståndet från början men återanvänder
oförändrade filer som redan lästs i samma jobb. Låt KOReader vara öppet på
sidan medan jobbet körs, och pausa innan du ersätter EPUB-filerna. Bibliotekens
mappar och sökdjup gäller. Räknare visar lästa, återanvända och misslyckade
filer; oläsbara filer blir inte falska tomträffar. Sökningar/chip behåller sin
visningsgräns på 400 träffar, även om fler böcker är indexerade.

**RC2:** sleep pauses offline tag
search/indexing without automatically restarting it on wake. Completed reads
are kept; Continue resumes the index manager. If navigation changed, Close
still works and the page explains that it must be reopened. Tapping a title in
either local or BookOrbit tag results selects the book on its actual shelf,
showing its cover/description without opening it for reading. Long-press still
opens book details; other search/reader open actions are unchanged.

**RC2:** vila pausar lokal
taggsökning/indexering utan automatisk återstart. Redan lästa taggar behålls;
Fortsätt återupptar indexeringen. Om navigationen ändrats fungerar Stäng ändå,
och sidan förklarar att den behöver öppnas igen. Ett titeltryck i lokala eller
BookOrbit-taggträffar markerar boken i rätt bokhylla och visar omslag/beskrivning
utan att öppna läsvyn. Långtryck öppnar fortfarande bokdetaljer; övriga
sök- och läsåtgärder är oförändrade.

**OrbitUI settings > Integrations > BookOrbit** has a master switch and
independent controls for the BookOrbit list, manual status actions and online
tags, available from Beta 23. They do not disable the separate BookOrbit plugin's
reading-progress sync, erase its credentials, or replace your saved layouts.

| Feature | Source and requirements |
| --- | --- |
| **Want to read [Local]** | Existing local To Be Read module and KOReader collection. No account, network or server patch. |
| **Want to read [BookOrbit]** | BookOrbit's Want to Read list, matched to files already on the device. Requires its connected KOReader plugin; no optional server patch. Does not download books. |
| **Manual BookOrbit menu actions** | Explicitly add/remove a linked book from Want to Read. These actions change the server's read status; they are not a second automatic progress sync. |
| **EPUB tags (offline)** | Read embedded `bookorbit:tags` metadata and find matching local EPUBs across profiles. No BookOrbit installation or API patch required. Standard EPUB subjects remain genres. Available in Beta 22. |
| **Online BookOrbit tags** | Explicit load/refresh in the Tags tab. Exact matches among linked local files need the optional server API addition. No server-only results or automatic metadata writes. |
| **Import reading status (experimental, Beta 28)** | Opt-in GET-only import for linked device books. Requires the separately installed read-statuses v1 server extension, published in BookOrbit Extras 0.3.0. No position sync or new remote writer. |
| **Undo accidental opening** | Separate device patch plus a version-compatible server extension. Not bundled or controlled by OrbitUI. |
| **Hardcover single-writer compatibility** | Optional device patch keeps BookOrbit as the automatic Hardcover writer while retaining the separate Hardcover plugin's linking/edition/metadata tools. |

The two Want to Read modules remain separate. Turning BookOrbit off does not
silently substitute the local collection, alter either list or remove saved
source selections. Add the local module through **Home (SimpleUI) > Layout &
modules**, or choose its source in **Reading dashboard**. Custom headings stay.

See **[BookOrbit Extras](https://github.com/komadorirobin/bookorbit-extras)** for
device-patch installation, exact server bases, licenses and English/Swedish
instructions. Server changes require the server administrator to build, test
and deploy them separately. An OrbitUI update never deploys a server patch.
The reviewed official BookOrbit **3.6.0** source package can combine tags and
undo; it does not mean support for every newer version. The old **3.2.0**
compiled overlay must not be copied over a newer server. Databases using that
old custom migration need a separately reviewed upgrade; do not erase opening
state or rewrite migration history to bypass its safety check.
Do not disable/remove undo support with a protected opening pending; resolve
that state using the patch first. Local EPUB tags need none of these extras.

**Svenska:** Under **OrbitUI-inställningar > Integrationer > BookOrbit** samlas
de valfria funktionerna. **Vill läsa [Lokalt]** använder KOReaders lokala samling;
**Vill läsa [BookOrbit]** hämtar serverns lista men visar bara matchade filer på
enheten. Listorna byts aldrig ut mot varandra. Huvudbrytaren styr bara OrbitUIs
funktioner, inte BookOrbits egen synk. EPUB-taggar fungerar offline utan patchar;
taggmatchning via servern och Ångra öppning har separata serverkrav. De nya
inställningarna och källnamnen ingår från Beta 23. BookOrbit Extras har ett
granskat paket för exakt officiella 3.6.0 med båda funktionerna. Använd inte det
gamla 3.2.0-överlägget på en nyare server; gamla egna databaser kräver en separat
granskad uppgradering.

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
by Bookshelf. Keep KOReader's **Cover browser** plugin enabled. Beta 26 is a
prerelease, not a promise of compatibility with every device or user patch.

1. **Back up first.** Keep a copy of your KOReader settings, user patches,
   custom artwork and working plugins. Preserve book sidecars/reading data
   separately too. See [backup details](docs/MIGRATION.md#what-is-preserved).
2. **If SimpleUI or Bookshelf is installed, disable it in KOReader's plugin
   manager and restart KOReader.** Disable both if you have both. Do not delete
   their settings or plugin folders.
3. Download **`orbitui.koplugin.zip`** from the
   [Beta 27 release](https://github.com/komadorirobin/orbitui.koplugin/releases/tag/v0.1.0-beta.27).
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
**v0.1.0-beta.26**, then select **`orbitui.koplugin.zip`**. Restart KOReader
after installation. Preview builds are not returned by GitHub's "latest stable release"
endpoint, so the default latest-release lookup may report that none exists.
Do not choose **Direct download from repo**, **Source code**, the checksum
file, or the add-on-only **ornaments-1** release.

**[Storefront by ultimatejimmy](https://github.com/ultimatejimmy/storefront.koplugin):**
use **26.10.20 or newer**, which includes the
[embedded-plugin detection fix](https://github.com/ultimatejimmy/storefront.koplugin/releases/tag/26.10.20).
Find `komadorirobin/orbitui.koplugin` and choose **v0.1.0-beta.26** and
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

**0.1.0-beta.26** publishes Bookshelf **6.1.1**, configurable **Android apps**,
and the measured first-Manga-opening optimizations. On the test Bigme, first
Manga visits improved from a 15.76-second median to 6.18 seconds; warm Manga
did not improve and metadata refresh can still pause. Picker cards now use
their own height inside the shelf editor. Quiet update work forwards the tap
that cancels it, and single-page settings retain category cards.

It also fixes the Android crash on long-press > **Refresh metadata**.
The safety check now uses the existing preference store instead of the settings
editor. Android safe mode and your settings remain unchanged; no cache reset or
full reindex is needed for this fix. All Beta 24 changes below remain. See
[Beta 26 notes](docs/OTA.md#orbitui-010-beta26).
App Launcher additionally offers an optional device-local **Settings shortcut >
Developer options** target; normal Android Settings stays the default.

**Svenska:** Beta 26 innehåller Bookshelf **6.1.1**, valbara **Android-appar**
och optimerad första öppning av Manga. På test-Bigmen sjönk medianen från
15,76 till 6,18 sekunder; redan laddad Manga blev inte snabbare. Valkort får
rätt höjd i hyllredigeraren, tyst uppdateringsarbete släpper vidare avbrytande
tryck och inställningarnas kategorikort fungerar även på en sida.
Beta 26 rättar också kraschen vid långtryck > **Uppdatera metadata** på
Android. Säkerhetsläget och dina inställningar behålls. Du behöver inte radera
omslagscachen eller indexera om för att rätta den här kraschen. Uppdatera via
förhandsversionskanalen och starta om KOReader. Fortsatt beta.
App Launcher får också ett frivilligt enhetslokalt val **Inställningar-genväg >
Utvecklaralternativ**. Vanliga Android-inställningar är fortfarande standard.

**0.1.0-beta.24** publishes the reviewed **Bookshelf 6.1.0** integration:
page-based shelf editing, clearer book dialogs/actions, richer genre/collection
filters and improved cover/ornament cache reuse. SimpleUI fixes bold-font sizing
under UI scaling. OrbitUI's profile, navigation, binding, caption, Android/night
and BookOrbit adaptations remain, with new English/Swedish labels. No settings,
reading data, external patch or server is reset or deployed. Physical Bigme/Boox
acceptance remains open; cache benefits are not measured device speedups.
See [Beta 24 notes](docs/OTA.md#orbitui-010-beta24), including rollback caveats.

**Svenska:** Beta 24 innehåller Bookshelf 6.1 med tydligare bokdialoger,
sidindelad hyllredigering, fler filter och förbättrad cache för omslag/ornament.
Våra profiler, snabbstängning och BookOrbit-funktioner behålls. Fortsatt beta;
prova de nya vyerna på enheten efter uppdatering och omstart.

**0.1.0-beta.23** adds the BookOrbit integration settings, explicit local/server
Want to Read source names, independent feature switches and guarded pending
requests. It keeps offline EPUB tags and the external BookOrbit plugin's own
progress sync independent. No server or device patch is deployed by OrbitUI.
Physical Bigme/Boox settings and source-switch acceptance remain open.

**0.1.0-beta.22** adds offline embedded
EPUB tags to the existing Tags tab, alongside the optional online source.
Exact local results span configured profiles without an account or server
patch. It includes Beta 21's Book details crash fix and Beta 20's night-mode,
search/browse refinements and reviewed upstream changes. Physical Bigme/Boox
acceptance and optional live tag API verification remain open. Its published
archive is unchanged; the newer controls are a separate Beta 23 release.

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
Exact imported baselines and currently reviewed upstream revisions are recorded
in [sources.json](sources.json); historical release numbers are not source pins.
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

# v0.1.0-beta.26 · 2026-11-01


Beta 26 publishes the previously local Beta 25 changes and the reviewed
Bookshelf **6.1.1** import through `c686f5a3`. Self-sizing picker cards use their
own height when opened as an editor page, while remaining within the display.
SimpleUI stays at `fdf83c7d`; no new SimpleUI commits were available. Beta 25
was never publicly released: using 26 also permits upgrades from that installed
local test version. All earlier public release assets remain immutable.

Svenska: Beta 26 publicerar de tidigare lokala Beta 25-ändringarna och
Bookshelf **6.1.1**. Valkort får sin egen höjd inne i hyllredigeraren utan att
gå utanför skärmen. SimpleUI är oförändrat. Beta 25 släpptes aldrig offentligt;
26 gör att även den lokala testversionen kan uppdateras.

The release fixes the Android crash after long-pressing a book and choosing
**Refresh metadata**. OrbitUI's Android safety check read the settings editor
instead of the preference store and called a missing `nilOrTrue` function.
It now reads the existing store without changing the safety preference.

Regression coverage reproduces the original failure before the fix, uses the
real component loader/preference store/storage adapter, and checks unset,
enabled, disabled and non-Android behavior. The cover queue tests no longer
give the editor an invented store API. Both source and sealed-package paths
are covered. Existing cover preservation, bounded no-fork extraction and
cancellation remain; no cache reset or full reindex is required for this fix.

Svenska: Beta 26 rättar kraschen vid **långtryck på en bok > Uppdatera metadata**
på Android. Säkerhetskontrollen läste från inställningsmenyn i stället för
inställningslagret. Befintligt säkerhetsläge behålls och ett regressionstest
använder det riktiga lagret. Du behöver inte radera omslagscachen eller indexera
om biblioteket för att rätta den här kraschen.

The SimpleUI **App Launcher** module also gains **Settings shortcut > Android
settings / Developer options**. Normal Android Settings remains the default
on all devices. The explicit device-local alternative opens Android's public
Developer options entry, useful where a vendor Settings homepage crashes
entering Wireless debugging. It does not directly open private Android pages,
enable debugging, grant permissions or change any system setting. The Settings
icon and other app buttons remain unchanged.

Svenska: SimpleUI-modulen **App Launcher** får valet **Inställningar-genväg >
Android-inställningar / Utvecklaralternativ**. Standardvalet är oförändrat;
det nya målet väljs separat på varje enhet. Det kan kringgå en felande
inställningsstartsida hos tillverkaren. Inga Android-inställningar eller
behörigheter ändras och felsökning aktiveras inte. Från Utvecklaralternativ
öppnar du själv Trådlös felsökning. Ikonen och de andra appknapparna behålls.

The release additionally makes **Android apps**
(previously App Launcher) configurable through long-press > **Apps**. Add a
device launcher app, rename, move before/after a named neighbour, or confirm
removal of its shortcut without uninstalling it. Extra apps receive responsive
page arrows; an empty module remains configurable. Existing enabled modules
keep their choices; newly enabled ones start empty, not with personal defaults.
Only explicit edits save the device-local list. Discovery runs on Add app only;
manual package-name entry is available if Android filters/fails the query.
Removing/re-adding Settings does not reset its destination choice.

Svenska: Du kan långtrycka på
**Android-appar > Appar** för att lägga till, byta namn, flytta och ta bort
genvägar. Flyttvalen namnger grannen och visar platsen direkt. Att ta bort en
genväg avinstallerar inte Android-appen. Fler appar får sidpilar och en tom
modul går fortfarande att konfigurera. Befintliga aktiva moduler behåller
sina val; nya börjar tomma. Applistan och Inställningar-målet sparas lokalt.
Långtryck, riktig applista och avbryt är nu provade på Bigme. Ändringar av
applistan är ännu bara automatiskt testade.

The release also reuses bounded text metadata between library
scopes and makes layout probes skip unused folder-cover work. First Manga
profile visits measured about 5–7 seconds versus 15–17 before on the test Bigme;
warm Manga did not improve, and metadata refresh can still pause for a fresh
derivation. Own quiet update work forwards its canceling input rather than
dropping it; visible download cancellation is unchanged. One-page category
cards no longer fall back to the old list when native pagination is a stateless
span. Full tests and focused device checks pass, not complete device acceptance.

Svenska: Versionen återanvänder textmetadata mellan biblioteksvyer
och undviker onödigt omslagsarbete vid layoutmätning. Första Manga-besök tog
cirka 5–7 sekunder mot tidigare 15–17 på test-Bigmen. Redan laddad Manga blev
inte snabbare och metadatauppdatering kan fortfarande ge en paus. OrbitUIs
tysta uppdateringsarbete släpper nu vidare trycket som avbryter det. Kategorikort
på en sida fungerar även med KOReaders enkla sidavstånds-widget. Detta är
testat på Bigmen, men är inte ett godkännande av alla enhetsflöden.

All Beta 24 Bookshelf/SimpleUI behavior remains alongside the reviewed 6.1.1
picker fix. No bootstrap/API-1 or installed-path change, settings migration, resource removal,
external patch or BookOrbit/Hardcover synchronization change. Previous public
releases/assets remain immutable. Update through the preview channel and
restart KOReader. Still a prerelease: the exact final merged package has not
been tested on a physical device. Broader Bigme/Boox acceptance, app-edit
persistence and metadata-refresh extraction/filter-result acceptance remain
open. The user's new explicit publication request approves this beta with
those limits; it is not a claim that all earlier device gates have passed.

The separately published Undo-opening fix is **BookOrbit Extras 0.2.1** /
the Ereader Patch Manager catalogue, not an embedded OrbitUI patch. Update
that patch separately and restart KOReader. No server is deployed and no
already committed reading history is restored by either update.
Svenska: Ångra-fixen uppdateras separat via Ereader Patch Manager eller
BookOrbit Extras 0.2.1. OrbitUI installerar ingen serverpatch. Befintlig
läshistorik ändras inte. Slutpaketet och kvarstående app-/metadataflöden
behöver fortfarande provas på enheten.

# v0.1.0-beta.24 · 2026-10-31

# OrbitUI 0.1.0-beta.24

Bookshelf 6.1.0, clearer shelf/book controls and improved image-cache reuse.
This is a prerelease; physical Bigme/Boox acceptance remains open.

## English

- The reviewed **Bookshelf 6.1.0** integration adds page-based shelf editing
  for source, view, sort, filters, themes, modules and order, with breadcrumbs
  and coalesced live previews.
- Clearer book dialogs use rounded action cards, segmented choices, an editable
  action layout and a persistent Tags edit strip. Review spoilers are optional.
  OrbitUI's minimal header, lazy Book details and offline/online tag sections remain.
- Filters gain genre AND/NOT and excluded collections. Themes can sort by
  newest or last use. These controls do not edit book files or reading status.
- Separate cover/ornament disk budgets and last-use recency improve reuse after
  restart, retaining OrbitUI's bounded cancelable maintenance. Expected benefits
  are not measured device speedups.
- SimpleUI fixes cached bold-font sizing under global UI text scaling.

Our profiles/chips, fast close/return, face-out shelves, cover size/captions,
bindings, Android safe covers, night contrast, folder/MAL actions and BookOrbit
features are retained. New labels have Swedish/English equivalents. No additional
upstream is imported during release preparation, and no external patch, hardware
driver, server, credential or reading data is changed.

## Svenska

- **Bookshelf 6.1.0** ger sidindelad hyllredigering med tydligare val för källa,
  visningsläge, sortering, filter, tema, moduler och ordning.
- Bokdialogerna får tydligare åtgärdskort och valknappar. Åtgärder kan ordnas om
  och Taggar får en fast redigeringsrad. Våra bokdetaljer och taggkällor behålls.
- Fler genre-/samlingsfilter och sortering av teman efter nyast/senast använd.
- Omslag och ornament får separata cachegränser och senast använda bilder
  prioriteras. Rensningen sker fortfarande avbrytbart i små steg. Ingen fysisk
  snabbhetsvinst är uppmätt.
- SimpleUI rättar storleken på fet text vid skalning av gränssnittets text.

Våra profiler, snabbstängning, bokbindningar, omslagskontroller och
BookOrbit-funktioner behålls. Inga böcker, läsdata eller inställningar återställs.
Server- och enhetspatchar installeras inte av den här uppdateringen.

## Update and limits

Update through OrbitUI's preview channel and **restart KOReader**, or install
this release's **orbitui.koplugin.zip**, not GitHub's source archive. Back up
settings first. Standalone SimpleUI/Bookshelf must remain disabled.

Bootstrap API 1 and all 2,000 installed paths remain unchanged. Existing languages,
fonts and artwork are retained. Earlier public tags/assets are never replaced.
Code rollback retains user data, but older code may ignore new filters/action
layouts; review shelf scope after rollback rather than restoring old reading data.

Full Lua/LuaJIT, translation, sealed/native OTA and source/history/artwork/secret
checks precede publication. They are not physical e-ink/font/touch acceptance.
Retest new dialog/editor/Back/Close paths, profiles, Tags/Book details, cache reuse,
day/night, rotation/sleep and reader return on Bigme/Boox.

Svenska: Uppdatera via förhandsversionskanalen och starta om KOReader. Fortsatt
beta: prova de nya vyerna på enheten. Äldre kod kan ignorera nya filter efter
kodåterställning; kontrollera då hyllans avgränsning.

See [OTA notes](https://github.com/komadorirobin/orbitui.koplugin/blob/v0.1.0-beta.24/docs/OTA.md)
for details and rollback limitations.

# v0.1.0-beta.23 · 2026-10-31

# OrbitUI 0.1.0-beta.23

Optional BookOrbit integration controls and clearer local/server reading lists.
This is a prerelease; physical Bigme/Boox acceptance remains open.

## English

- New **OrbitUI settings > Integrations > BookOrbit** page with a master switch
  and separate controls for Want to Read, manual status actions and online tags.
- Explicit **Want to read [BookOrbit]** and **Want to read [Local]** source names.
  The local source uses the existing KOReader To Be Read collection. Add either
  or both through **Home (SimpleUI) > Layout & modules**, or select a Reading
  dashboard source. Disabling one never replaces it with the other.
- Explicit refresh feedback and a durable last-successful list timestamp,
  including unchanged lists. Opening settings does not test a connection.
- Deferred requests retire when a feature is disabled, including rapid off/on.
  Already-sent server mutations cannot be unsent; late results are not adopted.
- English/Swedish help explains manual read-status writes, optional server
  requirements and the separate [BookOrbit Extras](https://github.com/komadorirobin/bookorbit-extras)
  package. Its reviewed exact official 3.6.0 source can combine tags and undo.
  Never reuse the old 3.2.0 compiled overlay on a newer server; old custom
  databases need a separately reviewed upgrade.

Offline EPUB tags remain independent. BookOrbit's own reading-progress sync,
credentials, links, cached lists, memberships, module/source IDs, custom headings
and layouts are retained. OrbitUI does not install or deploy external patches.
Resolve protected openings and pending cleanup before removing undo support.

## Svenska

- Ny sida: **OrbitUI-inställningar > Integrationer > BookOrbit**, med huvudbrytare
  och separata val för Vill läsa, manuella lässtatusval och taggar via nätet.
- Tydliga källor: **Vill läsa [BookOrbit]** och **Vill läsa [Lokalt]**. Den lokala
  använder KOReaders befintliga samling To Be Read. Lägg till båda via **Hem
  (SimpleUI) > Layout och moduler**, eller välj källa i Läsöversikt. Listorna byts
  aldrig ut mot varandra när BookOrbit stängs av.
- Tydlig uppdateringsstatus och sparad tid för senast lyckade listuppdatering.
  Väntande svar från avstängda funktioner får inte skriva över lokal cache.
- Hjälpen förklarar synk och versionsbundna serverkrav. BookOrbits egen synk,
  sparade listor, kopplingar och layouter behålls. EPUB-taggar fungerar offline.
  Server- och enhetspatchar installeras inte av denna OrbitUI-uppdatering.

## Update and limits

Update via OrbitUI's preview channel and restart KOReader, or install this
release's **orbitui.koplugin.zip**, not GitHub's source archive. Back up first.
Standalone SimpleUI and Bookshelf must remain disabled; keep their data/files.

Full Lua/LuaJIT, translation, sealed-package, native OTA and source/history/
artwork/secret checks precede publication. These are headless checks, not physical
acceptance or proof that an optional API is deployed on your BookOrbit server.
Retest SV/EN layout, touch/keyboard, refresh, off/on, source selection, long help,
Back, rotation/sleep and reader return on Bigme/Boox.

No new upstream merge, artwork, runtime path, language removal, bootstrap/API
limit change or production server update. Previous public assets stay immutable;
rollback changes code, not reading data. See [OTA notes](https://github.com/komadorirobin/orbitui.koplugin/blob/v0.1.0-beta.23/docs/OTA.md)
for details.

# v0.1.0-beta.22 · 2026-10-31

## Svenska

- Klickbara taggar finns i den befintliga **Taggar-fliken**. Välj **EPUB-taggar (offline) > Läs EPUB-taggar** och tryck sedan på en tagg för fler böcker med exakt samma tagg på enheten.
- EPUB 2/3-taggar som BookOrbit har skrivit in i filen fungerar helt lokalt, utan BookOrbit-plugin, konto, koppling, nätverk eller API-tillägg. Vanliga EPUB-ämnesord ligger fortfarande under Genrer; samlingar hålls separata.
- Träfflistan söker i konfigurerade biblioteksprofiler och hemmabiblioteket, med bibliotekets vanliga skanningsdjup. Den går att avbryta och behåller normal boköppning. Uppdatera läser om filerna; oläsbara EPUB-filer och gränsen på 400 träffar visas tydligt.
- Valfri hämtning av taggar från BookOrbit finns separat. Nätbaserad taggsökning kräver serverstödet som förberetts lokalt men **inte driftsätts här**. Det behövs inte för EPUB-taggarna.
- Ny upstream-kontroll: SimpleUI och Bookshelf är redan helt ikapp. Inga ytterligare upstream-ändringar i denna beta. Bokdetalj-fixen från Beta 21 och tidigare nattläge-, omslags- och navigationsanpassningar behålls.

Uppdatera via förhandsversionskanalen och starta om KOReader. Inga bokfiler, läsdata, kopplingar eller inställningar återställs. Fortsatt beta: fysisk provning på Bigme/Boox återstår.

## English

- Clickable tags live in the existing **Tags** tab. Choose **EPUB tags (offline) > Read EPUB tags**, then tap a tag for local books with the exact same tag.
- EPUB 2/3 `bookorbit:tags` metadata works entirely offline: no BookOrbit plugin, account, link, network or API addition required. Standard EPUB subjects remain Genres; collections stay separate.
- Results cover configured library profiles and the home library, respecting native scan depth. Scanning is cancelable and normal reader actions are retained. Refresh rereads files; unreadable EPUBs and the 400-match limit are disclosed.
- Optional online BookOrbit tag loading is separate. Online tag search needs the separately prepared server endpoint, **not deployed by this release** and not needed for embedded tags.
- Fresh upstream check: SimpleUI and Bookshelf are already current. No additional upstream imports. Beta 21's Book details crash fix and earlier night-mode, cover and navigation adaptations remain.

Update through the preview channel and restart KOReader. No books, reading data, links or settings are reset. Still a prerelease: physical Bigme/Boox layout, input, scan latency, cancellation and lifecycle acceptance remain open.

# v0.1.0-beta.21 · 2026-10-31

Beta 21 fixes the KOReader crash when selecting **Book details** in the book panel.

The tab passed no header to a renderer that requires one. It now uses the modal's native headerless HTML scroller, preserving CSS, dimensions, per-tab zoom, scrolling gestures and native replacement/close ownership.

The regression test now selects the actual tab through native modal switching, assembly, scrolling, zoom, resize and close paths. It reproduces the nil-header failure on Beta 20 and passes after the fix. Render primitives remain stubbed; physical device testing is still required.

### Svenska

Beta 21 rättar kraschen när du väljer **Bokdetaljer**. Fliken använde fel renderingshjälp utan den rubrikdel som den krävde. Nu används dialogens vanliga HTML-yta med rätt textstorlek, scrollning och stängning.

Det nya regressionstestet växlar verkligen till fliken och kontrollerar zoom, storleksändring, upprepade flikbyten och frigöring av ersatta vyer. Du behöver inte indexera om eller ändra några inställningar.

### Update / uppdatering

Update through OrbitUI's preview channel and restart KOReader. For manual installation use **orbitui.koplugin.zip**, not GitHub's source-code archive. / Uppdatera via förhandsversionskanalen och starta om KOReader.

Earlier betas can update directly. All Beta 20 night/search/shelf improvements remain. No source pins, bootstrap/API-1, installed paths, assets, reading data, metadata, links, collections or sync owners are changed. No earlier public release or asset is overwritten. BookOrbit tag navigation is being assessed separately and is not included in this crash hotfix.

Still a prerelease: retest Book details scrolling, independent zoom, repeated tab switches, close and reader/shelf return on Bigme/Boox. / Fortsatt beta: automatiska tester ersätter inte fysisk provning på enheten.

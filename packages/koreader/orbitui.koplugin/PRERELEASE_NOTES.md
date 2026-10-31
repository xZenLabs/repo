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

# v0.1.0-beta.20 · 2026-10-31

Beta 20 combines the reviewed SimpleUI update with the approved night-mode and shared-interface refinements.

### Highlights

- **Night mode:** clearer dark backgrounds over retained wallpaper, consistent rounded RGB card corners on Android and a readable navigation bar. Day preferences and original cover colours are preserved.
- **Tilted Cover Deck covers:** upstream matches warped images to the screen format before night inversion and correctly accounts for their cache memory. Conversion never frees the original cached cover. Polish translations are updated.
- **Search:** optional typo-tolerant matching for accents, prefixes and transposed letters, with exact Swedish spelling ranked first. Existing scopes, genre preference, recent searches and the 400-hit cap remain.
- **Shelf controls:** tap the page counter marked **▾** for **Sort, filter & view**, including compact one-/two-column lists and relative dates. Choices are remembered per profile/chip/opened group. **Use shelf defaults here** restores the original grouping, layout and sorting. Filters never write reading status or remote progress.
- **Settings:** **You are here** offers direct jumps to parent settings levels.
- **Book details:** a simpler cover/title/author/progress header, lazy technical-information tab with independent zoom and **Read now** using the original reader action. Existing tabs and plugin actions remain.
- **Diagnostics:** additional opt-in local scalar timings; no queries, titles or paths are logged. The developer CPU benchmark is not a measured reader-performance claim.

### Svenska

Beta 20 innehåller nattlägesfixen för ljusa bakgrunder, felaktiga korthörn och svårläst navigationsrad. SimpleUI rättar även bildformatet för lutade omslag i Cover Deck vid nattläge samt deras minnesräkning. Bookshelf har inget nytt upstream.

**Stavfelstålig sökning** kan hitta böcker trots stavfel och omkastade bokstäver. Exakt svensk stavning prioriteras; funktionen kan stängas av. Tryck på hyllans sidräknare med **▾** för **Sortering, filter och vy**. Kompaktlistor visar titel, författare, läsprocent och datum. Valen sparas per profil/chip/grupp, och **Använd hyllans standard här** återställer ursprunglig gruppering, vy och sortering. Filtren ändrar aldrig lässtatus eller fjärrsynk.

Inställningarnas **Du är här** gör det enklare att gå tillbaka genom nivåerna. Bokpanelen får en renare header, teknisk information under **Bokdetaljer** och **Läs nu** med samma läsaröppning som tidigare. Nya egna texter finns på svenska och engelska.

### Install / installation

Download **orbitui.koplugin.zip**, not GitHub's source-code archive, or update through OrbitUI's preview channel. Restart KOReader afterward. / Uppdatera via förhandsversionskanalen och starta om KOReader.

Older supported betas can update directly. Same 2,000 installed paths and unchanged API-1 bootstrap; no bridge, settings reset or automatic metadata scan. Existing profiles, chips, fast book closing, Android-safe cover handling, BookOrbit/Hardcover/MAL and external patches retain their owners. The prose bookmark patch is distributed separately through Ereader Patch Manager. No prior public release or asset is replaced.

Reviewed upstream: SimpleUI `5631ce1035286803d7586979c75993671ff022cb`; Bookshelf unchanged at `ee84a8fe1621171c00df91c41dee76b9ed07028c`. Thanks to both upstream projects and their contributors.

Still a prerelease: physical Bigme/Boox acceptance remains outstanding. Retest day/night/day, tilted/ordinary covers, fonts/touch/keyboard, compact views and saved defaults, settings navigation, detail tabs/zoom, reader return, rotation/sleep and OTA. / Fortsatt beta: automatiska tester ersätter inte provning på enheten och innebär ingen uppmätt snabbhetsvinst.

# v0.1.0-beta.19 · 2026-10-30

## Svenska

- Förbättrad gemensam sökning: tio senaste lokala sökningar med vald avgränsning, rensningsbar historik och sortering efter relevans, titel, författare eller serie. Profiler och aktuell hylla behåller sin avgränsning.
- Enklare samlingshantering: välj en egen samling under **Hantera samlingar → Hantera böcker…**. Sök, lägg till/ta bort medlemskap, granska ändringar och välj **Spara** eller **Avbryt**. Inga bokfiler raderas. Favoriter och mappstyrda samlingar behåller KOReaders vanliga hantering.
- Senaste granskade SimpleUI-ändringarna ingår: månadsdiagram för böcker/sidor i läsinsikterna, separat årsväljare samt säkrare statistikcache och återförsök. Läsöversiktens layout ersätts inte.
- Separat inspirationsbevakning på GitHub för utvalda delar av sex UI-projekt. Ingen automatisk merge/import och ingenting som körs på läsplattan.

Hardcover, utgåvekoppling, BookOrbit/MAL/patch-integrationer, profiler/chip och snabbstängning lämnas oförändrade. Inga nya upstream-importer görs för denna release: SimpleUI `7a605bbc`, Bookshelf `ee84a8fe`.

Uppdatera via **förhandsversionskanalen** och starta om KOReader. Ingen återställning eller mellanversion behövs. Inställningar, läsprogression och metadata behålls; kodåterställning återställer inte senare användardata.

Fortsatt beta: automatiska tester ersätter inte fysisk testning på Boox/Bigme. Prova sökning/historik/avgränsning, samlingarnas vyväljare/sökning/paging/Spara/Avbryt, läsinsikternas årsväljare samt rotation, viloläge och återgång från boken. Ingen uppmätt prestandavinst påstås.

## English

- Shared search now has ten local recent query/scope pairs, explicit history clearing and relevance/title/author/series sorting. Current-shelf and profile restrictions are preserved.
- Custom collection contents can be edited through **Manage collections → select a collection → Manage books…**. Search, stage membership additions/removals, review changes and Save or Cancel. Book files are never deleted. Favourites and folder-managed collections retain native KOReader controls.
- Includes the already-reviewed SimpleUI changes: monthly books/pages charts in Reading Insights, an independent year selector and safer statistics caching/retries. The existing Home/dashboard layout is preserved.
- A separate GitHub inspiration watcher monitors selected parts of six UI projects, never auto-merges/imports and does not run on the reader.

Hardcover, edition linking, BookOrbit/MAL/patch integrations, profiles/chips and fast close are unchanged. No additional upstream is imported for this release: SimpleUI `7a605bbc`, Bookshelf `ee84a8fe`.

Update through the **preview channel** and restart KOReader. No reset or bridge release is needed. Existing settings, reading progress and metadata remain; code rollback does not roll back later user data. All 2,000 installed paths, bootstrap/API, artwork, fonts and languages are retained.

Still a prerelease: automated tests are not physical Boox/Bigme acceptance. Retest search/history/scopes, collection views/search/paging/Save/Cancel, the Insights year picker, rotation, sleep and reader return. No measured performance gain is claimed.

# v0.1.0-beta.18 · 2026-10-30

## Svenska

Beta 18 rättar snabbkontrollerna från Beta 17:

- Tryck på Hems statusfält öppnar rätt snabbkontroll i stället för att fångas av toppmenyn.
- Valet att aktivera statusfältens snabbkontroller börjar gälla direkt.
- Dialogerna behåller sin ursprungliga identitet, så flikar, Uppdatera status, Stäng och Wi-Fi-åtgärder inte blockeras av SimpleUI.

Öppna **OrbitUI-inställningar > Navigation och gränssnitt > Snabbkontroller**.
Statusfältstryck är fortsatt valfritt. Egna gester, sparade knappar, profiler/chip,
Androids säkra omslagshantering och snabbstängning behålls.

Alla tidigare Beta 17-funktioner och granskade upstream-ändringar ingår. Ingen ny
upstream-merge eller ljusdrivrutin ingår. Bigmes valfria ljuspatch är redan
publicerad separat i [Ereader-patchpaketet](https://github.com/komadorirobin/Ereader)
och [sin egen repo](https://github.com/komadorirobin/koreader-bigme-frontlight).

Uppdatera via förhandsversionskanalen och **starta om KOReader**. Ingen
inställningsåterställning eller mellanversion behövs. Detta är fortsatt beta;
bekräfta tryck, dialogstängning och återgång från Androids Wi-Fi-inställningar
på enheten. Automatiska tester är inte fysisk enhetsverifiering.

## English

Beta 18 fixes the quick-control input regressions reported in Beta 17:

- Home's current status targets receive taps before the parent top menu.
- Enabling/disabling status-field quick controls takes effect immediately.
- Quick-control dialogs retain native identity, allowing tabs, Refresh, Close and Wi-Fi actions to pass the existing owner guards.

Open **OrbitUI settings > Navigation & interface > Quick controls**. Status taps
remain opt-in. Custom gestures, saved bars, profiles/chips, Android safe-mode
covers and fast reader return remain intact. All Beta 17 features and reviewed
upstreams are included; no new upstream import or hardware light driver.
The optional Bigme userpatch remains separately distributed through the links above.

Update on the preview channel and **restart KOReader**. Existing supported betas
can update directly. Bootstrap/API 1, the same 2,000 installed paths, artwork,
fonts and languages are retained. Previous releases remain immutable; code
rollback does not restore old reading progress or later settings.

This is a prerelease. Automated Lua/LuaJIT, package and native-boundary/OTA
checks do not establish physical Boox/Bigme touch, rendering, hardware controls,
Android system return, rotation or suspend acceptance. Please retest those.

Download **orbitui.koplugin.zip**, not GitHub's source-code archives.
Keep KOReader's Cover browser enabled; disable standalone SimpleUI/Bookshelf.

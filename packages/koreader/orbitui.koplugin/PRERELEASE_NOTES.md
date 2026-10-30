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

# v0.1.0-beta.17 · 2026-10-30

# OrbitUI Beta 17 — snabbkontroller och tydligare inställningar

Förhandsversion för test på Boox/Bigme. Ingen ny upstream-import i själva releasen;
de redan granskade ändringarna från 30 oktober ingår.

- Fem stora inställningskort med förklaringar, sökning och alternativ listvy.
- Små snabbmenyer för ljus/färgtemperatur, Wi-Fi, batteri och klocka. Kontroller
  visas efter enhetens stöd; Android Wi-Fi går till systemets inställningar.
- Valfria upstream-funktioner: rutnät för snabbåtgärder, upp till sex omslag per
  rad på Hem, menyfiltrering, bläddringsstatistik och fler Tiny Critter-val.
- Egna patchar stängs inte av. Profiler/chip, omslagsfixen, snabbstängning och
  BookOrbit/MAL-integrationer behålls. Svenska och engelska finns för nya egna UI.

Uppdatera via förhandskanalen och **starta om KOReader**. Öppna sedan
**OrbitUI-inställningar → Navigation och gränssnitt → Snabbkontroller**.
Slå vid behov på **Tryck på statusfält för snabbkontroller**, eller lägg till
**Snabbkontroller** som navigationsknapp. Tryckfunktionen är av från början;
sparade navigationsrader ersätts inte. Ta gärna bilder från Hem och Bookshelf.

## English

Beta 17 adds large bilingual settings-category cards and shared anchored quick
controls. Open **OrbitUI settings → Navigation & interface → Quick controls**.
Status-field taps are opt-in; the same action can be added to a bar without
replacing saved buttons. Native light ranges/warmth conversions, existing
statistics/calendar owners and Android's system Wi-Fi settings are reused.
Opening status does not start scans, network connections or polling.

Also includes the already-reviewed October 30 changes through Bookshelf
`ee84a8fe` and SimpleUI `257c26d6`: optional grid quick actions/six-cover rows,
protected menu hiding, page-turn statistics, Tiny Critter enhancements, guarded
startup work and scrollable long messages. Automatic patch disabling is blocked.

Download **orbitui.koplugin.zip**, not the source-code archives. Update through
the preview channel and restart KOReader. Stable bootstrap/API 1, all 2,000
installed paths, languages, fonts and artwork are retained. Earlier betas can
update directly. Previous public releases/assets are unchanged.

Back up KOReader's data independently. Rollback changes code, not later settings
or reading progress; remove/reselect the optional Quick controls bar action if
rolling back to code that does not recognize it. Physical font/touch/focus,
light/warmth, Android return, colour/night/underlay and lifecycle acceptance
remains open. Automated checks are not a measured device-speed/RAM claim.

[Full bilingual notes and recovery guidance](https://github.com/komadorirobin/orbitui.koplugin/blob/v0.1.0-beta.17/docs/OTA.md#orbitui-010-beta17).

# v0.1.0-beta.16 · 2026-10-28

## Svenska

- Läsöversikt begär nu bara statistik, bokräkning och senaste-böcker-data för kort som behöver dem.
- Nya frivilliga **Adaptiv minneshantering** och **Snabbhetsläge** under **OrbitUI-inställningar → System och underhåll → Snabbhet, minne och diagnostik**. Befintligt beteende är standard. Snabbhetsläget stänger av svepanimationer och spekulativ förladdning; kalla sidladdningar kan därför ta längre tid.
- Lokal prestandamätning och kopierbar rapport utan boknamn, sökvägar, konton eller uppladdning. Mätningarna gäller synkrona anrop, inte skärmens totala svarstid.
- Ny snabbguide för Hem (SimpleUI), Bookshelf-profiler, chip, navigationsknapp och snabb återgång från en bok. Alla nya kontroller och hjälptexter finns på svenska och engelska.
- Mindre releasepaket: bara utvecklarnas fil-/radreferenser utelämnas ur översättningsfilerna. Alla språk, texter, bilder, typsnitt och licensuppgifter behålls.
- Säkrare lagringsstädning: efter verifierad start kan högst en gammal, oanvänd kodkopia tas bort. Fabrikskopia, aktiv version, återställningsversion och okända/ändrade filer behålls. Inställningar, läsdata, omslagscache och tilläggsbilder rörs inte.

Android safe mode, omslagskvalitet och snabb återgång till rätt profil/chip/hyllposition behålls. Inga nya upstream-importer; samma granskade Bookshelf 6.0.4 och SimpleUI 3.0.1-uppföljning som Beta 15 ingår.

**Uppdatera via förhandskanalen och starta om KOReader.** För manuell installation: välj `orbitui.koplugin.zip`, inte GitHubs källkodsarkiv. Ta en separat säkerhetskopia av KOReaders data. Detta är en förhandsversion; fysisk Boox/Bigme-kontroll av snabbhet, minne, skärm och lagringsbeteende återstår. Ingen uppmätt enhetsvinst utlovas.

## English

- Reading dashboard data demands follow visible cards and the selected goal owner; hidden cards no longer request unnecessary statistics, book counts or recent-book candidates.
- Optional **Adaptive memory** and **Responsive** profiles: **OrbitUI settings → System & maintenance → Speed, memory & diagnostics**. Existing behaviour remains the default. Responsive skips Bookshelf wipe animations and speculative next-page/chip preload; cold page loads may take longer.
- Opt-in, bounded local call timings and a viewable/copyable performance report. No book names, paths, accounts, raw errors or upload. Synchronous call timings are not end-to-end display latency; Lua heap is not total RAM.
- Bilingual Home/Bookshelf quick guide for library profiles, chip sources, navigation and reader return.
- Smaller package without removing languages, messages, images, fonts or licenses: only developer source-location comments are omitted from packaged translation catalogs.
- After healthy startup, at most one verified strictly older unused code snapshot can be collected. Factory/current/rollback, pending/newer code and unknown/modified files stay protected. No books, settings, reading data, cover caches or add-on artwork are cleanup targets.

Keeps Android safe mode, cover quality, fast profile/chip/page return and external sync ownership. No new upstream import; retains Bookshelf `d07905ba` (6.0.4) and SimpleUI `22d5a3d2` (3.0.1 follow-up).

**Update on the preview channel and restart KOReader.** Use `orbitui.koplugin.zip` for manual installation, not GitHub's source archive. Bootstrap/API 1 and all 2,000 installed paths are unchanged. Earlier public releases remain immutable. Code rollback retains later settings and reading progress; keep an independent data backup.

Automated Lua/LuaJIT, translation/package/source/history and native older-installer upgrade/rollback checks are separate from physical-reader acceptance. Boox/Bigme performance, native image pressure, UI/display and storage acceptance remain outstanding; no measured device speed/RAM improvement is claimed.

# v0.1.0-beta.15 · 2026-10-28

## Svenska

- **Färg i Läsöversikt:** välj Av, Accenter eller Tonade kort under **OrbitUI-inställningar > Hem (SimpleUI) > Läsöversikt > Kortfärger**, eller i modulens egna inställningar. Tonade kort ger pastellbakgrunder och färgade ramar/indikatorer. Valet gäller den aktuella läsöversikten, inte hela gränssnittet.
- **Omslagsfärgat Fortsätt läsa-kort:** ett färgat omslag kan ge kortet en passande mörk nyans. Mörkt/ljust kort, rubriker, layout, bokkällor, öppna/långtryck och oberoende bläddring behålls. Svartvita skärmar och avstängd färgrendering behåller gråskalan; nattläget får egna nyanser.
- **Senaste granskade upstream:** Bookshelf 6.0.4 med färgfixar, mindre onödiga helskärmsblinkningar och sökbar samlingshantering. SimpleUI får rättningar av minnesläckor/sidpilar, uppskjuten fillistning, färre onödiga omslagsuppdateringar, bakgrundsdithering, valfri sidblinkning och Hazel.
- Våra profil-/snabbstängningsfixar, Android safe mode/omslagsfixen, Home/Bento, serieboxar/ornament och BookOrbit/MAL-kopplingar är kvar.

**Befintliga installationer behåller Av tills du väljer färg.** Uppdatera via OrbitUI med förhandsversioner tillåtna och starta om KOReader. Ingen återställning eller ny indexering krävs för färgerna.

## English

- **Reading dashboard card colours:** Off, Accents or Tinted cards, scoped to each Home/Custom Screen. Existing installations remain Off until explicitly changed. Find it in **OrbitUI settings > Home (SimpleUI) > Reading dashboard > Card colours**, or the module's own settings.
- Optional cover-derived continue-reading colour, native monochrome fallback and day/night palettes. Existing dark/light hero, layout, headings, sources, independent row paging and book actions are retained. This is an independent OrbitUI implementation inspired by BookOrbit's colour-board options; no BookOrbit code, palette or artwork is imported.
- Includes reviewed **Bookshelf 6.0.4** through `d07905ba932e09044827aadf480c188a5d324b96` and **SimpleUI 3.0.1 follow-up** through `22d5a3d2dd7be4651e718eb49027d82f68b3ace7`. Fast profile return, settings improvements, safe Android covers, Home/Bento and external sync owners remain intact.

Install **orbitui.koplugin.zip**, not GitHub's source archive. Existing supported betas can update on the preview channel; restart KOReader. Bootstrap/API 1, installer limits and the complete 2,000-file installed path set are unchanged. No settings, progress, links, caches or artwork are reset. Code rollback preserves later data/settings changes; older builds ignore the new scoped colour choice.

This is a **prerelease**. Automated Lua/LuaJIT, contrast/native-UI-boundary, package and native archive/OTA checks are not physical display acceptance. Actual Boox/Bigme colour strength, night-mode rendering, ghosting, responsiveness and touch/rotation/sleep checks remain outstanding. SVG schematics use synthetic covers and approximate text; they are not device screenshots or performance measurements.

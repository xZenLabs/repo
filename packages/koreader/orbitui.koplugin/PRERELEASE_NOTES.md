# v0.1.0-beta.29 · 2026-11-01

## Svenska

Beta 29 innehåller den granskade **Bookshelf 6.2.0**-uppdateringen. SimpleUI är redan uppdaterat. Inga ytterligare upstream-ändringar hämtas i detta publiceringssteg.

- **Bildkontrast:** valfri kontrastökning för omslag, ornament och bokryggar samt separat kontrast/ljusstyrka för bakgrunden. Standardutseendet ändras inte. Originalbilder och rå bildcache skrivs inte om. Bakgrundsreglagen finns också under **Tema → Bakgrund**.
- **Beteende → Nederkantens knapprad:** Visa, Dölj eller Osynliga knappar. Dölj frigör utrymmet; osynliga knappar behåller sina tryckytor. Markering/tangentfokus visar kontrollerna igen. OrbitUI:s egna storlekar, marginaler och navigationsfält behålls.
- **Mindre blinkande:** meny- och temabyten använder färre helskärmsuppdateringar. Svep på hyllan utanför en dialog kan byta sida bakom dialogen. Ett tryck utanför ett reglage sparar värdet; kryss/Bakåt ångrar fortfarande.
- **Android-nattläge:** jämnare runda färgade hörn, med bibehållen mjukvarureservväg och våra egna bakgrunds-/navigationsfixar. Fixar även felaktig bakgrund, fastnad menyåterställning och skuggor när böcker öppnas.
- Valda hyllmoduler får minutuppdateringar när rätt hylla visas. Sena återanrop får inte rita om en stängd eller annan hylla; delade menykrokar frigörs när deras ägare avslutas.

Hem/Bento, Manga-profiler, serielådornas omslag/proportioner, taggar/indexering, ornament och BookOrbit/Hardcover/MAL/patch-kopplingar behålls. BookOrbit-statusimporten är fortfarande avstängd som standard och kräver separat servertillägg. Ingen server driftsätts eller enhet uppdateras av själva publiceringen.

Svenska och engelska kontroller/hjälptexter ingår. Samma 2 000 installationsfiler och oförändrad API-1-bootstrap. Tidigare releaser, taggar och filer ändras inte. Uppdatera via förhandskanalen och starta om KOReader.

Fortsatt beta: de senaste kontrast-/knapprads-/svep-/menyändringarna är automatiskt testade men ännu inte visuellt accepterade på Bigme/Boox. Ingen ny uppmätt hastighetsförbättring utlovas. Se TESTING för exakta resultat och kvarvarande enhetskontroller.

## English

Beta 29 publishes the reviewed **Bookshelf 6.2.0** merge. SimpleUI is already current. No additional upstream revision is imported during publication.

- **Image contrast:** optional contrast boost for covers, ornaments and spines, with separate wallpaper contrast/brightness. Defaults stay unchanged; original artwork and raw disk images are not rewritten. Wallpaper controls also appear under **Theme → Wallpaper**.
- **Behavior → Footer bar:** Show, Hide or Invisible buttons. Hide reclaims space; Invisible retains hitboxes. Selection/key focus reveals the controls. OrbitUI's adjustable footer dimensions, margins and dock geometry remain.
- Fewer intended full-screen flashes on menu/theme changes. Side swipes on the shelf outside a picker can turn its page without closing the picker. Tapping outside a slider commits its value; X/Back still cancel.
- Android night-mode rounded RGB paints keep consistent corners, including software fallback and OrbitUI's existing backdrop/dock fixes. Fixes stale wallpaper/menu restoration and face-out opening shadows.
- Explicitly configured shelf modules can update every minute. Late callbacks cannot repaint hidden/replaced/closed shelves. Shared menu hooks are released with their host.

Existing Home/Bento, Manga profiles, aspect-preserving series artwork, tags/indexing, ornament add-ons and external BookOrbit/Hardcover/MAL/patch ownership stay intact. BookOrbit status import remains OFF by default and requires its separate server extension. This release deploys no server and installs nothing on a device by itself.

Swedish/English controls/help; the same 2,000 installed paths and unchanged API-1 bootstrap. Previous public releases, tags and assets are immutable. Update through the preview channel and restart KOReader.

Still a prerelease: latest contrast/footer/swipe/menu changes have automated verification but no fresh physical Bigme/Boox visual acceptance or measured speedup. See TESTING for exact results and remaining device checks.

# v0.1.0-beta.28 · 2026-11-01

## Svenska

Beta 28 innehåller senaste granskade Bookshelf-upstream och den valfria BookOrbit-statusimporten. SimpleUI är redan uppdaterat.

- **OPDS-kataloger:** utgivningsår kan nu visas med `%calibre{pubdate}` för både OPDS 1.x och 2.0. Publiceringsdatum prioriteras framför datum då boken lades till; första kända året behålls när utgåvor slås ihop.
- **Experimentell statusimport:** **Integrationer → BookOrbit → Hämta lässtatus från BookOrbit**. Avstängd som standard. Kontrollerar redan kopplade böcker på enheten högst var 15:e minut efter att Hem/hyllan visas; manuell uppdatering och senaste lyckade kontroll finns på samma sida.
- Importen kräver det separata servertillägget **read-statuses v1 för exakt BookOrbit 3.6.0**. Det är byggt/testat lokalt men **ännu inte publicerat eller driftsatt**. Enbart OrbitUI-uppdateringen ger alltså inte serverstödet. Ingen server ändras i denna release.
- Öppna böcker, väntande ångring, nyare lokala ändringar och osäkra konflikter samma dag skyddas. Oläst/Vill läsa återställer aldrig lokal läsning. Sidposition, historik, betyg, recensioner och BookOrbits egna synkinställningar behålls. Ingen ny skrivare till servern eller Hardcover.

Hem/Bento, Manga-profiler, snabbretur, taggchip, indexering, ornament och externa patchar behålls. Inga nya installerade filer eller bootstrap-/API-1-ändringar. Svenska och engelska texter ingår. Tidigare releaser och deras filer ändras inte.

Uppdatera via förhandskanalen och starta om KOReader. Fortsatt beta: senaste OPDS-/statusändringarna är automatiskt testade men ännu inte provade på Bigme/Boox. Ingen ny uppmätt prestandaförbättring utlovas. Se TESTING för testresultat och återstående enhetskontroller.

## English

Beta 28 includes the latest reviewed Bookshelf upstream and optional BookOrbit reading-status import. SimpleUI is already current.

- OPDS 1.x/2.0 catalog books expose their publication year through `%calibre{pubdate}`, preferring publication-specific dates and preserving the first known year when editions merge.
- **Experimental, OFF by default:** **Integrations → BookOrbit → Import reading status from BookOrbit** checks already matched device books after Home/a shelf is visible, at most every 15 minutes. Update now and the last successful check are available there.
- Requires the separate **read-statuses v1 extension for exact BookOrbit 3.6.0**, currently built/tested locally but **NOT published or deployed**. This OrbitUI update alone does not provide server support and deploys nothing.
- Protects open/parked books, pending Undo, newer local changes and ambiguous same-day conflicts. Unread/Want to Read never reset a read. Position, history, ratings/reviews and native sync preferences remain unchanged. GET-only server access; no new remote/Hardcover writer or forced Manga rebuild.

Existing Home, shelves, profiles, fast return, offline tags/indexing, ornaments and external patch behavior remain. No new installed path, bootstrap/API-1 change, cache reset or server deployment. Previous releases/assets are immutable. Swedish/English controls and help are included.

Update through the preview channel and restart KOReader. Still a prerelease: latest OPDS/status changes have no fresh physical Bigme/Boox acceptance or measured latency gain. See TESTING for automated/sealed/native OTA evidence and remaining device gates.

# v0.1.0-beta.27 · 2026-11-01

## Svenska

Beta 27 samlar våra senaste taggfunktioner och Android-fixar. Ingen ny upstream-import: Bookshelf 6.1.1 och SimpleUI-baslinjen är oförändrade.

- **OrbitUI-inställningar → Bookshelf → Taggar och indexering**: Uppdatera läser nya/ändrade EPUB-filer och försöker igen med fel. **Läs om alla EPUB-taggar…** läser efter bekräftelse om hela det konfigurerade biblioteket. Ingen gräns på 400 filer. Pausa/Fortsätt fungerar efter omstart; stängning pausar och behåller färdiga läsningar. Fortsätt räknar om beståndet men återanvänder oförändrade filer från samma jobb. Låt KOReader vara öppet medan jobbet körs, och pausa innan du ersätter EPUB-filer.
- **Smarta taggchip**: långtryck på en lokal EPUB-tagg i Tags/Taggar, namnge chipet och kombinera upp till 16 taggar med **OCH/ELLER**, i valt eller alla lokala bibliotek. Vanlig sortering, visning och Hem-pinning behålls. Chip/sökresultat visar högst 400 träffar med tydlig **400+**-markering; den separata indexeringen har ingen sådan filgräns.
- **Snabbare återanvändning av taggar** via ett separat lokalt index, med synliga framsteg och fungerande Stopp/Fortsätt. Saknade/ändrade/oläsbara filer hoppas inte tyst över.
- **Android-fixar** för appmodulens sidpilar, native-inläsningsrutor och omslagsbevarande vid manuell metadatauppdatering. Din inställning för automatiskt säkerhetsläge ändras inte.

Offline-taggar kräver `bookorbit:tags` i EPUB-filen, men inget BookOrbit-konto, plugin eller servertillägg. Vanliga EPUB-ämnesord förblir genrer. Inga EPUB-filer, läsdata, externa synkägare eller gamla releaser ändras. Allt nytt har svenska och engelska texter.

Uppdatera via förhandskanalen och starta om KOReader. Fortsatt beta: riktade Bigme-tester och automatiska/native-tester är inte fullständig enhets- eller 1.0-validering. Första läsningen av tusentals arkiv, särskilt Manga, kan fortfarande ta tid. Rotation, suspend/resume, alla läsarvägar och Boox behöver fortsatt bredare provning.

## English

Beta 27 publishes the offline tag-index/search and smart-chip work, plus the Android acceptance fixes since Beta 26. No additional upstream import; Bookshelf 6.1.1 and the SimpleUI baseline remain unchanged.

- **OrbitUI settings → Bookshelf → Tags and indexing**: Update reuses unchanged entries and checks new/changed files and failures. Confirmed **Reread all EPUB tags…** reads every configured EPUB afresh, without a 400-file cap. Pause/Continue survives restart; closing pauses and keeps completed reads. Resume recounts current inventory while reusing unchanged successful files from that run. Keep KOReader open while indexing; pause before replacing EPUB files.
- **Smart tag chips**: hold a local EPUB tag in Tags, name the chip and combine up to 16 literal tags with **AND/OR**, scoped to one library or all local libraries. Retain native sorting/filtering/views and Home pins. Match views still show at most 400 results and disclose **400+**; the separate indexer is not capped.
- A separate disposable SQLite index and bounded input-aware batches support progressive, stoppable local tag search. Failed files stay retryable, not false empty results.
- Fix Android app-page navigation, explicitly native progress-dialog ownership, and transactional cover preservation during manual metadata refresh without changing the automatic safe-mode preference.

Offline tags mean embedded `bookorbit:tags` JSON, not ordinary EPUB subjects/genres or KOReader collections. No BookOrbit account/plugin/API extension is required. No book/reading-data edits, cache reset, server deployment, sync-owner change, new installed path or bootstrap/API-1 change. Swedish/English controls and help are included. Previous releases and assets remain immutable.

Update through the preview channel and restart KOReader. Still a prerelease: focused Bigme and automated native-boundary checks are not whole-library cold completion, physical-panel benchmarking, Boox compatibility or 1.0 acceptance. See TESTING for evidence and remaining gates.

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

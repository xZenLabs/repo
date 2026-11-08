# v1.1.0-beta.8 · 2026-11-08

## Svenska

Fixar de tomma menyerna och återöppningskraschen i beta.7.

- BookOrbit-källistan visas efter uppdatering och går att öppna igen med sparade hyllor/smartscopes.
- Hämta fler moduler / Modulbibliotek visar den medföljande Silverfish-posten igen.
- Valet mellan omslagsrad och karusell för BookOrbit-kort fungerar.
- Orsaken var tre loopvariabler som krockade med översättningsfunktionen. Din enhetslogg bekräftar modulbiblioteksfelet. Åtta nya menytester återskapar felen i publicerad beta.7 och passerar med fixen på svenska och engelska.

Befintliga hyllor, kort, inställningar och plugindata behålls. Ingen cache behöver rensas. Inga ändringar av BookOrbit-servern, lässtatussynken eller modulinstallationens regler.

Uppdatera via förhandskanalen och starta om KOReader. Säkerhetskopiera inställningar/läsdata separat. BookOrbit-kort använder fortsatt konfigurationsformat v3: beta.6/äldre bevarar sidan men kan inte redigera den. Kodåterställning återställer inte dina inställningar eller tredjepartsdata.

Förhandsversion: testerna använder riktiga menybyggare med simulerade enhets-/tjänstegränser. Nytt prov på Bigmen och verklig käll-/fillänkskontroll återstår. Ingen installation på enheten, serverdriftsättning eller ny upstream-merge ingår. Stabil 1.0 och tidigare releaser lämnas oförändrade.

## English

Fixes beta.7's blank menus and cached-source reopening crash.

- BookOrbit sources render after refresh and can be reopened with saved shelves/smartscopes.
- Get more modules / Module library shows the bundled Silverfish entry again.
- BookOrbit cards' cover-row/carousel chooser works.
- Three loop indices accidentally shadowed the translator. The supplied device log confirms the module-library error. Eight native-menu regressions reproduce failures in public beta.7 and pass with the fix in Swedish and English.

Existing sources, cards, settings and plugin data are preserved. No cache reset is needed. BookOrbit server, reading-status sync and module-installation policies are unchanged.

Update through preview and restart KOReader; back up settings and reading data separately. Source cards retain dashboard config v3: beta.6/older preserve the page but cannot edit it. Code rollback does not reverse settings or third-party data.

Prerelease: real menu builders with substituted display/service boundaries, not physical Bigme acceptance. Real-device retesting and live source/link coverage remain pending. No device/plugin installation, server deployment or new upstream merge. Stable/latest 1.0 and previous tags/assets remain unchanged; API1/bootstrap, 27 exact lazy helpers / 407 identities and 2,000 installed paths are retained.

Download orbitui.koplugin.zip, not the source-code archive. Details: docs/TESTING.md and docs/OTA.md.

# v1.1.0-beta.7 · 2026-11-08

## Svenska

BookOrbit-hyllor och smartscopes kan nu läggas till som egna kort i Läsöversikt.

- Öppna **Läsöversikt → + → BookOrbit-hyllor och smartscopes → Uppdatera hyllor och smartscopes** och välj en källa. Lägg till flera kort med egna rubriker/storlekar och omslagsrad eller karusell. Tryck på rubriken eller långtryck på bakgrunden för att konfigurera kortet.
- Bara BookOrbit-länkade filer som redan finns på enheten visas. Olänkade kopior gissas inte fram och serverböcker laddas inte ned. Smartscope-reglerna utvärderas av BookOrbit.
- Sparade träffar visas direkt. Synliga kort uppdateras i bakgrunden högst var 15:e minut; bara berört kort ritas om. Borttagna källor och gamla svar hanteras separat. OrbitUI slår inte på Wi-Fi eller skickar lässtatus.
- Egen av/på-brytare under **Integrationer → BookOrbit**, separat från Vill läsa och BookOrbit-pluginets egen synk. Svenska och engelska finns. Kräver ett anslutet BookOrbit-plugin/server med katalog- och bakgrunds-API; inget nytt extras-servertillägg behövs.

Uppdatera via **förhandskanalen** och starta om KOReader. Säkerhetskopiera inställningar och läsdata först. Nya BookOrbit-kort använder läsöversiktens konfigurationsformat v3: beta.6/äldre bevarar den sidan men kan inte redigera den. Kodåterställning återställer inte inställningar; behåll en matchande säkerhetskopia.

**Förhandsversion:** automatiska tester och datorprov är inte prov på Bigmen eller mot din riktiga server. Verkliga källor, fillänkar, menyer/nattläge, vila/återgång och starttid/minne återstår att verifiera. Ingen ny upstream-merge, serverdriftsättning eller installation på din enhet. Stabil 1.0 och tidigare releaser är oförändrade.

## English

Add BookOrbit libraries, shelves and smartscopes as independent Reading dashboard cards.

- **Reading dashboard → + → BookOrbit shelves and smartscopes → Refresh shelves and smartscopes**. Choose sources for several cards, with custom titles/sizes and cover-row or one-cover carousel views. Tap the heading or hold the background to configure.
- Only exact BookOrbit-linked files already on the device are shown. No title guesses or remote-book downloads. The server evaluates smartscope rules.
- Cached-first, visible-only asynchronous refresh, at most every 15 minutes; only the requesting card redraws. Account/policy/map/mount/sleep guards retire old responses. Transient failures preserve saved results; missing sources are suppressed. No automatic Wi-Fi activation or reading-status writes.
- Separate **Integrations → BookOrbit** switch, independent of Want to Read and the external plugin's own sync. Swedish/English controls. Requires a connected BookOrbit plugin/server with native catalog/background APIs, not a new extras server extension.

Update through **preview** and restart KOReader. Back up settings and reading data independently. Adding a source card opts that screen into dashboard config v3: beta.6/older preserve it but cannot edit it. Code rollback does not reverse layout/cache or third-party data changes; keep a matching settings backup.

**Prerelease:** desktop/automated evidence only. Physical Bigme and live-server source/link coverage, menus/day/night, suspend/read-return and measured start/latency/RSS remain pending. No universal compatibility or measured device-speed claim. No new upstream import, server deployment, device/plugin install or independent module-catalog publication. Stable/latest 1.0 and all earlier release assets/tags remain unchanged. API1/bootstrap stay fixed at 2,000 installed files, 27 exact lazy helpers/407 identities.

Download **orbitui.koplugin.zip**, not the source-code archive. Verification details and device limits: docs/TESTING.md and docs/OTA.md.

# v1.1.0-beta.6 · 2026-11-08

# OrbitUI 1.1.0-beta.6

Experimental preview. Stable/latest stays **1.0.0**. Update through OrbitUI's preview channel and restart KOReader; back up settings and reading data first.

## Svenska

- **Fler moduler i Läsöversikt:** tryck + eller håll inne → Lägg till modul. Lägg till kompatibla SimpleUI-/Bookshelf-kort eller åtgärdsgenvägar, ändra storlek, ordna, dölj och ta bort dem. Fler kort får egna sidor.
- **Modulbibliotek:** Lägg till modul → Hämta fler moduler. Först finns versionslåst **Silverfish 2.0.0**. Hämtningen verifieras med SHA-256 och kräver bekräftelse och omstart. Befintliga plugins och sparfiler skrivs inte över. Uppdatering och avinstallation är manuella i denna första version.
- **Bättre återanvändning av omslag:** begränsad LRU-cache för miniatyrer utan att hålla stora originalbilder kvar i minnet. Återanvänder även externa omslags nedskalningar. Ingen hastighetsvinst på Bigme är ännu uppmätt.
- **Ordförslag:** valfritt och avstängt som standard i Sök i OrbitUI. Kompletterar sista ordet från redan cachade lokala titlar, författare och serier, utan filskanning eller nätanrop medan du skriver.
- **Tidigare granskad upstream följer med:** Bookshelf 6.3.3 och SimpleUI 3.0.3, bland annat förbättringar av bokdetaljernas uppdatering, sortering och samlingarnas ordning. Ingen ytterligare upstream-merge görs i detta steg.

**Viktigt:** Silverfish-märket betyder att adaptrarna är testade på dator – inte att hela pluginet är säkerhetscertifierat eller testat på Bigme. Tredjepartsplugins körs med KOReaders fil- och nätverksåtkomst. Silverfishs eget gränssnitt är på engelska/portugisiska; OrbitUIs nya reglage och katalog är på svenska och engelska. Ingen separat online-modulkatalog har publicerats ännu; den medföljande katalogen fungerar och uppdateringsknappen förklarar detta.

## English

- Add compatible SimpleUI/Bookshelf plugin cards and action shortcuts to Reading dashboard. Resize, arrange, hide/remove and paginate up to 16 added cards per screen. Original Home layouts and book actions stay intact; visible card refreshes and timer lifetimes are scoped.
- Get more modules opens the curated Module library, initially official Silverfish 2.0.0. Explicit first install, pinned archive/checksum/source/license disclosure and restart. Never overwrite/adopt/enable an existing plugin; updates and removal remain manual. No pet code or artwork is bundled in OrbitUI.
- Bounded thumbnail LRU reuse no longer strongly retains large sources; warm external-cover downscales are reused. Desktop fixtures reduce repeated scaler calls from 20 to 1, not a measured device speed ratio.
- Optional local-cache Word suggestions, OFF by default, and the previously reviewed Bookshelf 6.3.3 / SimpleUI 3.0.3 fixes are included.

Desktop adapter testing is **not** a safety certificate or full-plugin/Bigme approval. Physical module/catalog installation, complete Silverfish startup/screensaver/save, night/rotation/sleep and device opening-time/RSS checks remain open. No new upstream import, server deployment or device installation accompanies publication. The independent catalog channel is supported but not yet published; the bundled reviewed entry remains usable.

## Upgrade and recovery

API1/bootstrap remains unchanged with 2,000 installed files (26 exact lazy helpers, 407 canonical module identities). Update from beta.5 via the preview channel and restart. Existing profiles, sources/headings, ornaments and sync/data ownership are retained.

Adding dashboard cards opts that screen into layout config v2: older versions cannot edit it but must preserve it. Code rollback does not reverse layout edits or third-party data migrations, and does not uninstall a separately installed plugin. Keep an independent settings backup; do not restore old reading progress.

Full Lua/LuaJIT, translations, sealed/native, real pinned Silverfish archive, older-installers, source/history/artwork/secrets and main/tag CI checks precede publication. See docs/TESTING.md and docs/OTA.md for exact evidence and remaining device limits.

# v1.1.0-beta.5 · 2026-11-07

OrbitUI 1.1.0-beta.5 — Visible alphabet labels · Synliga bokstäver

## Svenska

- Fixar att bokstavslisten i beta.4 kan reagera på dragning utan att bokstäverna syns. Den gamla beräkningen utgick från önskad textstorlek, inte typsnittets faktiska radhöjd och extra textmarginaler. Text som inte fick plats ritades inte alls.
- Listens egna texter får nu noll extra marginal; radavståndet följer uppmätt normal/fet texthöjd. Storleken anpassas efter faktisk bredd/höjd i listen, den markerade bokstavens rad och den stora återkopplingen.
- Pekytan, bokstavspositionerna, omslagens utrymme, sortering/filter, läsaråtergång och paus/avbryt-beteende behålls. Ingen metadata, EPUB, nätverksläsning eller ombyggnad av hyllan under dragning. Bokstavslisten är fortsatt valfri och avstängd som standard, med svenska och engelska.

Aktivera per vy via **sidräknaren ▾ > Sortering, filter och vy > Bokstavslist**.

Ett nytt test återskapar osynliga bokstäver med den publicerade beta.4-koden och passerar med fixen. Kontrollen använder även KOReaders riktiga textwidget och FreeType-mått från ett medföljande typsnitt. Tidigare tester kontrollerade bakgrund/pekyta men använde för förenklade textmått. Teckenformning och faktisk skärmvisning är fortfarande inte ett fysiskt Bigme/Boox-test; bekräfta gärna att listen nu syns, även vid andra textstorlekar, rotation och nattläge.

**Endast förhandskanalen; stabil/latest är fortfarande 1.0.0.** Ingen ny upstream-merge, ändring av komponentversioner, bootstrap/API1, bilder, befintliga inställningar, läsdata eller synkägare. Ingen användarenhet/server driftsätts av releasen. Äldre versioners filer/taggar lämnas oförändrade. Övriga 1.1-funktioner och tidigare säkerhetsbegränsningar finns kvar.

## English

- Fixes beta.4's alphabet strip accepting gestures while its letters remain invisible. Requested font size underestimated native line height plus default vertical padding; oversized text was silently omitted.
- Owned labels now have zero extra padding. Measured regular/bold line heights determine spacing, and bounded cached size fitting covers actual width/height of normal labels, the selected row and large feedback.
- Touch mapping, cover/content space, sorting/filtering, reader return and cancellation/lifecycle ownership remain unchanged. Dragging still performs no metadata/EPUB/network reads or shelf rebuild. The strip remains optional, OFF by default, with SV/EN controls.

Enable per view through **footer counter ▾ > Sort, filter & view > Alphabet strip**.

New visibility assertions fail against the exact published beta.4 adapter and pass with the fix, including actual KOReader TextWidget sizing and FreeType measurements from a bundled font. Earlier tests exercised fills/input with over-simplified text dimensions. This does not run native glyph shaping or physically certify Bigme/Boox output; please check visible labels, font sizes, rotation and night mode on-device.

**Preview only; stable/latest stays 1.0.0.** No additional upstream merge, component/source-pin/bootstrap/API1/path/artwork migration, settings/reading-data wipe, new sync owner or device/server deployment. Older releases/tags stay immutable. Existing 1.1 features and hosted safety deferrals remain.

Download **orbitui.koplugin.zip**, not GitHub's source archive. Back up settings/reading data and restart KOReader after installation.

Unchanged reviewed pins: Bookshelf d47edfcc7c160691417235201595ab12cdffbdfe; SimpleUI 4bf2d2c5605d4172c5283e224450854d0b72219b.

Built on / bygger på SimpleUI by doctorhetfield-cmd and contributors, and Bookshelf by AndyHazz and contributors. See README.md, LICENSE, NOTICE and asset-specific notices.

# v1.1.0-beta.4 · 2026-11-07

OrbitUI 1.1.0-beta.4 — Alphabet strip · Bokstavslist

## Svenska

- Valfri **Bokstavslist**, avstängd som standard och sparad per vy. Aktivera via **sidräknaren ▾ > Sortering, filter och vy > Bokstavslist**.
- Tryck på en bokstav, eller dra för att visa en stor bokstav och släpp för att hoppa i den befintliga sorterade/filtrerade hyllan. Å/Ä/Ö hålls isär; andra latinska accenter använder grundbokstaven, övriga skriftsystem och siffror hamnar under # om ingen translitterering finns.
- Dragningen läser inga böcker, omslag, EPUB-filer eller metadata och bygger inte om hyllan. Bara bokstavsåterkopplingen ritas om. Ett uttryckligt hopp kan fråga den befintliga metadatacachen; ingen ny indexering eller bakgrundsskanning startas. Moduler i rutnätet, serieboxar och bokryggarnas faktiska positioner behålls.
- Listen använder ledigt utrymme i högermarginalen, inte omslagens bredd. Döljs bland annat vid icke-alfabetisk sortering, ensideslistor, öppnad serie, tvåspaltslistor, fjärrvyer och för snäv marginal. Den ändrar aldrig din sortering för att kunna visas.
- Gester/återkoppling avbryts säkert när vyn byts, täcks, stängs, går i vila eller roteras. Första trycket efter läsaråtergång får en aktuell inmatningsägare. Monokrom återkoppling följer hyllans faktiska ljusa/mörka bakgrund.

**Endast förhandskanalen; stabil/latest är fortfarande 1.0.0.** Ingen ytterligare upstream-merge ingår: samma Bookshelf- och SimpleUI-versioner som beta.3. Tidigare Serier/Volymer och övriga 1.1-nyheter finns kvar. Inga befintliga böcker, läsdata, inställningar eller cacher raderas/migreras; bootstrap/API1, 2 000 installerade sökvägar, bilder och externa synkägare behålls. BookOrbit-statusimport är fortsatt experimentell och avstängd som standard. Tidigare säkerhetsbegränsningar för automatisk datumläsning och mappradering kvarstår.

Automatiska/native tester är inte fysisk Bigme/Boox-godkänning. Prova svenska/engelska, stora typsnitt, stående/liggande, Manga/serieboxar/moduler, högermarginalens pekytor, släpp utanför listen, läsar-/menyavbrott, vila/återgång och nattläge/ghosting. Kalla/varma hopptider är ännu inte enhetsmätta. Ingen server eller användarenhet driftsätts genom publiceringen.

## English

- Optional **Alphabet strip**, OFF by default and remembered per view. Enable through **footer counter ▾ > Sort, filter & view > Alphabet strip**.
- Tap a letter, or drag to preview a large letter and release to jump in the existing native sorted/filtered shelf. Å/Ä/Ö stay distinct; other Latin accents map to the base letter, numbers/untransliterated scripts to #.
- Dragging performs no book/cover/EPUB/metadata reads and no shelf rebuild. Only letter feedback refreshes. An explicit jump can query the existing metadata cache, not a new index or background scanner. Native module visual slots, series boxes and actual spine item positions remain intact.
- Uses spare right-margin space without reducing content/cover width. Hidden for nonalphabetical sorts, single-page/opened-series/remote/two-column views and tight margins; never changes sorting to make itself appear.
- Gesture/feedback ownership expires on replacement, cover, close, sleep or rotation; reader return renews it before the first tap. Monochrome feedback follows native light/dark page paint space.

**Preview only; stable/latest stays 1.0.0.** No additional upstream merge or device/server deployment. Existing Series/Volumes and 1.1 features remain. No book/reading-data migration, cache wipe, bootstrap/API1/path/artwork change or new sync owner. BookOrbit status import stays experimental and OFF by default; existing automatic file-date/folder-delete safety deferrals remain.

Headless/native tests are not physical Bigme/Boox acceptance or measured speedups. Fonts, SV/EN portrait/landscape, touch ergonomics, module/series/spine layouts, reader/menu interruptions, sleep/rotation, dark themes/ghosting and cold/warm jump timing still need device testing.

Download **orbitui.koplugin.zip**, not GitHub's source archive. Back up settings/reading data and restart KOReader after installation.

Unchanged reviewed pins: Bookshelf d47edfcc7c160691417235201595ab12cdffbdfe; SimpleUI 4bf2d2c5605d4172c5283e224450854d0b72219b. Alphabet-strip reference reviewed, not imported: Library GUI by antonyvo; independent OrbitUI implementation.

Built on / bygger på SimpleUI by doctorhetfield-cmd and contributors, and Bookshelf by AndyHazz and contributors. See README.md, LICENSE, NOTICE and asset-specific notices.

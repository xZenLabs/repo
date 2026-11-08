# v1.1.0-beta.10 · 2026-11-08

## Dashboard card fixes

- Adding a card shows saved feedback. BookOrbit shelves/smartscopes get a checkmark; repeated picker taps cannot create duplicate cards for that source on this screen.
- Remove card is one action with feedback and an immediate updated list, not another removal submenu. Existing duplicates are kept; remove unwanted placements individually.
- Healthy BookOrbit sources and usable offline caches no longer incorrectly show Unavailable. Failed saves never show success.

## Optional reading companion

New **Currently reading + Silverfish** module: book cover, title/author/progress plus your active companion. Tap the book to resume; tap the creature to open Silverfish. **Continue reading is not replaced.** Add through **Reading dashboard > + > Home modules (SimpleUI)**, or the ordinary Home module picker.

Requires separately installed/enabled public **Silverfish 2.0.0** and restart. No fork, copied artwork, plugin-file edits, save access or duplicate development. Other versions show a compatibility explanation. Late/missing covers use native polling; colours follow KOReader/Silverfish.

## Svenska

Tillägg får kvittens och BookOrbit-källor en bock; upprepade tryck skapar inga dubbletter. **Ta bort kort** ger kvittens och återgår direkt till listan. Felaktig **Inte tillgänglig**-märkning är rättad. Befintliga dubbletter lämnas orörda.

Valfria **Läser just nu + Silverfish** visar bokomslag/läsprogress och din figur. **Fortsätt läsa ersätts inte.** Välj under **Läsöversikt > + > Hem-moduler (SimpleUI)**. Silverfish 2.0.0 installeras/aktiveras separat; inga sparfiler ändras.

## Update and scope

Update through OrbitUI's preview channel and restart KOReader. For manual installation use **orbitui.koplugin.zip**, not GitHub's source-code archive. Back up settings and reading data separately: code rollback does not undo layout edits or third-party data. Dashboard v2/v3 downgrade limits still apply.

Prerelease: automated/native-adapter tests are not complete Silverfish or physical Bigme certification. Real font/touch, checkmark/toast, layout/colour/night, sleep/wake/rotation and plugin lifecycle retesting remain pending. No device or BookOrbit-server deployment, new upstream merge, component/pin or artwork update. Stable/latest 1.0 is unchanged. Bootstrap/API1 and the 2,000-file limit are preserved.

# v1.1.0-beta.9 · 2026-11-08

## Svenska

Fixar standardplaceringen för nya Silverfish-kort: de hamnar i Läsöversikt i stället för under den, där de kunde ritas över docken. På vanligt Hem används en egen sida om det inte säkert finns plats.

Silverfishs eget Hem-val känner igen dashboard-kortet efter på/av och omstart, utan dubletter. Dina redan sparade placeringar, kortinställningar, Silverfish-data och skärmsläckarval lämnas orörda. En gammal överlappande placering flyttas inte automatiskt: ta bort och lägg till kortet igen, eller justera placeringen manuellt.

Uppdatera via förhandskanalen och starta om KOReader. Säkerhetskopiera inställningar och läsdata separat. Inget plugin installeras om och inget ändras på BookOrbit-servern. Ingen ny upstream-merge ingår. Stabil 1.0 påverkas inte.

Automatiska tester omfattar native-adaptrarna och Silverfishs publika Hem-funktioner på dator, inte hela pluginet eller fysisk Bigme-kontroll. Visuella tester, tryck, vila och rotation på Bigmen återstår.

## English

New Silverfish Home cards go inside Reading dashboard instead of becoming a sibling below its full-page module and drawing over the dock. Ordinary Home uses a separate page unless current matching geometry proves there is room.

The plugin's public Home toggle recognizes dashboard placement across add/off/restart without duplicates. Existing placements, edited cards, pet saves and screensaver options are preserved. Old overflowing placements are intentionally not migrated; remove/re-add the card or adjust it manually.

Update through preview and restart KOReader. Back up settings and reading data separately; code rollback does not restore settings or third-party data. No Silverfish fork, plugin reinstall, new upstream merge or BookOrbit-server operation. Stable/latest 1.0 is unchanged; API1/bootstrap and the 2,000-file installation budget are retained.

This prerelease is desktop-tested with native adapter/input/buffer fixtures and frozen Silverfish public Home methods, not the full plugin or physical Bigme drawing/touch/wake/rotation. Device acceptance remains pending.

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

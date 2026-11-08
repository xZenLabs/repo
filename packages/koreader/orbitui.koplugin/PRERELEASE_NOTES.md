# v1.1.0-beta.12 · 2026-11-08

## Svenska

Ny layout för **Läser just nu + Silverfish**:
- Större figur till vänster, samlad text i mitten och bokomslaget till höger.
- Namn/stadium, boktitel/författare och läsprogression får en tydligare placering.
- Texten behåller läsbar storlek; kompakta kort döljer sekundära rader först.
- Tryck på figuren/namnet för Silverfish, på titeln/omslaget för att fortsätta läsa.

**Fortsätt läsa ersätts inte.** Befintliga placeringar och Silverfishs sparfiler/progression ändras inte. Kräver separat installerat och aktiverat Silverfish 2.0.0; ingen fork eller kopierad grafik.

Uppdatera via förhandskanalen och **starta om KOReader**. Säkerhetskopiera inställningar/läsdata separat; kodåterställning återställer inte dem eller tredjepartsdata. Tidigare dashboard-v2/v3-begränsningar vid nedgradering gäller fortfarande.

Automatiska tester, fryst runtime/uppgraderingskontroll och CI kontrolleras före publicering. **Test på själva Bigmen återstår**, inklusive typsnitt, tryckytor, färg/nattläge, rotation/vila och hela Silverfish-livscykeln. Förhandsbilden var en schematisk rendering, inte ett enhetstest.

## English

Recompose **Currently reading + Silverfish**: full-height companion left, vertically centered text in the middle, book cover right. Native measured title height avoids unused lines; compact cards omit secondary rows instead of miniature fonts. Normal-contrast secondary text and separate pet/book tap targets.

Continue reading, saved placements and Silverfish data/progression are unchanged. Requires separately installed/enabled public Silverfish 2.0.0; no fork or copied artwork. No new upstream/component/pin/art/API/server/device changes. Stable/latest 1.0 and earlier releases remain unchanged. Physical Bigme/full-plugin acceptance remains pending.

Download **orbitui.koplugin.zip**, not GitHub's source archive. Existing migration and dashboard downgrade limits apply: see docs/OTA.md and docs/MIGRATION.md.

# v1.1.0-beta.11 · 2026-11-08

## Reading companion fix

Fixes the missing cat/silverfish in **Currently reading + Silverfish**. OrbitUI incorrectly rejected KOReader's normal event wrapper as an unsupported plugin API; the wrapper is now accepted without bypassing its error boundary. Public Silverfish **2.0.0** and the existing version/state/species checks are still required.

Text now follows screen density and available width rather than shrinking with a shallow row. The cover/book use the full inner height, the companion has its own name/stage column, and long titles truncate within compact cards. **Continue reading, saved placements and Silverfish's files/saves are unchanged.** No fork, copied artwork or duplicate pet progression.

## Svenska

Rättar den saknade katten/silverfisken i **Läser just nu + Silverfish** och den pyttelilla texten i breda, låga kort. Texten får läsbar storlek och omslaget mer höjd. Långa titlar kortas i stället för att krympas. **Fortsätt läsa och dina placeringar lämnas orörda.** Silverfish 2.0.0 behöver vara separat installerat och aktiverat; inga sparfiler ändras.

## Update and scope

Update through OrbitUI's **preview** channel and restart KOReader. For manual installation use **orbitui.koplugin.zip**, not GitHub's source-code archive. Back up settings and reading data separately: code rollback does not restore those or third-party data. Dashboard v2/v3 downgrade limits still apply.

This is a prerelease. Automated tests include KOReader's native minimum/current sandbox and font code, and Silverfish's real frozen renderer; they do not establish physical Bigme font/layout/touch/night/colour/wake/rotation or complete external-plugin acceptance. Those checks remain pending. No new upstream/component/pin/artwork/bootstrap/API1, independent catalog, device or BookOrbit-server deployment. Stable/latest 1.0 remains unchanged; the 2,000-file limit is preserved.

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

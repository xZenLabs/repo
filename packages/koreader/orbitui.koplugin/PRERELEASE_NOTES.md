# v1.2.0-beta.2 · 2026-11-10

OrbitUI 1.2.0-beta.2 brings a new reader bottom panel and more ways to discover, continue and keep track of local books.

This is a preview release. **Physical touch input after sleep/wake still needs verification with a stable connection.** Wireless ADB disconnected during that part of the Bigme tests. The release is published with this known verification gap; stable **1.1.0** remains available.

## A new reader bottom panel

- Book information, reading position and chapter progress in one panel, with clear tabs for the current book and other ongoing reads.
- Quick access to contents, bookmarks, search, book details, pinned references and Go to page. The ongoing-books tab includes paging and respects KOReader's ask-before-opening setting.
- **Reading settings…** opens KOReader's original reading controls, including margins and fonts.
- The OrbitUI panel is the default bottom-menu entry in this preview. To use the original menu, disable **Use OrbitUI as the bottom menu** under **OrbitUI settings → Integrations → Reader panel & X-Ray**.
- Optional standalone X-Ray and KOAssistant shortcuts. Automatic selection prefers an active X-Ray plugin, then KOAssistant. Choose a provider manually or hide the shortcut. The shortcut opens the plugin's own interface; opening the reader panel does not generate AI data.

## More local reading tools

- **Pinned references:** keep page locations, excerpts and images in a separate per-book drawer, with previews and explicit jumps.
- **Similar books and series:** discover local EPUBs through shared tags, with separate book and series results.
- **Next in series:** an optional Home card prepares the next local volumes without needing a server account.
- **Finish forecast:** an optional card uses available local reading statistics and reports when there is not enough data for an estimate.
- Reuse prepared series ordering to reduce repeated sorting during browsing. This is a scoped optimization; no claim of a measured whole-library opening speedup.

These features take inspiration from Aleph. The implementation builds on OrbitUI's existing integration; no Aleph code or assets are included.

## Updates and fixes

- Redesigned update panel with version comparison, expandable release notes, progress, cancellation and restart guidance.
- Fixed unnecessary horizontal scrolling in the new reader/update panels after viewport or display-scale changes.
- Fixed overlapping modal headings and Next in series preparation being left paused across native card rebuilds.
- Updated README and feature guide. Bookshelf 6.4.1 and SimpleUI 3.0.3 remain the integrated versions.

## Verification and limits

Both complete Lua/LuaJIT suites, all 43 translation catalogs, sealed-package tests, package/source checks and older-installer tests pass. Physical Bigme tests exercised tap/swipe entry, original reading settings, immediate opt-out/re-enable, reader-tool navigation, ongoing-book paging/switching, the KOAssistant chooser and compact scrolling. Update-panel actions were tested using an isolated UI fixture.

The sleep/wake input check remains open. Standalone X-Ray was not installed on the device, no AI request was generated, and these tests do not certify every device or plugin combination. Current release notes and source documentation distinguish software checks from physical testing.

## Install or update

Enable **Include preview releases** in OrbitUI's updater, check for updates and restart KOReader after installation. For manual installation, use **orbitui.koplugin.zip**, not GitHub's source-code archive. Back up settings and reading data first; code rollback does not restore older reading data.

OrbitUI replaces standalone SimpleUI and Bookshelf: disable those plugins and restart before enabling OrbitUI. X-Ray and KOAssistant are separate optional plugins.

Package SHA-256: `d7abac63c97b05e5a7b6b77d6ee3d20b9d6ebd16cc92e13eab422200e07ffd5f`

## Svenska

Ny läsarpanel med bokverktyg, pågående böcker och genväg till KOReaders vanliga läsinställningar. Dessutom kommer lokala bok-/serietips, egna läsreferenser, Nästa i serien, läsprognos och en ny uppdateringspanel. Panelen är standard i betan och kan stängas av i OrbitUI-inställningarna.

**Tryck efter vila är ännu inte färdigtestat på Bigmen**, eftersom den trådlösa anslutningen bröts. Betan publiceras med den begränsningen. Uppdatera via förhandskanalen och starta om KOReader.

# v1.2.0-beta.1 · 2026-11-09

## Svenska

Första betan i 1.2-serien, efter den stabila 1.1-releasen. Bookshelf är uppdaterat till **6.4.1**. SimpleUI var redan aktuellt (3.0.3).

- Mindre onödigt arbete med omslag, metadata och kataloger; bättre återanvändning av lätta hyllistor och lugnare uppdateringar efter metadataextraktion. Förväntade förbättringar, inte uppmätta hastighetsvinster på Bigmen.
- Nya val för lika höga/lika stora böcker, ryggtextens storlek och Plain/Spines-serieboxar. Valbara serierutor även i Covers/List och bläddring per årtionde.
- Anpassat till OrbitUI: separata bibliotekssektioner, Home/dock, serieomslag, MAL, ornament, taggar, BookOrbit och Silverfish behåller sina egna inställningar och ansvar.
- Säkrare omslagscache vid skrivfel och avbrutna bakgrundsjobb. Inga inställningar, läsdata eller cachefiler nollställs.

**1.1.0 är fortfarande stabil/latest.** Den här betan finns i förhandskanalen. Nya layoutval, vila/återgång och prestanda med stora bibliotek behöver fortfarande provas på enheten. Automatiska tester är inte ett sådant godkännande.

Vi aktiverar inte upstreams nya helsidescache/förladdning, bytecode-sökare eller uppdelning av navigationsinställningar: de behöver först uppfylla OrbitUI:s minnes-, modul- och återställningskrav. Omslags- och listförbättringarna ingår ändå.

## English

First 1.2 preview after stable 1.1. Integrates **Bookshelf 6.4.1**; SimpleUI 3.0.3 was already current. Credit to AndyHazz, doctorhetfield-cmd and their contributors for the upstream foundations and improvements.

Lighter cover/metadata/directory work, retained scoped shelf lists and throttled extraction updates; optional book-size/spine-text/series-box styles, Covers/List series tiles and Decades browsing. Host adaptations preserve OrbitUI sections, Home/dock, cover proportions, ornaments, tags, BookOrbit/MAL/Hardcover ownership and the optional Silverfish card. Cache-write failures preserve the previous good cover and retired background callbacks stay inert.

New whole-page pixel caching/build-ahead, the competing bytecode searcher and navigation-file migration remain deferred in hosted mode. No settings, reading data, cache reset or server deployment. API1 and the identical 2,000 installed paths are retained.

Use the complete **orbitui.koplugin.zip**, not GitHub's source archive; restart KOReader after updating. Disable standalone SimpleUI/Bookshelf before first installation. Back up settings and reading data separately: code rollback does not restore them or third-party saves. Stable **1.1.0** remains available and unchanged.

Automated source/package/native-fixture/upgrade/rollback checks precede publication. Physical Bigme font/layout/touch/colour/night/rotation/wake, large-library resource use and timings remain pending. This is a prerelease, not a device-performance certification.

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

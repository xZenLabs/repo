# v1.1.0 · 2026-11-09

## Svenska — stabil 1.1

Samma fungerande implementation som 1.1.0-beta.12, nu som stabil release efter användarens godkännande. Ingen ny upstream-kod tas in i detta släpp.

- Taggträffar på serienivå, bokstavslist och sökförslag.
- Återbruk av omslag i rätt storlek.
- Valbara pluginmoduler och ett litet versionslåst modulbibliotek.
- BookOrbit-hyllor och smartscopes som egna läsöversiktskort, med tydlig återkoppling när kort läggs till eller tas bort.
- Valbar Läser just nu + Silverfish med större figur till vänster, samlad text och bokomslag till höger. Fortsätt läsa ersätts inte.

Silverfish kräver separat installerat/aktiverat publicerat Silverfish 2.0.0; ingen fork eller kopierad grafik. BookOrbit-funktioner är valfria och kräver motsvarande plugin/anslutning; vissa andra integrationer kräver separata servertillägg. Inga sådana installeras eller driftsätts här.

Uppdatera via den stabila kanalen och starta om KOReader. Säkerhetskopiera inställningar och läsdata separat; kodåterställning återställer inte dem eller tredjepartsdata. Tidigare dashboard-v2/v3-begränsningar vid nedgradering gäller fortfarande.

Bookshelf 6.4 och senare upstream-arbete följer i en separat 1.2-betacykel. 1.1 behåller de redan granskade Bookshelf 6.3.3/SimpleUI 3.0.3-baslinjerna. Allmän acceptans på användarens enhet är inte en dokumenterad testmatris för alla enheter och valfria integrationer.

## English — stable 1.1

Promotes beta.12's unchanged runtime after user acceptance. Includes series-level tag results, alphabet navigation, search suggestions, exact-size cover reuse, optional dashboard plugin cards/module library, BookOrbit shelf/smartscope cards and Currently reading + Silverfish.

Existing placements, Continue reading and third-party data remain unchanged. No new upstream import, device installation or server deployment. Bookshelf 6.4 is reserved for the next 1.2 preview cycle. General user acceptance is not agent-run certification of every device/optional integration.

Download **orbitui.koplugin.zip**, not GitHub's source archive. See docs/OTA.md and docs/MIGRATION.md for installation, backups and downgrade limitations.

# v1.0.0 · 2026-11-04

OrbitUI 1.0.0 — first stable release / första stabila releasen

## English

Promotes the same runtime implementation as the user-accepted 1.0.0-rc.2.
No last-minute upstream feature import: the new Bookshelf/SimpleUI backlog is reserved for a separate 1.1 beta cycle.

OrbitUI combines SimpleUI's modular Home screen and Bookshelf's visual library in one plugin, with connected navigation, Reading dashboard, configurable library profiles, shared book details/settings/search, offline EPUB tags and tag shelves, optional ornament packs and optional BookOrbit/Hardcover/MyAnimeList integrations.

RC2's tag-search/index lifecycle fix and shelf selection remain: Close works when a view retires, sleep pauses work without automatic wake scanning, and tapping a tag-result title selects its real book on the shelf rather than opening the reader. Long-press still opens details.

No new reading-data/settings migration, sync owner, bootstrap change or server deployment. BookOrbit status import remains experimental and OFF by default, with its existing optional server API requirement and conflict safeguards. External plugins and patches remain separately owned.

Download orbitui.koplugin.zip (not the source archive). Back up settings and reading data, disable standalone SimpleUI/Bookshelf, install/update and restart KOReader. Both stable and preview channels can select 1.0.0; later 1.1 betas remain preview-only. Existing public releases are not replaced.

General RC2 user acceptance does not certify every Bigme/Boox model or every large-library/recovery/integration scenario. Full automated Lua/LuaJIT, translation, exact-package/source and native headless installer checks are required; those are not additional physical-device tests. See docs/TESTING.md for coverage and limits.

## Svenska

Första stabila releasen har samma funktionskod som den användargodkända 1.0.0-rc.2. Inga nya upstream-funktioner läggs till i sista stund; eftersläpningen från Bookshelf/SimpleUI tas i en separat 1.1-beta.

OrbitUI kombinerar SimpleUI:s modulära hemskärm och Bookshelfs visuella bibliotek i ett plugin: sammanhängande navigering, Läsöversikt, egna biblioteksprofiler, gemensamma bokdetaljer/inställningar/sökning, lokala EPUB-taggar och tagghyllor, valfria prydnadspaket och valfria BookOrbit/Hardcover/MyAnimeList-integrationer.

RC2:s fix för taggsökning/indexering och markering på hyllan ingår. Stäng fungerar även när vyn blivit inaktuell. Vila pausar utan automatisk återstart; titeltryck i taggträffar markerar boken i rätt hylla i stället för att öppna läsvyn. Långtryck öppnar fortfarande bokdetaljer.

Ingen ny läsdata-/inställningsmigrering, synkägare, bootstrap-ändring eller serverdriftsättning. BookOrbit-statusimport är fortsatt experimentell och avstängd som standard, med samma krav på valfritt server-API och konfliktskydd. Externa plugin och patchar ägs fortfarande separat.

Hämta orbitui.koplugin.zip, inte källkodsarkivet. Säkerhetskopiera inställningar/läsdata, inaktivera fristående SimpleUI/Bookshelf och starta om KOReader efter installation/uppdatering. Både stabil- och förhandskanalen kan välja 1.0.0; senare 1.1-betor stannar i förhandskanalen. Äldre publika releaser ersätts inte.

RC2-godkännandet är inte en certifiering av alla Bigme/Boox-modeller eller varje storbiblioteks-, återställnings- och integrationsscenario. Automatiska och headless-installationstester skiljs från verkliga enhetstester; se docs/TESTING.md.

## Credits

Built on SimpleUI by doctorhetfield-cmd and contributors, and Bookshelf by AndyHazz and contributors. Their substantial code and interfaces form OrbitUI's foundation. See README.md, LICENSE, NOTICE and asset-specific notices for attribution and licenses.

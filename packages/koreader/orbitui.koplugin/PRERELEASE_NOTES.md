# v1.0.0-rc.2 · 2026-11-02

## OrbitUI 1.0.0-rc.2 — release candidate, not stable 1.0

Feature freeze continues. This release publishes the tested tag lifecycle fix and the explicitly requested shelf-preview navigation change. Bookshelf stays at `b512cd90`; SimpleUI stays at `fdf83c7d`. No new upstream import or synchronization owner.

- Fixes the reproduced tag-search/index dialog retirement bug: Close remains usable after background-work ownership expires, and stale work releases busy/index state without adopting stale results. A changed view explains that it must be reopened instead of leaving enabled no-op actions.
- Sleep pauses offline tag search/indexing without painting or automatically restarting on wake. Completed tag reads are kept. Use Continue/Refresh when ready; reopen the page first if navigation changed.
- Tapping a title in offline or BookOrbit tag results now selects the actual book on its Bookshelf profile/folder/page with cover/description, without opening ReaderUI. Repeated selection cannot start reading. Long-press still opens book details. Missing/filtered targets fail safely, and unrelated search/reader actions are unchanged.

Existing settings, cache schemas, reading progress/history, artwork/languages and external BookOrbit/Hardcover/MAL/patch ownership remain. BookOrbit status import stays experimental, OFF by default, with unchanged protection rules. No server is deployed. Bootstrap API 1 and exactly 2,000 installed paths are retained; previous public releases/tags, including RC1, are not replaced.

**Testing limitation:** automated/sealed/native installer checks are not physical device acceptance. Sleep/wake during all 3,341 files, pause/continue/Close, actual selected-cover/description layout, cold/warm/parked transitions and on-device update/recovery still need Bigme/Boox testing. The synthetic reproduction does not prove the exact trigger on the user's device. This is not stable-1.0 sign-off.

Install `orbitui.koplugin.zip` (not GitHub's source archive), or update through the **preview channel**, then restart KOReader. Keep an independent backup. The stable channel must ignore RC2. See `docs/TESTING.md` for the remaining RC acceptance checklist.

## Svenska

**1.0.0-rc.2 är en testkandidat, inte stabil 1.0.** Funktionsfrysen fortsätter. RC2 innehåller den testade fixen och den önskade ändringen av titeltryck i taggträffar. Bookshelf/SimpleUI är kvar på granskade versioner; ingen ny upstream-merge eller synkägare.

- Fixar den återskapade låsningen i taggsökning/indexering: Stäng fungerar även när bakgrundsarbetet blivit inaktuellt. Gammalt arbete släpper upptaget tillstånd utan att ta över träfflistan. En ändrad vy förklarar att den behöver öppnas igen.
- Vila pausar lokal taggsökning/indexering utan automatisk återstart. Redan lästa taggar behålls. Välj Fortsätt/Uppdatera när du vill; öppna sidan igen först om navigationen ändrats.
- Titeltryck i lokala eller BookOrbit-taggträffar markerar boken på rätt profil/mapp/sida i bokhyllan och visar omslag/beskrivning utan att öppna läsvyn. Upprepade tryck startar inte läsning. Långtryck öppnar fortfarande bokdetaljer. Saknade/filtrerade mål hanteras säkert; övriga sök- och läsåtgärder är oförändrade.

Inställningar, cacheformat, läsdata, bilder, språk och externa plugin-/patchkopplingar behålls. BookOrbit-statusimport är fortsatt experimentell och avstängd som standard, med samma skyddsregler. Ingen server driftsätts. API-1 och 2 000 installationsfiler är kvar. RC1 och äldre releaser skrivs inte över.

**Återstår:** fysiska Bigme/Boox-tester av vila under indexering av alla 3 341 filer, paus/fortsätt/Stäng, markerat omslag/beskrivning, kall/varm/parkering och riktig uppdatering/återställning. Automattester bevisar inte exakt vad som utlöste felet på enheten och är inte godkännande för stabil 1.0.

Installera `orbitui.koplugin.zip` eller uppdatera via **förhandskanalen** och starta om KOReader. Behåll en separat säkerhetskopia. RC2 ska inte väljas av stabila kanalen.

# v1.0.0-rc.1 · 2026-11-02

## OrbitUI 1.0.0-rc.1 — release candidate, not stable 1.0

The feature set is frozen for focused acceptance testing. Bookshelf stays at the reviewed `b512cd90` documentation follow-up after 6.2.0; SimpleUI stays at `fdf83c7d`. No further upstream features, redesign, settings migration or new synchronization owner.

- BookOrbit status checks now report unchanged, missing files/data, protected entries and real newer-local conflicts separately. Open **Integrations > BookOrbit > Import reading status > Status check details** for reasons and up to 50 session-only filename examples. Only counts persist. Existing overwrite protections, server API requirement and OFF default are unchanged; status import remains experimental.
- The unavailable Bookshelf-OS reference is removed only from inspiration monitoring. The other five sources, historical attribution, existing settings-category cards and quick controls remain.
- Home/Bento, Library/Manga profiles, fast return, tags/indexing, shelves/series/artwork, optional add-ons and external BookOrbit/Hardcover/MAL/patch ownership retain their behavior. The API-1 bootstrap, all assets/languages and exactly 2,000 installed paths are preserved.

**Testing scope:** automated/sealed/native installer checks do not establish physical device acceptance. Fresh install, real-device update/recovery, full 3,000+ EPUB indexing, Bigme/Boox rendering/lifecycle and write-safe optional-integration checks remain open. No device or server was changed for this release. The exact RC checklist is in `docs/TESTING.md`.

Install `orbitui.koplugin.zip` (not GitHub's source archive), or update through the **preview channel**, then restart KOReader. Keep an independent backup. RC1 is a prerelease and must not be selected by the stable channel. Previous public releases are not replaced.

## Svenska

**1.0.0-rc.1 är en testkandidat, inte stabil 1.0.** Nya funktioner pausas inför riktad testning. Bookshelf/SimpleUI är kvar på granskade versioner; ingen ny design, migrering eller synkägare.

- BookOrbits statusrapport skiljer på oförändrat, saknade filer/läsdata, skydd och nyare lokal status. Under **Integrationer > BookOrbit > Hämta lässtatus > Detaljer om statuskontrollen** finns orsaker och högst 50 tillfälliga filnamnsexempel. Bara antalen sparas. Säkerhetsregler, serverkrav och standardvalet avstängt är oförändrade; statusimport är fortsatt experimentell.
- Bookshelf-OS tas bort enbart ur inspirationsbevakningen. De andra fem källorna, historiken, inställningskorten och snabbkontrollerna behålls.
- Hem/Manga, profiler, snabbåtergång, taggar/indexering, hyllor/serier/bilder, tillägg och externa plugin-/patchkopplingar ändras inte. API-1, samtliga bilder/språk och 2 000 installationsfiler behålls.

**Återstår:** fysiska Bigme/Boox-tester, full indexering av 3 000+ EPUB-filer, riktig uppdatering/återställning och säkra integrationstester. Automattester är inte enhetsgodkännande. Ingen läsplatta eller server ändras av publiceringen. Testlistan finns i `docs/TESTING.md`.

Installera `orbitui.koplugin.zip` eller uppdatera via **förhandskanalen** och starta om KOReader. Behåll en separat säkerhetskopia. RC1 ska inte väljas av stabila kanalen. Gamla releaser skrivs inte över.

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

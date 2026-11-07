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

# v1.1.0-beta.3 · 2026-11-05

OrbitUI 1.1.0-beta.3 — Series / Volumes · Serier / Volymer

## Svenska

- Taggträffar får flikarna **Serier / Volymer**. Manga visar Serier som standard; ditt uttryckliga val sparas per ursprungsbibliotek. Sökningen omfattar fortfarande samma lokala bibliotek.
- En serie visas en gång med antal matchande respektive lokalt indexerade volymer. Fristående böcker och okänd metadata finns kvar. Varningar visas om första volymen saknas i metadata eller volymordningen är okänd. Den befintliga gränsen på 400 volymträffar förklaras även i serievyn.
- Ett tryck markerar första tillgängliga lokalt indexerade volymen i rätt serie/bokhylla så att omslag och beskrivning visas, utan att boken öppnas. Första volymen kan sakna den sökta taggen. Flikbyte återanvänder taggträffar och cachad metadata, inte en ny EPUB-skanning.
- Senaste SimpleUI-mergen hindrar orelaterade menyer från att rita om nederlisten. Vanlig filbläddring och menyer med egen nederlist behåller sidnavigeringen. En ny post i upstreams lista över krockande omslagspatchar följer med som källkod, men OrbitUI kan fortfarande inte ändra eller stänga av dina patchar. Bookshelf var redan ikapp.

Endast förhandskanalen. **Stabil/latest är fortfarande 1.0.0.** Inga böcker, läsdata, serverstatusar eller befintliga inställningar migreras/raderas. API1/bootstrap, bilder, profiler och BookOrbit/Hardcover/MAL/patch-integrationernas ägare behålls. BookOrbit-statusimport är fortsatt experimentell och avstängd som standard.

De nya serievyerna och menyfixen är automattestade men ännu inte fysiskt godkända på Bigme/Boox. Prova svenska/engelska, rotation, Stoppa/Stäng/vila under indexering och återgång från serieförhandsvisning med filter. Inga nya enhetsmätta prestandasiffror hävdas. Tidigare 1.1-skydd behålls: automatisk datumläsning ur filer och den nya mappraderingen är uppskjutna i OrbitUI.

Hämta **orbitui.koplugin.zip**, inte källkodsarkivet. Säkerhetskopiera inställningar/läsdata och starta om KOReader efter installation. Ingen server eller användarenhet driftsätts av publiceringen.

## English

- Tag results gain **Series / Volumes** tabs. Manga defaults to Series; explicit choices are remembered per origin library without narrowing the existing local search scope.
- One row per series shows matching versus locally indexed volumes. Standalone and unknown-metadata books remain visible, with honest cached-missing-first/unknown-order warnings and disclosure of the existing 400-volume hit cap.
- Tap a series to select its first available locally indexed volume in the correct shelf/series preview, showing cover and description without opening the reader. That first volume may be untagged. Switching tabs reuses hits and bounded read-only cached metadata, not another EPUB scan.
- Reviewed SimpleUI updates stop unrelated menus from refreshing the bottom bar while preserving native chooser/injected-menu pagination. The updated incompatible cover-patch catalog remains upstream source only: OrbitUI's read-only compatibility shim cannot rename or disable patches. Bookshelf was already current.

**Preview only; stable/latest remains 1.0.0.** No book/reading-data migration, cache wipe, new sync owner, bootstrap/API1 change or server/device deployment. Existing artwork, profiles, settings and external integrations remain. BookOrbit status import stays experimental and OFF by default. Existing hosted automatic file-date/folder-delete safety deferrals remain.

Automated/native headless gates are not physical Bigme/Boox acceptance or measured performance gains. The new SV/EN views, rotation, index/grouping Stop/Close/sleep, filtered series preview/return and real menu refresh still need device testing. Install orbitui.koplugin.zip, back up settings/reading data and restart KOReader.

Reviewed source pins: Bookshelf d47edfcc7c160691417235201595ab12cdffbdfe; SimpleUI 4bf2d2c5605d4172c5283e224450854d0b72219b, full unsquashed ancestry.

Built on / bygger på SimpleUI by doctorhetfield-cmd and contributors, and Bookshelf by AndyHazz and contributors. See README.md, LICENSE, NOTICE and asset-specific notices.

# v1.1.0-beta.2 · 2026-11-04

OrbitUI 1.1.0-beta.2 — separate upstream preview / separat upstream-beta

## English

Beta.1 was never published: beta.2 fixes a final reproduced race where a pending page timer could override a direct wallpaper choice. Its pushed tag is preserved, not moved.

Stable 1.0.0 remains the user-accepted RC2 implementation. This prerelease starts a separate 1.1 cycle with reviewed Bookshelf 6.3.2 (53 commits, d47edfcc) and SimpleUI follow-ups (five commits, 633ffbff).

- Refreshed book-menu layout, publication-year sorting/token, and locally editable display dates. Cached Hardcover/calibre/OPDS/user dates remain available without a new network writer.
- Wallpaper Stretch, Crop to fill and Fit to screen, with screen-shaped previews. Late page/tab/Close callbacks cannot save stale choices; pathological native allocations are bounded.
- Metadata/series refresh, filtered-folder light-map efficiency, retained page facts/spine colours and missing-file/cover fixes. OrbitUI keeps its cancellable, blob-free metadata windows instead of a blocking full-table refresh. These are expected benefits, not new Bigme timing measurements.
- Cover Deck truncates non-Latin titles more conservatively; Critter gains ground/bubble shadows while retaining embedded/custom art and cache ownership.

Two deliberate hosted safety deferrals: automatic publication-date file reads use an unowned fork queue upstream, so they remain disabled in OrbitUI with an explicit explanation; cached/curated and explicit local display dates still work. The new folder-delete flow is not exposed because it purges sidecars before a fallible folder deletion. Move/rename and standalone component fallbacks remain.

Existing Home/Reading dashboard, Manga/profiles/series/artwork, local tags, reader return, settings and BookOrbit/Hardcover/MAL/patch owners are retained. No books/EPUBs/reading sidecars/remote statuses are rewritten by date editing. No server/device deployment, bootstrap change, removed language/artwork or increased old-updater limit. Same 2,000 API-1 installed paths, 24 exact lazy helpers and 407 canonical identities.

Preview channel only. Stable/latest remains 1.0.0; use the stable channel to stay on that accepted release. Install orbitui.koplugin.zip, back up settings/reading data and restart KOReader. New 1.1 UI/lifecycle has not been physically accepted on Bigme/Boox. Automated/native headless gates are not device tests. BookOrbit status import remains experimental and OFF by default.

## Svenska

Beta.1 publicerades aldrig: beta.2 rättar ett återskapat fel där en väntande sidtimer kunde skriva över ett manuellt bakgrundsval. Den pushade taggen behålls orörd.

Stabil 1.0.0 behåller den användargodkända RC2-koden. Den här separata 1.1-betan tar in Bookshelf 6.3.2 och SimpleUI-fixar efter granskning.

- Ny bokmenylayout, sortering/token för utgivningsår och egna lokala visningsdatum. Kända datum från Hardcover/Calibre/OPDS och användaren kan visas utan en ny synkägare.
- Bakgrundsbilder kan sträckas ut, beskäras för att fylla eller anpassas till skärmen. Skärmformade förhandsbilder, skydd mot sena meny-anrop och begränsade extrema bildallokeringar.
- Fixar för metadata/serier, filtrerade mappar, sparade sidfakta/bokryggsfärger och omslag. Våra avbrytbara metadatajobb behålls. Förväntade förbättringar är inte nya prestandamätningar på Bigmen.
- Cover Deck kortar exempelvis japanska titlar säkrare. Läskompanjonen får skuggor utan ändrat ägarskap för bilder eller cache.

Två medvetna säkerhetsbegränsningar i OrbitUI: automatisk datumläsning ur bokfiler är avstängd tills bakgrundskön fått rätt livscykel-/Android-skydd; kända datum och egna visningsdatum fungerar. Ny mappradering erbjuds inte eftersom misslyckad filradering kan lämna sidodata raderade. Flytta/byt namn och fristående komponentbeteende behålls.

Hem/Läsöversikt, Manga/profiler/serier/bilder, lokala taggar, snabbåtergång, inställningar och externa integrationer behålls. Datumredigering skriver inte böcker, EPUB-taggar, läsdata eller serverstatus. Ingen server/enhet driftsätts; inga språk/bilder tas bort och äldre uppdaterares gränser höjs inte.

Endast förhandskanalen. Stabil/latest är fortsatt 1.0.0; välj stabilkanalen för att stanna där. Hämta orbitui.koplugin.zip, säkerhetskopiera och starta om KOReader. Den nya 1.1-vyn behöver fysisk testning på Bigme/Boox; automattester ersätter inte det. BookOrbit-statusimport är fortsatt experimentell och avstängd som standard.

Built on / bygger på SimpleUI by doctorhetfield-cmd and contributors, and Bookshelf by AndyHazz and contributors. See README.md, LICENSE, NOTICE and asset-specific notices.

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

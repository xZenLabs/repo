# v0.32.0 · 2026-10-04

## Docker Image
```bash
docker pull tumetsu/crossbill:v0.32.0
```


## What's Changed
* UI proximity tweaks by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/926
* Set up react-i18next with typed, per-area English copy by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/937
* UI tweaks by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/938
* Consistent list card style for notes, flashcards and sessions by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/939
* Update frontend dependencies from open Dependabot PRs by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/940
* Assert response bodies in status-only API tests by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/945
* Rewrite docs in plain language by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/946
* Bump the uv group across 2 directories with 3 updates by @dependabot[bot] in https://github.com/Crossbill-App/crossbill-web/pull/943
* Fix the Docker install setup and its docs by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/947


**Full Changelog**: https://github.com/Crossbill-App/crossbill-web/compare/v0.31.1...v0.32.0

# v0.31.1 · 2026-09-26

## Docker Image
```bash
docker pull tumetsu/crossbill:v0.31.1
```


## What's Changed
* Fix reader crash when adding a note to a highlight (#919) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/922
* Ban unittest.mock outside infrastructure unit tests and migrate application-layer tests by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/923
* Let browser Back return from a link followed in the reader (#921) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/925


**Full Changelog**: https://github.com/Crossbill-App/crossbill-web/compare/v0.31.0...v0.31.1

# v0.31.0 · 2026-09-26

## Release notes
- You can now upload epub files via web ui from Library page. So technically you don't need Koreader to benefit from Crossbill if you use web reader :tada: 
- Optimized Koreader upload flow to not send epub files on every upload. Should speed up upload and solve some data integrity edge cases with books existing without epubs
- Automated test improvements and streamlining 

## Docker Image
```bash
docker pull tumetsu/crossbill:v0.31.0
```


## What's Changed
* Run pure-logic tests in node, rendered tests in Chromium by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/905
* Reader tests: control time with a fake clock, drop test-only props by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/906
* Fold the dialog-shell tests into the chapter dialog route test by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/907
* Give empty states and reader failures a role to be found by by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/908
* Add test-specific lint rules: vitest plugin, no real-time sleeps, capped per-test timeouts by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/909
* Bump @tanstack/router-cli from 1.167.21 to 1.167.33 by @dependabot[bot] in https://github.com/Crossbill-App/crossbill-web/pull/699
* Bump lint-staged from 17.2.0 to 17.5.1 by @dependabot[bot] in https://github.com/Crossbill-App/crossbill-web/pull/696
* Bump @types/react-dom from 19.2.4 to 19.2.7 by @dependabot[bot] in https://github.com/Crossbill-App/crossbill-web/pull/766
* Merge open Dependabot updates by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/911
* Fix the flaky frontend tests from #910 by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/912
* Read user settings from the chapter on screen in the reader page tests by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/913
* Prune tests shadowed by stronger ones by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/914
* Extract parse-first EPUB ingestion into AttachEpubUseCase by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/915
* Say KOReader is optional now that EPUBs can be uploaded in the browser by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/917
* Create a KOReader book with a single upload request by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/918


**Full Changelog**: https://github.com/Crossbill-App/crossbill-web/compare/v0.30.1...v0.31.0

# v0.30.1 · 2026-09-21

## Docker Image
```bash
docker pull tumetsu/crossbill:v0.30.1
```


## What's Changed
* Update logo by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/887
* Typography: rebuild the scale on Lora's real axis, add a UI sans for eyebrows by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/888
* Keep the swipe that turns a page from opening a highlight by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/890
* Give a highlight a colour of its own, apart from its label's by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/891


**Full Changelog**: https://github.com/Crossbill-App/crossbill-web/compare/v0.30.0...v0.30.1

# v0.30.0 · 2026-09-20

# Release 0.30.0 - Web reader update
<img width="600" alt="image" src="https://github.com/user-attachments/assets/0e2884a1-ba70-42e7-a5f7-b9f7d328478e" />

This is rather big update feature wise. The main big feature is the new web reader UI which allows you to:
- Read your books on the browser
- Jump to the location in the book from your highlights and chapter dialogs to view the context in the book
- Make highlights in the browser and sync them back to your Koreader

It is still a bit experimental so be prepared for some bugs. The Koreader/web reader conversion particularly is something which is difficult to do 100% cleanly so please report and issue if some books cause misaligned highlights etc. and I can take a look (though I might need your epub for debugging).

## Trouble shooting
- Your existing highlights should migrate over to be web reader compatible. If however after update you open a book and cannot see your highlights or get an error message, try syncing the book again from your Koreader.
- Some new required environment variables for deploy. Check `.env.example` file for guidance. **`PUBLIC_BASE_URL` is now required!**

## Docker Image
```bash
docker pull tumetsu/crossbill:v0.30.0
```


## What's Changed
* Parse an EPUB into a publication index (#794) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/809
* Web reader 2 - Readium publication parser by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/810
* Store the publication index at upload (#795) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/812
* Serve the Readium manifest from the stored index (#796) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/813
* Serve the Readium position list (#797) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/814
* Serve publication resources (#798) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/816
* Conditional requests for publication resources (#799) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/817
* Publication token and session endpoint (#800) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/818
* Cookie-only auth on manifest, positions and resources (#801) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/819
* App-wide CSP for the reader's blob frames (#802) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/820
* R1.10 Frontend: same-origin API base and Vite proxy (#803) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/821
* R1.11 Frontend: minimal web reader behind the EbookReader seam (#804) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/822
* R3.1 Frontend: table of contents drawer (#824) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/834
* R3.2 Appearance popover: font size, spacing, page colour, alignment, columns (#825) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/835
* R3.3 The page-turn buttons stand aside on a phone (#826) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/836
* R4.1 Backend: anchor service, xpointer ↔ Readium Locator via xpoint-cfi, and ADR-0004 on main by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/840
* R4.2 Backend: store derived locators on highlights and reading sessions by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/842
* R4.3 Backend: highlight locator routes, Bearer-only, outside /readium by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/844
* R4.4 Backend: web reading position, table, routes and resume answer by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/848
* fix(deps): ship xpoint-cfi in the production image by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/850
* R4.7 Frontend: resume where the reader left off and record where they are by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/849
* R4.5 Frontend: highlights drawn on the page, tap to open by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/854
* R4.6 Frontend: open the reader at a highlight by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/855
* Remove reader button from book title by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/856
* feat(web_reader): derive publication index and locators for existing books on deploy by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/857
* fix(web_reader): let a book's own images load on Safari by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/859
* fix(web_reader): release Readium's frames when the reader closes by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/860
* feat(library): resolve a book's chapter from a document position by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/862
* M4.1: selection capture with full anchoring by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/861
* M4.3: selection popover in the reader by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/864
* M4.7: extend a selection across pages by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/867
* Reorganize reader into engine, chrome, and domain layers by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/868
* Support highlight colors in web reader by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/871
* Open a chapter in the reader from the structure view by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/873
* Remove zip bomb defenses from EPUB parser by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/875
* Web reader UI tweaks by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/874
* Fix reader dark mode icon colors by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/876
* Align dialog padding and toolbar icons by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/877
* Make highlight_styles unique at every level and survive the find_or_create race by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/878
* Stamp web-reader highlights with the browser's own clock by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/879
* Disarm malformed and headless web-reader chapters by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/880
* Update docs by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/881
* Fade the landing page in once, whole by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/882
* Book header tweaks by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/886


**Full Changelog**: https://github.com/Crossbill-App/crossbill-web/compare/v0.29.0...v0.30.0

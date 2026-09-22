# v0.30.1

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

# v0.30.0

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

# v0.29.0

Major UI changes. New landing page and library page, sessions page replaced by statistics page in books, lots of minor UI/UX consistency fixes etc.

## Docker Image
```bash
docker pull tumetsu/crossbill:v0.29.0
```


## What's Changed
* Settle one list-length strategy, and place every highlight in a chapter by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/688
* Bump backend/uv.lock in the release workflow, and guard it in CI by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/690
* Remove AI summaries from reading sessions by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/700
* Replace the sessions listing with a compact SessionCard by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/701
* Share the compact-viewport test helper by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/702
* Change sessions page into statistics page by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/703
* Add a reading-activity grid to the book statistics tab by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/706
* Use SectionTitles in the Settings page by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/707
* Split library browsing into its own page by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/708
* Add library-wide reading activity grid endpoint by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/709
* Serve the reader's latest highlights and notes on one timeline by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/712
* Stop related content from repeating one book, and hide weak matches by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/714
* Give the search results room to breathe by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/719
* Add bulk book summary regeneration by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/720
* List books matched by name on top of global search results by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/721
* Commit every search field on Enter, never while typing by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/723
* Move the global search read from /semantic/search to /search by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/722
* Search books from the app bar without embeddings by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/725
* Show empty state instead of hiding sections for new readers by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/726
* chore(deps-dev): Bump eslint from 10.8.0 to 10.9.1 by @dependabot[bot] in https://github.com/Crossbill-App/crossbill-web/pull/691
* chore(deps): Bump axios from 1.19.0 to 1.20.0 by @dependabot[bot] in https://github.com/Crossbill-App/crossbill-web/pull/692
* chore(deps): Bump @mui/material from 9.3.1 to 9.4.0 by @dependabot[bot] in https://github.com/Crossbill-App/crossbill-web/pull/693
* chore(deps-dev): Bump @types/luxon from 3.7.3 to 3.7.5 by @dependabot[bot] in https://github.com/Crossbill-App/crossbill-web/pull/694
* Show the app with screenshots on the README and the site frontpage by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/728


**Full Changelog**: https://github.com/Crossbill-App/crossbill-web/compare/v0.28.1...v0.29.0

# v0.28.1

## Docker Image
```bash
docker pull tumetsu/crossbill:v0.28.1
```


## What's Changed
* Give the six book tabs one shared PageHeader by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/685
* Fix the mobile filter drawer leaving the page unscrollable by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/686


**Full Changelog**: https://github.com/Crossbill-App/crossbill-web/compare/v0.28.0...v0.28.1

# v0.28.0

## Docker Image
```bash
docker pull tumetsu/crossbill:v0.28.0
```


## What's Changed
* Show each book's reading stage in the library list by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/651
* Add note and reading-session counts to the book stats strip by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/656
* Bump @tanstack/react-router from 1.170.18 to 1.170.32 by @dependabot[bot] in https://github.com/Crossbill-App/crossbill-web/pull/563
* Add book blurb to the book header area (#653) by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/659
* Write and edit a chapter gist inline by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/658
* UI audit: the agreed findings in sections A–J by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/663
* MUI Guidelines based UI/UX improvements by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/667
* Normalise KOReader highlight timestamps to ISO in the backend by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/678
* Merge the two landing-page carousels into one recent-books row by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/679
* Fade every book tab in from one place by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/681
* Show highlight, note and flashcard counts on library book cards by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/682


**Full Changelog**: https://github.com/Crossbill-App/crossbill-web/compare/v0.27.2...v0.28.0

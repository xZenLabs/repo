# v0.33.0 · 2026-10-07

## Docker Image
```bash
docker pull tumetsu/crossbill:v0.33.0
```


## What's Changed
* Centre the reader footer stats on both axes by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/959
* Hand the device back the xpointers it sent by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/960
* Let the reader turn hyphenation on or off by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/962
* Let the reader choose the typeface the book is set in by @Tumetsu in https://github.com/Crossbill-App/crossbill-web/pull/961


**Full Changelog**: https://github.com/Crossbill-App/crossbill-web/compare/v0.32.0...v0.33.0

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

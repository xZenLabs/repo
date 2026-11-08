# v2.4.0-beta.12 · 2026-11-08

## ✨ New
- Save bulk-link results once per batch instead of once per book (#287)
- Add read:lists and read:goals to sign-in, and check sign-in scopes against Hardcover's scope map (#284)

## 🎨 Improved
- Improve bulk link by reading an EPUB's OPF with one unzip process (#285)
- Improve page turns on a shelf with a local search active (#286)
- Improve Reviews and Stats redraws by laying the page out once (#292)
- Improve Bookshelf card speed by building each card once per fit (#291)
- Improve eviction to check only books that may have lost their hold (#290)

## 🐛 Fixes
- Fix Stats Genres ring dropping its 5th genre into Other (#274)
- Fix empty book journal cache hiding saved entries (#282)
- Fix rate-limit waits to use Retry-After and stop treating every 403 as a missing scope (#283)
- Fix vibe pagination and edition selection (#267)
- Fix cover downloads, journal pagination and Unicode search (#263)
- Fix finish dates when old read books sync offline (#294)

## 🛠 For developers
- Fix CI Lua installation timeouts (#293)

## Other
- Adapt Bookshelf totals to portrait cards (#281)
- Batch the library lookups when the sync queue flushes (#289)
- Combine Home's reading, lists and goals requests into one (#288)

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.4.0-beta.11...v2.4.0-beta.12

# v2.4.0-beta.11 · 2026-11-05

No pull requests were merged since the last release.

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.4.0-beta.10...v2.4.0-beta.11

# v2.4.0-beta.10 · 2026-11-04

Bookshelf micromodules: the goal, goal-ring, stats and year cards now ship with the plugin as a module pack, alongside six new Hardcover data cards (authors read, books read, five-star books, rereads, reading memories, TBR rediscovery).

## ✨ New
- Add six Hardcover data cards to the Bookshelf module pack (#280)

## Other
- Keep offline reading history ordered and safe to retry (#279)

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.4.0-beta.9...v2.4.0-beta.10

# v2.4.0-beta.9 · 2026-11-01

## 🎨 Improved
- Show pages read offline in the Journal (#278)

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.4.0-beta.8...v2.4.0-beta.9

# v2.4.0-beta.8 · 2026-11-01

## 🐛 Fixes
- Fix offline status ordering, date queued changes, and show waiting status changes in the Journal (#275)

## Other
- Keep the progress queue by Hardcover book instead of by file (#276)
- Keep shelf changes in the progress queue and remove the shelf queue (#277)

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.4.0-beta.7...v2.4.0-beta.8

# v0.6.10 · 2026-11-17

## What's fixed

**KOReader no longer crashes when you open a ZIM on Android.** Any article used to close the app the moment it loaded. That's fixed.

**The "Offline Wikipedia" button now shows up in the dictionary popup.** It was registered before but never drawn. Tap a word and it's there.

**The lookup popup shows the article text on Android too.** It used to say "Tap to open article." instead; now it shows the lead paragraph and its image straight away.

**"Check for Updates" works.** It failed on Android with a "File exists" error every time. One tap now updates the plugin in place.

## Notes

- Menu path: **Search → Search settings → Wikipedia (offline)**
- Backup folders from earlier updates are cleaned up after an update instead of piling up.

## Requirements

The dictionary-popup button needs KOReader **v2026.07.1** or newer — older builds don't have that button API. Everything else works on older versions too.

## Install

1. Download `localwiki.koplugin.zip` below and extract `localwiki.koplugin` into `koreader/plugins/`
2. Restart KOReader
3. **Search → Search settings → Wikipedia (offline)** → Search articles

## Verified on

- Nothing Phone 3 (Android 17, KOReader v2026.07.1)
- Kindle (KOReader v2026.07.1)


**Full Changelog**: https://github.com/nar-io/localwiki.koplugin/compare/v0.6.9...v0.6.10

# v0.6.9 · 2026-11-17

## What's fixed

**Reading a ZIM on Android no longer crashes KOReader.**

Opening any article on Android killed the app with `SIGSEGV` at address `0x0` the moment the first cluster was decompressed. The clusters inside ZIM files are written without a content-size header, so the plugin used zstd's streaming API — and the copy of zstd bundled in Android's `libkoreader-monolibtic.so` does not expose a usable `ZSTD_DStream`. Frames without a known size are now decoded with a growing destination buffer instead, which succeeds on the first attempt for normal compression ratios.

The Kindle was never affected: it loads a real `libzstd.so.1` that has the streaming API.

**The "Offline Wikipedia" button now actually appears in the dictionary window.**

Two separate things kept it hidden:

- KOReader has no `show_func` field in its dictionary button spec — the plugin set one anyway, and it was silently ignored.
- Conditional buttons only render when a `default_layout` exists. Once a `dict_button_config` has been saved — which is the normal state on Android — there is no `default_layout`, so a conditional button never showed up. The button is registered as a plain button now, which is the form KOReader actually renders.

The plugin also used to strip its own button out of the saved layout on every lookup and every start, which kept it hidden permanently once it went missing. That is gone.

## What's changed

- The lookup window preloads the article intro on Android too. The old platform carve-out showed "Tap to open article." instead, because eager cluster work used to crash there — but the crash was in the decompression path, not the lookup window.
- zstd and lzma are resolved the way KOReader itself resolves them (`ffi.findlib`), so Android finds them inside the monolibtic bundle and the Kindle keeps using its own library.
- FFI calls now keep a strong reference to their input string. The raw pointer handed to C could outlive the Lua string behind it once the garbage collector ran.
- The highlight-menu button sorts just before KOReader's own Wikipedia entry instead of after it.

## Requirements

KOReader **v2026.07.1** or newer for the in-dictionary button — earlier versions have no dictionary button registry at all. Everything else in this release works on older builds.

## Install

1. Download `localwiki.koplugin.zip` below and extract `localwiki.koplugin` into `koreader/plugins/`
2. Restart KOReader
3. Tools → LocalWiki (offline ZIM) → Search articles

## Verified on

- Nothing Phone 3 (Android 17, KOReader v2026.07.1): search, title index and full articles
- Kindle (KOReader v2026.07.1): a real Dune article decompresses in 45 ms
- Test suite: 29 lua smoke checks, 35 KOReader checks, 50 python tests


**Full Changelog**: https://github.com/nar-io/localwiki.koplugin/compare/v0.6.5...v0.6.9

# v0.6.5 · 2026-11-17

**Full Changelog**: https://github.com/nar-io/localwiki.koplugin/compare/v0.6.4...v0.6.5

**Full Changelog**: https://github.com/nar-io/localwiki.koplugin/compare/v0.6.4...v0.6.5

# v0.6.4 · 2026-11-17

**Full Changelog**: https://github.com/nar-io/localwiki.koplugin/compare/v0.6.3...v0.6.4

**Full Changelog**: https://github.com/nar-io/localwiki.koplugin/compare/v0.6.3...v0.6.4

# v0.6.3 · 2026-11-17

**Full Changelog**: https://github.com/nar-io/localwiki.koplugin/compare/v0.6.2...v0.6.3

**Full Changelog**: https://github.com/nar-io/localwiki.koplugin/compare/v0.6.2...v0.6.3

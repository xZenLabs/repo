# 26.11.24-beta · 2026-11-24

## What's Changed

### New Features
- **Custom HTTP headers for Custom APIs**: Added `custom1_headers` and `custom2_headers` options to `xray_config.lua` so you can pass extra headers (one `Header-Name: value` per line) with your requests. Handy if your self-hosted endpoint or proxy sits behind something like Cloudflare Access.

### Improvements
- **Better memory management and background task coordination**: Added optional integration with Storefront's Memory Conductor. When Storefront is installed, X-Ray coordinates its background scans, catch-up fetches, and update checks to avoid memory spikes on low-RAM e-readers, clears caches when memory gets tight, and cleanly cancels background work when your device goes to sleep.
- **Translation updates**: Updated UI translations and localized AI prompts across all supported languages.

### Fixes
* Translate Polish UI strings and fix README duplication by @Pepe-PL in https://github.com/ultimatejimmy/xray.koplugin/pull/171

## New Contributors
* @Pepe-PL made their first contribution in https://github.com/ultimatejimmy/xray.koplugin/pull/171

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.20...26.11.24-beta

# 26.11.18-beta · 2026-11-18

## What's Changed

* Some UI updates

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.17-beta...26.11.18-beta

# 26.11.17-beta · 2026-11-17

- Fix performance with entity underlines
- some UI fixes

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.15-beta...26.11.17-beta

# 26.11.15-beta · 2026-11-15

- Various fixes
- #166 

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.13-beta...26.11.15-beta

# 26.11.13-beta · 2026-11-13

## What's New in 26.11.13-beta

This release includes a major behind-the-scenes cleanup of the plugin, a fix for underlines not showing up on Kobo devices, and several fixes for spoiler gating, character detection, and unit conversion.

### Underlines & Kobo Fixes
- **Fixed underlines on Kobo:** Entity and unit conversion underlines now use KOReader's native view module system instead of hooking into the page paint loop, which fixes missing underlines on Kobo devices.
- **Wavy underline fallback:** If wavy SVG rendering fails or isn't supported on a device, underlines now fall back cleanly to a solid line instead of disappearing.
- **More reliable unit scanning:** If a background unit scan doesn't produce a usable cache, the plugin now falls back to scanning in-process.
- **Cleaner entity underlines & tooltips:** Overlapping matches on the same phrase are now deduplicated so longer names win cleanly, entity footnote taps respect your toggle state, and tooltip auto-dismissal no longer hits timer cancellation errors.
- **Sidecar cache reliability:** Improved directory creation when saving unit and entity caches.

### Character & Spoiler Fixes
- **Better protagonist & family name handling:** Improved AI prompts and name-matching logic so first-person protagonists are reliably extracted, and relational names (like *"Nick"* and *"Nick's Dad"*) are kept as separate characters instead of being merged or flagged as duplicates.
- **Spoiler-safe incremental updates:** Batch and incremental fetches now preserve each character's earliest introduction and story-arc states properly, so characters stay visible on earlier pages of a fetched window without leaking future descriptions.
- **Spoiler-safe mention highlighting:** Highlighting mentions on a page now respects unlocked aliases instead of revealing spoiler-gated ones.

### Other Improvements
- **Major code refactor:** Split the oversized main plugin and UI files into smaller, focused modules to make future updates easier and safer.
- **Updated default Gemini model:** Switched the default primary model to `gemini-4-hydrogen` with Gemini 4 thinking-level support.
- **Cleaner request cancellation:** Canceling an active AI request now also stops any running sequential background tasks.

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.9...26.11.13-beta

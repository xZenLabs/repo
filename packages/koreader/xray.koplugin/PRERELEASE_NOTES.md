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

# 26.11.7-beta · 2026-11-07

## Entity Underlining (optional new feature)

You can now have X-Ray underline characters, locations, historical figures, and terms directly on your book pages as you read. Tapping any underlined name brings up an instant description pop-up without losing your place.

A huge thank you to @Dukko for creating the original user patch that inspired and kicked off this native feature!

**This feature is opt-in and fully configurable.**

### What's New

- **In-Book Entity Underlining**: Automatically underlines people, places, and terms found in your X-Ray data. Tapping an underlined item opens its summary right on the page.
- **Customizable Underline Styles**: Choose from solid, wavy, dotted, dashed, or double underlines with adjustable line thickness and contrast to suit your screen.
- **Tooltip & Footnote Displays**: Pick between a compact tooltip bubble pointing to the word or a bottom panel, along with customizable auto-close timers.
- **Frequency & Category Controls**: Highlight every mention or keep things tidy by only underlining the first appearance per chapter. You can also toggle characters, locations, terms, or historical figures independently.
- **Instant Inline Fetch Support**: When you look up and fetch a new entity while reading, it gets underlined across your book immediately.
- **Smart Matching**: Dialogue transcripts, all-caps speaker tags, and chapter headings are cleanly detected without accidental matches on common lowercase words.

*Note for users who previously installed Dukko's `2-xray-entity-footnotes.lua` patch: entity underlining is now built directly into the plugin, so the old patch file in your patches folder can be safely removed.*

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.6-beta2...26.11.7-beta

# 26.11.6-beta2 · 2026-11-06

Fix #164 

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.6-beta...26.11.6-beta2

# 26.11.6-beta · 2026-11-06

Fix #163 

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.5...26.11.6-beta

# 26.11.4-beta2 · 2026-11-04

- Do unit scanning in the background 

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.2-beta...26.11.4-beta2

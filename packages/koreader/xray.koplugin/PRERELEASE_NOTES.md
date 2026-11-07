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

# 26.11.4-beta · 2026-11-04

- Improve spoiler mode logic
- Improve pre-fetch/collision logic

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.2-beta...26.11.4-beta

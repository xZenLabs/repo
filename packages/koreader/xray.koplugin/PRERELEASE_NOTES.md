# 26.11.24-beta2 · 2026-11-25

Fix #172 for Kobo readers

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.24-beta...26.11.24-beta2

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

# 26.10.6-beta · 2026-10-06

## What's Changed
* Fix Ukrainian unit conversion by @Gargoyle-Gecko in https://github.com/ultimatejimmy/xray.koplugin/pull/146
* Fix: restore unit underlines from cache on book reopen by @Gargoyle-Gecko in https://github.com/ultimatejimmy/xray.koplugin/pull/147

## New Contributors
* @Gargoyle-Gecko made their first contribution in https://github.com/ultimatejimmy/xray.koplugin/pull/146

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.10.2-beta3...26.10.6-beta

# 26.10.2-beta3 · 2026-10-02

## What's Changed

This release focuses on memory optimizations and stability improvements to keep X-Ray running smoothly, especially on older or low-memory e-ink devices like earlier Kindles and Kobos.

* **Low-memory protection**: X-Ray now dynamically monitors available device RAM. If system memory is running critically low, silent background tasks (like automatic chapter fetches and weekly update checks) will quietly step aside to prevent crashes or freezes. Manual requests from the menu still work as usual.
* **Smoother book opening**: Background tasks and automatic unit scans are now deferred for a few moments after opening a book. This gives KOReader the breathing room it needs to render pages and load fonts without competing for CPU and RAM.
* **Unit scanner memory cleanup**: Searching an entire book for units now cleans up temporary search tables in stages rather than holding them in memory, noticeably lowering peak memory usage during book scans.
* **Leaner AI data handling**: Background network requests now clean up raw downloaded buffers and temporary structures immediately after parsing book details.

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.10.2-beta...26.10.2-beta3

# 26.10.2-beta · 2026-10-02

## What's Changed
* Add Slovak and Czech translations with declension-aware lookups by @misko903 in https://github.com/ultimatejimmy/xray.koplugin/pull/138

## Bug Fixes
- Fix #145 
- Fix #144 
- Fix #143 

## New Contributors
* @misko903 made their first contribution in https://github.com/ultimatejimmy/xray.koplugin/pull/138

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.30.1...26.10.2-beta

# 26.9.29-beta · 2026-09-29

- Fix series bug
- Fix alias/lookup bug 
- fix overlapping save bug

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.23-beta...26.9.29-beta

# 26.9.23-beta · 2026-09-23

- fix claude bugs
- update series logic
- fix unit converter range logic 

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.17...26.9.23-beta

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

# 26.9.15-beta · 2026-09-15

### What's New

* **Series Manager**: You can now manage book series directly from the settings menu. View the full reading order, adjust series names and volume numbers, add or remove books using the built-in file picker, and save changes straight to your book's sidecar metadata. Thanks @Juansero29 for the idea and getting started on it.
* **Rebuild X-Ray Data (Clean Fetch)**: Added a new option under *Maintenance* that lets you completely discard cached data for the current book and fetch a fresh profile from AI without having to manually delete cache files. The standard fetch button also dynamically switches between *Fetch* and *Update (Merge)* depending on whether data already exists.
* **Cleaner Gestures**: Removed unnecessary unit scanning and unit converter actions from the dispatcher gesture list to declutter your gesture configuration options.

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.13-beta3...26.9.15-beta

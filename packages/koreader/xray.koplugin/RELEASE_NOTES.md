# 26.10.8 · 2026-10-08

This release focuses on memory optimizations and stability to keep X-Ray running smoothly, especially on older or lower-RAM e-ink devices like earlier Kindles and Kobos, along with new language support and several bug fixes.

### Memory & Performance Improvements

* **Low-memory protection**: X-Ray now monitors available device RAM. When free memory is critically low, non-essential background tasks (like automatic chapter fetches and update checks) quietly pause to prevent crashes and freezes. Manual lookups from the menu continue to work as usual.
* **Smoother book opening**: Background tasks and unit scans are deferred for a few moments after opening a book, giving KOReader room to render pages and load fonts without competing for resources.
* **Unit scanner memory cleanup**: Searching books for units now releases temporary search data in stages, noticeably reducing peak memory usage.
* **Leaner network handling**: Background network requests now clean up raw download buffers and temporary structures immediately after parsing book details.

### New Features & Improvements

* **Slovak and Czech translations**: Added Slovak and Czech language support with declension-aware lookups ([#138](https://github.com/ultimatejimmy/xray.koplugin/pull/138)) by [@misko903](https://github.com/misko903).

### Bug Fixes

* **Unit underlines**: Restored unit underlines from cache when reopening books ([#147](https://github.com/ultimatejimmy/xray.koplugin/pull/147)) by [@Gargoyle-Gecko](https://github.com/Gargoyle-Gecko).
* **Ukrainian unit conversion**: Fixed unit conversion handling for Ukrainian ([#146](https://github.com/ultimatejimmy/xray.koplugin/pull/146)) by [@Gargoyle-Gecko](https://github.com/Gargoyle-Gecko).
* Resolved issues [#143](https://github.com/ultimatejimmy/xray.koplugin/issues/143), [#144](https://github.com/ultimatejimmy/xray.koplugin/issues/144), and [#145](https://github.com/ultimatejimmy/xray.koplugin/issues/145).

### New Contributors

Thanks to our new contributors for helping improve the plugin:
* [@misko903](https://github.com/misko903) in [#138](https://github.com/ultimatejimmy/xray.koplugin/pull/138)
* [@Gargoyle-Gecko](https://github.com/Gargoyle-Gecko) in [#146](https://github.com/ultimatejimmy/xray.koplugin/pull/146)
**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.30.1...26.10.8

# 26.9.30.1 · 2026-09-30

## What's Changed
- Add gpt-6-luna support by @abs3ntdev in https://github.com/ultimatejimmy/xray.koplugin/pull/141
- ix claude bugs
- update series logic
- fix unit converter range logic
- Fix series bug
- Fix alias/lookup bug
- fix overlapping save bug


## New Contributors
* @abs3ntdev made their first contribution in https://github.com/ultimatejimmy/xray.koplugin/pull/141

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.30...26.9.30.1

# 26.9.17 · 2026-09-17

## What's New

- Series Manager: You can now manage book series directly from the settings menu. View the full reading order, adjust series names and volume numbers, add or remove books using the built-in file picker, and save changes straight to your book's sidecar metadata. Thanks @Juansero29 for the idea and getting started on it.
- Rebuild X-Ray Data (Clean Fetch): Added a new option under Maintenance that lets you completely discard cached data for the current book and fetch a fresh profile from AI without having to manually delete cache files. The standard fetch button also dynamically switches between Fetch and Update (Merge) depending on whether data already exists.
- Cleaner Gestures: Removed unnecessary unit scanning and unit converter actions from the dispatcher gesture list to declutter your gesture configuration options.
- Smarter Fetch Menu: The main menu now adapts based on whether you've fetched data for your book yet. If a book has no X-Ray data, the menu shows Fetch X-Ray Data to run a clean first-time analysis. Once data is saved, it switches to Update X-Ray Data (Merge) for your regular reading updates.
- Quick Fetch from Empty Screens: Opening Timeline, Locations, or Historical Figures on a book without any X-Ray data will now ask if you'd like to fetch data from AI right then and there, rather than just giving you an empty screen notice.
- Add page turn button support to paginated areas

## Fixes 
- Fix bug with Claude on certain thinking levels
- Fix bug with mentions scanning on some devices and is some situations


**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.11.2...26.9.17

# 26.9.11.2 · 2026-09-12

- Fix welcome screen bug.

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.11.1...26.9.11.2

# 26.9.11.1 · 2026-09-12

- Fix bug with mentions when access from the menu
- Fix bug with sorting options

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.11...26.9.11.1

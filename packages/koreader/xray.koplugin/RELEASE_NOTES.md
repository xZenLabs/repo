# 26.9.30.1

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

# 26.9.17

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

# 26.9.11.2

- Fix welcome screen bug.

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.11.1...26.9.11.2

# 26.9.11.1

- Fix bug with mentions when access from the menu
- Fix bug with sorting options

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.11...26.9.11.1

# 26.9.11

- Fix bug in the update release notes dialog https://github.com/ultimatejimmy/xray.koplugin/issues/125
- Update catchup logic to be more detailed with more triggers. Thanks to @mrpops2ko for getting started on this.
- Fix back to reading button in mentions bar
- Fix image jump bug

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.9...26.9.11

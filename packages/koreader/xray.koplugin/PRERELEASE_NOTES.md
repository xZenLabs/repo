# 26.9.23-beta

- fix claude bugs
- update series logic
- fix unit converter range logic 

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.17...26.9.23-beta

# 26.9.15-beta

### What's New

* **Series Manager**: You can now manage book series directly from the settings menu. View the full reading order, adjust series names and volume numbers, add or remove books using the built-in file picker, and save changes straight to your book's sidecar metadata. Thanks @Juansero29 for the idea and getting started on it.
* **Rebuild X-Ray Data (Clean Fetch)**: Added a new option under *Maintenance* that lets you completely discard cached data for the current book and fetch a fresh profile from AI without having to manually delete cache files. The standard fetch button also dynamically switches between *Fetch* and *Update (Merge)* depending on whether data already exists.
* **Cleaner Gestures**: Removed unnecessary unit scanning and unit converter actions from the dispatcher gesture list to declutter your gesture configuration options.

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.13-beta3...26.9.15-beta

# 26.9.13-beta3

### What's New: Address #114 

- **Smarter Fetch Menu**: The main menu now adapts based on whether you've fetched data for your book yet. If a book has no X-Ray data, the menu shows **Fetch X-Ray Data** to run a clean first-time analysis. Once data is saved, it switches to **Update X-Ray Data (Merge)** for your regular reading updates.
- **Rebuild X-Ray Data**: Added a **Rebuild X-Ray Data (Clean Fetch)** option under *Settings → Maintenance*. If cached events or character notes ever get messy or out of sync, you can completely refresh the book's data with a single tap (with a confirmation step) without losing your saved image favorites or series settings.
- **Quick Fetch from Empty Screens**: Opening Timeline, Locations, or Historical Figures on a book without any X-Ray data will now ask if you'd like to fetch data from AI right then and there, rather than just giving you an empty screen notice.


**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.13-beta2...26.9.13-beta3

# 26.9.13-beta2

- Add page turn button support

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.13-beta...26.9.13-beta2

# 26.9.13-beta

- Fix bug with Claude on certain thinking levels
- Fix bug with mentions scanning on some devices and is some situations

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.11.2...26.9.13-beta

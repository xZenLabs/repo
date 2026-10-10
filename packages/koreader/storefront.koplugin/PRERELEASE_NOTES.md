# 26.10.9-beta · 2026-10-09

## What's Changed

This release focuses on making Storefront significantly faster and more responsive, especially on older e-ink devices like Kindle Paperwhites.

* **In-Place Tab Switching**: Switching between tabs (*Plugins*, *Patches*, *Fonts*, *Screensavers*, *Installed*, and *Updates*) no longer closes and reopens the dialog. The interface now updates in-place with partial e-ink screen refreshes for a much smoother experience.
* **Instant Page Turning**: Turning pages across all catalog tabs is now immediate. Navigating forward or backward updates only the visible items on screen instead of reloading the catalog from storage.
* **Faster Screensavers Tab**: Eliminated the long loading delay when opening the Screensavers tab:
  * Uses KOReader's native, high-speed decoder for much faster catalog loading.
  * Image paths and details are now prepared on-demand only for the items currently visible on your page, rather than thousands of entries at once.
  * Catalog order is loaded directly without unnecessary sort passes on default views.
  * Switching between tabs keeps the catalog ready in memory so tapping back into Screensavers is instantaneous.
* **Better Memory Management**: All temporary catalog caches are automatically cleared from RAM the moment you close Storefront, keeping full memory free for reading your books.
* **Cached Tab Icons**: Tab bar icons are cached in memory after the first draw to prevent redraw stutter when tapping tabs.

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.10.7-beta3...26.10.9-beta

# 26.10.7-beta3 · 2026-10-08

- more screensaver efficiency improvements

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.10.7-beta2...26.10.7-beta3

# 26.10.7-beta2 · 2026-10-08

- Fix screensaver collection settings memory issue

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.10.7-beta...26.10.7-beta2

# 26.10.7-beta · 2026-10-07

Update screensaver catalog logic and reduce memory usage for low powered devices

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.10.6-beta2...26.10.7-beta

# 26.10.6-beta2 · 2026-10-07

Update screensaver sorting logic

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.10.6-beta...26.10.6-beta2

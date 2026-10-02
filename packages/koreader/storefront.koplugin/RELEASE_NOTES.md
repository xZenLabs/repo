# 26.10.2 · 2026-10-02

- Address memory issues with lower powered devices
- Add check for RB catalog to not download/refresh if there are no changes
- fix bug in rating system

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.10.1...26.10.2

# 26.10.1 · 2026-10-01

## What's new
- Add Readerbackdrop as an additional source for screensavers, open the filter dialog to change the sources
- Move refresh button to the top level of settings

## Bug fixes
- Fix refresh timestamp
- Update some translations #5066 
- Updated catalog refresh logic to be more consistent and follow the notification frequency settings
- Made sure screensaver catalog is updated at the same time
- Minor performance improvement when removing a screensaver from the collection

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.9.25.1...26.10.1

# 26.9.25.1 · 2026-09-25

- Fix bug with blueprint on Installed tab for some devices

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.9.25...26.9.25.1

# 26.9.25 · 2026-09-25

## What's Changed

* **New Blueprints Feature**: Easily snapshot, export, and share your KOReader customization setup! With a simple 6-digit code, you can quickly replicate all your installed plugins, user patches, fonts, screensavers, and Storefront settings onto another device.
  * Access it via **Settings → Blueprints** (or the **[ Blueprint ]** toolbar button on the Installed tab).
  * Check out the [Blueprints Wiki Guide](https://github.com/ultimatejimmy/storefront.koplugin/wiki/8.-Blueprints) for full documentation.
* **Reorganized Settings Menu**: Re-architected and streamlined the Settings interface into clean, structured categories for easier navigation.
* **Notification Settings & Persistence**: Fixed notification configuration handling so custom check frequencies (e.g., daily vs. weekly) persist properly across restarts ([#5064](https://github.com/ultimatejimmy/storefront.koplugin/issues/5064)).
* **Installed Font Filtering**: Fixed an issue on the Installed tab where default core fonts and user-installed fonts were miscategorized when filtering.
* **Duplicate Notification Fix**: Resolved an issue where Storefront updates were listed multiple times under both their localized name and default English name in update notifications ([#5061](https://github.com/ultimatejimmy/storefront.koplugin/issues/5061)).
* **Localization**: Added Slovak (`sk`) translation support thanks to @misko903 ([#5065](https://github.com/ultimatejimmy/storefront.koplugin/pull/5065)).


**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.9.15...26.9.25

# 26.9.15 · 2026-09-15

## What's Changed

- **Install from branch**: You can now install plugins directly from any Git branch, making it easy to test experimental features, pull requests, and preview builds right on your device ([#5057](https://github.com/ultimatejimmy/storefront.koplugin/issues/5057)).
- **Update notifications**: Added an update notification system to let you know when new versions are available for your installed items, with customizable options in settings.
- **Screensavers catalog performance**: Updating the screensaver catalog is much faster and more efficient, especially on lower powered devices
- **Screensavers refresh**: Triggering a catalog refresh now automatically updates the screensavers catalog as well, ensuring you always see the latest additions without needing extra steps.

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.9.9...26.9.15

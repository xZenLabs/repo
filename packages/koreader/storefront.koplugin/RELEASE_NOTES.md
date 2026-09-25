# 26.9.25

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

# 26.9.15

## What's Changed

- **Install from branch**: You can now install plugins directly from any Git branch, making it easy to test experimental features, pull requests, and preview builds right on your device ([#5057](https://github.com/ultimatejimmy/storefront.koplugin/issues/5057)).
- **Update notifications**: Added an update notification system to let you know when new versions are available for your installed items, with customizable options in settings.
- **Screensavers catalog performance**: Updating the screensaver catalog is much faster and more efficient, especially on lower powered devices
- **Screensavers refresh**: Triggering a catalog refresh now automatically updates the screensavers catalog as well, ensuring you always see the latest additions without needing extra steps.

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.9.9...26.9.15

# 26.9.9

## What's Changed

* **Performance and memory optimizations**: Overhauled background handling and memory usage across catalog browsing, settings, and ratings to keep things fast and prevent out-of-memory crashes on resource-constrained e-readers.
* **Patch installation and removal fix**: Fixed a bug where installing or removing patches would fail to apply cleanly or not update status properly in the UI.
* **Improved update checker**: Refined the update checking routine so checking for new releases is faster, smoother, and more reliable.
* **Pre-release tracking in catalog**: The catalog now stores the latest pre-release versions so that pre-release update checks can pull accurate version data without extra lookups.
* **Restart fix for Kobo devices**: Fixed an issue where tapping the restart button after updates or installs caused a freeze on Kobo hardware.

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.9.3...26.9.9

# 26.9.3

## What's New

- **Non-touch device support**: You can now navigate and use Storefront entirely using physical buttons and page-turn keys.
- **Less screen flashing**: Reworked e-ink refresh behavior to cut down on unnecessary full-screen flashes while browsing around.
- **Better performance**: Noticeably snappier overall, especially on older and lower-powered e-readers.
- **Faster update checks**: The *Check Updates* button is much more responsive and loads faster.
- **Download reliability**: Fixed issues with downloads failing, including a bug that caused larger files to fail when running *Update All*.
- **UI fixes for long names**: Cleaned up button layouts so long version numbers no longer overflow or wrap awkwardly, and fixed folder picker issues with long screensaver directory names.
- **Smoother tab loading**: Cleaned up the loading and refresh behavior when viewing READMEs and the *Versions* tab.
- **Font tracking**: Improved font tracking/management.

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.8.23...26.9.3

# 26.8.23

## What's New in 26.8.23

### Features & Improvements

* **Custom screensaver folder**: You can now choose a custom folder location for your screensavers using a built-in folder browser in the settings, or reset back to default at any time.
* **Automatic doc refresh**: The *README* and wiki views now automatically refresh whenever content changes, so you always see the latest details without needing to manually reload.
* **Clearer screensaver messaging**: Improved in-app status messages and logging when managing and applying screensavers.
* **New fonts**: Added *Fast Sans*, *Fast Serif*, and *Fast Sans Dotted* to the font catalog.
* **Cleaner Updates tab**: Removed the redundant search bar from the Updates screen to keep the page focused strictly on pending updates.
* **Better dialog sizing for translations**: Adjusted spacing and sizing across settings, filters, and info dialogs so translated text won't get clipped or cut off.
* **Screensaver sorting**: Tweaked the sort ordering for screensavers so browsing and finding wallpapers is smoother.
* **Installed item count**: Fixed how item counts are calculated and displayed on the Installed tab.

### Fixes

* **Font detection on WSL**: Fixed font path resolution issues when running KOReader in WSL environments.

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.8.18.2...26.8.23

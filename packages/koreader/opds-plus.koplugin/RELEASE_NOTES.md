# v1.2.1 · 2026-11-09

# OPDS Plus v1.2.1

A bug-fix release with cover cache, catalog compatibility and sync fixes since v1.2.0.

### Fixed
- Covers are cached on Kindle and other devices where KOReader runs from a relative directory (Issue #86, PR #87).
- Cached covers no longer miss and download again after LuaJIT switches from interpreted to compiled code (PR #97).
- Cover cache robustness: falls back to KOReader's data directory on versions without `getFullDataDir()`, creates relative cache directories in place, and writes covers atomically so an interrupted write cannot leave a truncated cover.
- Catalog URLs with a local hostname, such as `http://booktrove:8083/opds`, can be added (Issue #91, PR #95).
- Entries linked with the OPDS `crawlable` relation, like the Standard Ebooks "All Ebooks" feed, open instead of failing with "Cannot get catalog info from nil" (Issue #83).
- Listings no longer lose the entries after one with an empty `<content/>` tag (Issue #100).
- "Sync all catalogs" and "Force sync all catalogs" say when no catalog has "Sync catalog" ticked instead of reporting "Up to date!", and the gesture versions wait for the network like the menu entries (Issue #96).
- A sync that fails shows the error instead of leaving "Synchronizing lists…" on screen. Feeds with a link-less entry and Project Gutenberg style catalogs with a single-book sub-feed now sync (Issue #96).
- KOReader's plugin manager can delete OPDS Plus's settings and cover cache with "Disable plugin and delete settings" and "Delete plugin and settings". Downloaded books are kept (Issue #82).

### Changed
- Updated GitHub Actions dependencies for checkout and release publishing.

### Notes
- Covers cached by earlier versions are downloaded once more after updating, because the cache file naming changed.

### Thanks
Special thanks to these contributors for their work in this release cycle:
- @cardoso42 (Kindle cover cache, #87)
- @demrom (stable cover cache keys, #97)
- @439qi (local hostnames, #95)

Full changelog:
https://github.com/greywolf1499/opds_plus.koplugin/blob/main/CHANGELOG.md

# v1.2.0 · 2026-03-19

# OPDS Plus v1.2.0

This release includes merged PRs, issue resolutions, and new user-facing settings since v1.1.0.

> [!IMPORTANT]
> **Upgrade method for existing users:** This release is based on a complete plugin rewrite.
> To avoid stale files and update issues, **remove the old `opds_plus.koplugin` directory entirely**, then install the new release fresh.

### Added
- Book Info Dialog for at-a-glance book metadata with improved cover handling.
- Direct dispatcher actions for:
  - OPDS Plus: Sync all catalogs
  - OPDS Plus: Force sync all catalogs
- Cover pipeline improvements with disk-backed cache and lifecycle-safe image loading.
- New Cover Settings:
  - Prefer Large Covers (quality-first source selection)
  - Enable Cover Cache toggle
  - Advanced cache controls: max size, TTL, and manual cache clear

### Changed
- Refactored debug architecture to standardize logging through shared utilities.
- Extended state-manager usage across UI menu components.
- Removed obsolete/dead code and simplified some loader internals.
- Updated GitHub Actions dependencies for checkout and artifact workflows.

### Fixed
- Gesture registration failures (Issue #58).
- Duplicate PDF entries in results (Issue #57).
- Book info dialog stability issues, including filename capture timing and cover widget behavior.

### Thanks
Special thanks to these contributors for their work in this release cycle:
- Michael Cummings (@kodermike)
- Gavin Mogan (@halkeye)

### Documentation
- Added KOReader installation/upgrade path reference:
  https://github.com/koreader/koreader/wiki\#installationupgrading
- Updated README and CHANGELOG to cover major additions and settings for 1.2.0.

Full changelog:
https://github.com/greywolf1499/opds_plus.koplugin/blob/main/CHANGELOG.md

# v1.1.0 · 2025-11-18

# OPDS Plus v1.1.0 - Polish & Performance Release

This release focuses on polishing the user experience, fixing bugs discovered during real-world testing, and optimizing space utilization across all device sizes.

## 🎯 Highlights

### ✨ Better Text Display
- Titles and authors now show **ellipsis (…)** when truncated
- Smart word-aware truncation for cleaner breaks
- UTF-8 safe for international characters

### 📐 Optimized Layouts
- **List View**: Dynamically fits maximum items with minimal whitespace
- **Grid View**: Automatically maximizes rows based on screen height
- Works perfectly on small e-readers, tablets, and large desktop displays
- No more wasted space at the bottom of pages!

### 🐛 Bug Fixes
- Fixed release package containing nested directories
- Fixed crashes in Grid Layout and Border settings menus
- Fixed `%%` appearing in confirmation messages
- Fixed version display in About dialog
- Fixed text truncation crashes

### 🔧 Developer Features
- **Debug Mode Toggle**: Enable verbose logging when troubleshooting
- **Version Display**: Now shown in settings menu
- Cleaned up excessive logging for better performance

## 📦 Installation

1. Download `opds_plus.koplugin.zip` from assets below
2. Extract to your KOReader plugins directory:
   - **Linux/Mac**: `~/.config/koreader/plugins/`
   - **Android**: `/sdcard/koreader/plugins/`
   - **Kindle**: `/mnt/us/koreader/plugins/`
3. Restart KOReader
4. Access via: **File Manager → Menu → OPDS Plus Catalog**

## ⚙️ Settings

All settings accessible via: **OPDS Plus Catalog → Settings**

- **Display Mode**: Switch between List and Grid views
- **List View Settings**: Cover size presets (Compact/Regular/Large/Extra Large)
- **Grid View Settings**: Layout presets, borders, and styling
- **Font & Text**: Customize fonts, sizes, colors
- **Developer**: Toggle debug mode for troubleshooting

## 🔄 Upgrading from v1.0.0

Simply replace the plugin directory with the new version. All your settings and catalogs will be preserved.

## 🙏 Acknowledgments

Thanks to everyone (myself, so far) who tested v1.0.0 and provided feedback! This release addresses all reported issues and includes several UX improvements based on real-world usage.

---

**Full Changelog**: https://github.com/greywolf1499/opds_plus.koplugin/blob/main/CHANGELOG.md

# v1.0.0 · 2025-11-18

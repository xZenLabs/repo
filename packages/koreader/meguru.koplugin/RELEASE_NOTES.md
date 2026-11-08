# v1.8.1 · 2026-11-08

### Fixed

- Pinch in pan & zoom changes and remembers the zoom level.
- Edge swipes in panel views no longer zoom.
- Page turns right after a page appears are no longer missed.

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.8.0...v1.8.1

# v1.8.0 · 2026-11-07

### New

- Local `.cbz` covers and metadata load much faster.
- (.meguru) A page that fails to load now stops the forward turn. The next turn retries a transient failure (with a notice), or names a permanent one and skips it.
- Taps and swipes made while a page or panel is still rendering are ignored instead of replayed.
- Two-page view fills the blank under the shorter page with its margin colour.

### Fixed

- Large local pages that would run the device out of memory. Such a page is refused, retried once, then skipped with a "too large" message.
- Freezes of tens of seconds when Kavita or Suwayomi is unreachable.
- Dust widening the page-number strip and cropping into the artwork.
- Errors when pinching or spreading a panel whose image failed to load.

# v1.7.3 · 2026-11-02

## New features

- **ZenPM support**: Meguru can now be installed and updated from [ZenPM](https://github.com/xZenLabs/zen-pm). Search for `meguru`. (#10)

## Bug fixes

- **Derainbow works on Android again**: the native libraries are now copied into the app's private files directory, since shared storage is mounted `noexec`. Refs #9.
- **Compatible with KOReader's new OPDS dialog**: the *Meguru this series* row now appears in both the old `showDownloads` and the new `getDownloadButtons` dialog. Refs koreader/koreader#16311.


## New Contributors
* @KristanLaimon made their first contribution in https://github.com/Craftwork2720/meguru/pull/10

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.7.1...v1.7.3

# v1.7.1 · 2026-10-30

## Bug fixes

- Fixed turned panels appearing upside down on a landscape screen.
- Fixed **Meguru this series** missing on KOReader nightly builds ([koreader/koreader@dad1ad4](https://github.com/koreader/koreader/commit/dad1ad44335fafb1070d524c9ffd2fa2ce2da81d)).
- Fixed books opened from a just-added OPDS catalog not creating their series folder.

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.7.0...v1.7.1

# v1.7.0 · 2026-10-25

## Meguru v1.7.0

Two new optional integrations.

### [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) (OPDS catalog browser)

- **▶ Meguru this series** row in Bookshelf's OPDS catalog window opens a series directly in Meguru.
- **`.meguru` files also open from folder shelves** with bookshelf.koplugin 5.5.0+.

### [Panels+](https://github.com/KristanLaimon/PanelsPlus)

- **Panels+ added as an option for the long-press.** *Panel view* puts `panels+` first, followed by `off` and all three Meguru views: `panel cut`, `pan & zoom`, and `free view`.
- **Panels+ OCR text selection now works in Meguru**, in the Panels+ view only.

### Thanks

- [AcidWeb](https://github.com/AcidWeb) for [bookshelf.koplugin PR #496](https://github.com/AndyHazz/bookshelf.koplugin/pull/496), which made the Bookshelf integration possible

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.6.0...v1.7.0

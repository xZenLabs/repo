# v1.8.3 · 2026-11-10

### Fixed

- Page-turn buttons no longer invert when a wide page is auto-rotated.
- Books without series information no longer show series navigation entries or a blank series name (#12).

### Changed

- **Rotate wide pages** now uses rotation arrows instead of "left 90°" and "right 90°".

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.8.2...v1.8.3

# v1.8.2 · 2026-11-08

### Fixed

- Page turning did not work on the KOReader stable version (#11).


**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.8.1...v1.8.2

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

# v1.8.5 · 2026-11-11

### Fixed

- Page turns no longer stop working with ZenOS enabled.
- "In landscape" two-page view now works on tablets whose natural orientation is landscape (rotation mode 0).
- Two-page view no longer adds white bands above and below the pages when crop auto and flexible gutter crop the two pages differently.
- Local `.cbz` covers come from MuPDF page 1 again, the same page the reader opens.

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.8.3...v1.8.5

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

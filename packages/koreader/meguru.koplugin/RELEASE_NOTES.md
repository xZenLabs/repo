# v1.8.9 · 2026-11-18

## Added

- Edge swipe gestures in panel views (off by default). Enable in Meguru → Settings → Edge swipe gestures in panel views. by @Charliechin in #15
- "Meguru: toggle panel view" action, bindable to a gesture, quick menu or remote button. by @Charliechin in #17

## Fixed

- Panel Cut and Pan & Zoom now follow the Reading direction. by @Charliechin in #14
- Bluetooth remote page buttons now work in Panel Cut and Pan & Zoom. by @Charliechin in #16

## New contributors

- @Charliechin made their first contribution in #14

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.8.7...v1.8.9

# v1.8.8 · 2026-11-18

## Added

- Edge swipe gestures in panel views (off by default): brightness on the left edge and warmth on the right, as set in Gestures. Enable in Meguru → Settings → Edge swipe gestures in panel views. by @Charliechin in #15

## Fixed

- Panel Cut and Pan & Zoom now follow the Reading direction. by @Charliechin in #14
- Bluetooth remote page buttons now work in Panel Cut and Pan & Zoom. by @Charliechin in #16

## New contributors

- @Charliechin made their first contribution in #14

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.8.7...v1.8.8

# v1.8.7 · 2026-11-15

## Fixed

Fixes some `.cbz` files not opening.

- A damaged or unusual ZIP/image header no longer stops a local `.cbz` from opening. The page now falls back to the older density-based size.
- Page buffers on colour screens are now also capped by available memory (in bytes), not just by pixel count. Large high-DPI pages should be less likely to run out of RAM on smaller devices.
- If a page can't be rendered at its full source size, it's retried at the lower density size instead of being left blank.

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.8.6...v1.8.7

# v1.8.6 · 2026-11-13

## Fixed

- Blurry local `.cbz` pages on high-DPI images ([#13](https://github.com/Craftwork2720/meguru/issues/13)).

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.8.5...v1.8.6

# v1.8.5 · 2026-11-11

## Fixed

- Page turning works with Zen UI again.
- The "In landscape" two-page view now works on tablets that are landscape by default (rotation mode 0).
- Two-page view no longer shows white bands above and below the pages when auto crop and flexible gutter crop cut the two pages differently.
- Local `.cbz` covers are rendered with MuPDF again.

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.8.3...v1.8.5

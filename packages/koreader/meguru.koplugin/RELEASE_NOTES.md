# v1.8.10 · 2026-11-27

## Added

- Setting "Exclude from reading statistics" (Meguru → Settings, off by default). When enabled, Meguru books no longer add reading time, page turns or sessions to KOReader's statistics. Other books are not affected. Applies the next time a book is opened.

## Fixed

- Fixed a crash when long-pressing a page that failed to load. The panel view now simply doesn't open.
- Fixed a page being stretched to fill the screen after a retry following a load error. It now keeps its real proportions ([#18](https://github.com/Craftwork2720/meguru/issues/18)).
- Fixed a two-page spread mixing one-page and two-page layouts after a retry following a load error. It now keeps the two-page fit.

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.8.9...v1.8.10

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

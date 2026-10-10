# v1.5.3 · 2026-10-10

## Bug fixes

- **No more crash on Android while the file browser builds covers.** Opening a folder of local `.cbz` files or `.meguru` streams could close the app: KOReader builds covers in a background process, and that process was asking Android two questions only the main one may ask — the answer it got was an abort. Both are gone; those answers are now taken in the main process ([#4](https://github.com/Craftwork2720/meguru/issues/4))
- Everything else is untouched: reading, panel view, two-page view and streaming are unchanged, and covers outside Android are fetched exactly as before

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.5.2...v1.5.3

# v1.5.2 · 2026-10-10

# New features

- **Derainbow** — removes the rainbow shimmer on colour e-ink screens. All credit goes to [Euphoriyy](https://github.com/Euphoriyy) and his [derainbowify.koplugin](https://github.com/Euphoriyy/derainbowify.koplugin). Off by default, shown only on colour screens
- **Show in OPDS** — opens the OPDS browser on the book's series, from its Info popup or the on hold **file** menu (.meguru)
- **ComicInfo.xml switch** — Settings → *Read metadata from ComicInfo.xml*. On by default; off = local `.cbz` titled by file name

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.4.0...v1.5.2

# v1.4.0 · 2026-10-03

## New features

- **Two-page view**: shows two pages at once as a spread (off / landscape only / always, set per book). Wide pages are shown alone and the pairing restarts after them, so spreads never get cut in half
- **Pair offset**: lets you shift which pages get paired, for books where the pairing is off by one page. Can also be bound to a gesture
- **Flexible gutter**: brings back as much of the trimmed inner margin as fits between the two pages, without exceeding what the original page had
- **Bottom menu reorganized** into 4 tabs: Reading, Page, Rotation, Tone — plus an Info button showing current page, progress, and book metadata (with full description in its own popup)

## Improvements

- Shorter pages in a pair are now scaled up to fill the space, so mismatched page heights no longer leave blank space
- Panel cropping is now flush on all sides, and keeps a background frame on dark pages
- Slanted-border panels are now cropped along their actual border instead of the first detected line
- Menu rows renamed to match what they do: *Crop*, *Reading direction*, *Pair offset*, *Panel view*, *View mode* (now under *Fit*), and *Tone* has its own tab again
- Left/right arrows now navigate panel views in the book's own reading direction

## Bug fixes

- Fixed an issue where opening a book would request a page before the first one, causing a failed fetch (HTTP 400)
- Page numbers touching the edge of the artwork are now cropped correctly again
- Fixed a visual glitch where switching crop from off to auto briefly showed the old margin color

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.3.0...v1.4.0

# v1.3.0 · 2026-09-30

## New features

- The crop tab has a new **Long-press** row: what a long-press does — Panel Cut, Pan & Zoom, Free View or off — per book
- A long-press on that row makes a view the default for new books
- The space around a cropped page is filled with the colour of the margin the crop trimmed

## Improvements

- *Page Crop* at *auto* now trims the margins, removes the printed page number and leaves blank pages whole — one setting instead of three rows
- Borders are trimmed by whether they are *uniform* rather than by how light or dark they are, so colour, grey and black frames are cropped
- Cropping does about half the work it used to per page turn

## Bug fixes

- The page-number crop no longer removes things that are not page numbers — a sound effect, a boxed title
- The page a book opens on is now cropped too, not just the pages after it
- Night mode darkens paper and leaves colours untouched
- Fixed a conflict with `pagenumbercrop.koplugin`: Meguru's own crop takes priority

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.2.0...v1.3.0

# v1.2.0 · 2026-09-28

new: **Contrast**, **Saturation** and **Dithering** in the bottom menu

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.1.1...v1.2.0

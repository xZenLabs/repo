# v6.11.1

**Changed**

- Moved the chapter bar out of the "This book" section into its own "Chapters" section, placed directly below the "This chapter / Next chapter" row.

- With the skim-style bar selected, the "Chapters" heading is dropped and the skim bar becomes the first element of the "This book" section, right under its header.

# v6.11.0

**New**

Skim bar chapter view

- Added an alternative to the per-chapter bar chart in the Book progress popup. It is a single bar drawn like the one in KOReader's "Skim to" dialog: filled up to the current page, with a separator at every chapter start and the position marker (top and bottom triangles) at the current page.
- Chapter separators are drawn black or white, whichever contrasts with the color underneath.

- Settings → Advanced settings → Book progress popup → Chapter bar style
  - Chapter bars: the existing bar chart (default).
  - Skim bar: the new view.

# v6.10.5

**Changed**

- Book stats view: The "This book" section now orders its rows based on the progress bar setting.
  - Progress bar on: reading time row, then the read % row (percent + pages), then the progress bar.
  - Progress bar off: the read % row moves to the top, above the reading time row.

# v6.10.4

**Changed**
Switched reading time and read% rows on Book progress view - the progress bar now under te reading %.

# v6.10.3

**Fixed**
- Book stats popup: 
  - in the "Next 2 chapters" pages cell, the short
  page-count unit (e.g. "o.", "p.") no longer sits lower than and
  closer to the number than in the rest of the popup — it's now
  vertically centered with the same spacing used everywhere else.
  - pages cell now shows the
  full "page"/"pages" word whenever it fits, same as the regular
  (non-split) pages view, and only abbreviates when the translated
  word is too long for the available space.

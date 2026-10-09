# v7.4.5 · 2026-10-09

### Changed
- Average length replaced with **"Typical length":**
  It is the median length of the real chapters, not a mean over all TOC entries. Entries that aren't real chapters are filtered out first:
  1. Entries of 1 page are dropped (title page, dedication, part dividers).
  2. Entries under 1% of the whole book's pages are dropped, however many there are, so stubs can't dominate even when they outnumber chapters.
  3. Entries under 20% of the median of what's left are dropped, repeated until nothing more falls out (max 8 passes).
  4. The result is the median of the remaining entries. In time mode it is multiplied by the average time per page.
  If filtering would leave nothing, all entries count.
  Example: chapters of 1, 2, 132, 139, 12, 2, 1 min now give about 2:15
  instead of a value dragged down by the short entries.

# v7.4.4 · 2026-10-09

### Changed

Book progress: show "27 / 88 chapters" instead of "chapters read"

# v7.4.3 · 2026-10-09

### Fixed

- Book info popup: the reading time in the pages · time row could differ by a minute from the “read so far” value in Book progress (for example 1:10 vs 1:11). The popup truncated the minutes, while Book progress rounds them to the nearest minute. Both now use the same formatter (Locale.formatTimeHHMM), so the values always match.

### Changed

- Book info popup: the row now reads “N pages read · H:MM reading time” instead of “N pages · H:MM reading time”, so it is clear the number counts pages actually read.
- Book info popup: the reading time now follows KOReader’s global “Duration format” setting (classic, modern or letters), like the rest of the plugin, instead of always showing a hardcoded H:MM.

# v7.4.2 · 2026-10-09

### Changed
- "chapters read" and "chapters left" labels in the Book progress popup now
  use singular/plural forms (e.g. "1 chapter left"), in all supported languages.

# v7.4.1 · 2026-10-09

Small fix for hungarian translation for text: chapters read

# v7.5.0 · 2026-10-10

### Added
- **Daily goal | Weekly goal** section above "Last week", showing time read today and this calendar week against your goals (e.g. `0:23 / 0:30`). Durations follow KOReader's duration format setting.
  - Long press the section to set a goal with an hours/minutes picker.
  - Tap it to see how many days / weeks in a row you have met the goal (today or this week doesn't break the run while it is still in progress).
  - The streak is cached: closed days/weeks never change, so the next tap only checks the periods since the last one. The cache is reset when you change the goal or the week start, and on **Reload data** (long press the title bar). Opening the popup itself is not slowed down.
  - Defaults: 30 minutes a day, 5 hours a week.
  - The week starts on the day set in the plugin's week start setting.
  - Can be turned off in Advanced settings ▸ Reading insight popup ▸ **Daily / weekly goal**.
- **Last week layout** setting (Advanced settings ▸ Reading insight popup): *Compact* (default) or *Full* (the previous layout).

### Changed
- **Last week** now shows a single row by default: total and daily average for either reading time or pages read. Tap the "Last week" header to switch between the two views; the choice is remembered between openings.
- Tapping a value still opens the 8-week trend popup.

### Notes
- The goal streak applies the currently set goal to the whole history. If you edit or delete reading data in the statistics database, use **Reload data** to refresh the cached streak.

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

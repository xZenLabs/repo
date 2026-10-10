# v7.5.3 · 2026-10-10

### Changed
- "Last week" is now "Last 7 days" in all languages, since the section shows a rolling 7-day window, more clear what doest this show
- "Annual goal" is now "Yearly goal"
- Finished books counter now reads "27 / 30" instead of "27/30"

# v7.5.2 · 2026-10-10

### Changed
- Daily/weekly goal popup: the “default values” button now shows a readable value (e.g. “Default: 00:30/30m” / “Default: 05:00/5h”) instead of KOReader’s raw “Default values: 0 : 30” / “5 : 0”.
  - The value follows KOReader’s duration format setting.

# v7.5.1 · 2026-10-10

### Added
- **Months chart layout** setting (Settings → Reading insight popup → "Months chart layout"). The yearly bar chart in Reading insights can now show either **2 rows of 6 months** (default, unchanged) or **all 12 months in a single row**. Landscape already used a single row and is unaffected by the setting.

### Changed (landscape only)
- **Reading insights popup:** if the page is still taller than the screen after the bar charts have been sized, so that a scroll bar would appear, all text (section headers, values, labels, small print and the title) is scaled down by the same percentage until the scroll bar is gone.
  - The scale never goes below 50% of the configured sizes, and no font role drops below 8 pt. If it still doesn't fit at that point, the page scrolls as before.
  - The scale that worked last time is reused as the first guess on the next open.
  - It is discarded and recalculated whenever any of the plugin's settings (or the interface language) change, for example when a section is switched on or off.
- **Streak popup:** the popup is only as wide as it needs to be. It is wide enough for the calendar (week column and seven day squares), the month title with its paging arrows, the "Last read" line, the "Current streak" / "Best streak" headers and each "<n> days | <n> weeks" figure to stay on one line. Previously it always took 94% of the screen width. The calendar keeps the cell size that fits the screen height.
- **Streak history popup** (opened from the streak popup):
  - Shows 10 days per page instead of 21. The page size follows screen rotation while the popup is open.
  - Is at most 50% of the screen wide, or wider if the title, the date range with both paging arrows (measured over every page) and one row (date, a minimal bar, value) need it. It is never wider than before (88%).
- **Reading heatmap popup:** the popup is never taller than 94% of the screen height, the same limit the other popups use, so it no longer touches the bottom edge. If it would be taller, the popup becomes narrower and the heatmap squares shrink with it until it fits. It will not go below 40% of the screen width or 4 px squares. Already-loaded data is reused while fitting, so nothing is queried twice.

### Unchanged
- Portrait layouts, sizes and fonts are exactly as before. The new "Months chart layout" option is the only new behaviour that can affect portrait, and only if you select it.

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

# v8.7.10 · 2026-11-04

### Fixed

- The Achievements info dialog appearing behind the list when SimpleUI is installed #87 (Thanks: @NijatTagizada )

# v8.7.9 · 2026-10-28

### Changed
- All-time "pages read" is now counted per book/page/day, the same way as Last 7 days, the monthly and yearly totals and the streak periods. A page read on several days counts once per day, so the all-time total always matches the sum of the per-day totals.
- After updating, run "Reload data" once to refresh the cached all-time figure.

# v8.7.8 · 2026-10-24

### Changed

- Reading calendar: without the cover shadow, a day's books are stacked from the bottom left (first book in front, the others behind it, up and to the right), which looks better than the shadowed layout without its shadow. The layout with the shadow is unchanged.

# v8.7.7 · 2026-10-24

### Changed

- 1 px cover frame. The shared cover frame is now exactly 1 px thick (it was at least 2 px). This applies to Book info, the Reading calendar and the Reading shelf.
- Night-mode cover shadow now matches Bookshelf. In night mode the default drop shadow is painted as gray(0.15) (
#D9D9D9). After night-mode inversion it shows as a dark grey instead of the bright halo the day value produced. The day shadow is unchanged, and a colour picked under Settings > Appearance > Colors > “Cover shadow color” always takes priority.
- Book info: books without a cover now show the Reading shelf’s stand-in card (a centred book icon, no title) instead of an empty frame with a diagonal line.

### Added

- New setting: “Dark border in night mode” (Settings > Appearance > Covers, under “Cover border”). In night mode the cover frame is painted 
  - #FAFAFA (shown as ~98% black, as in Bookshelf) instead of black (shown as white).
  - It is on by default, has no effect in day mode, and is only available while “Cover border” is on.
  - It applies to Book info, the Reading calendar and the Reading shelf.
- Book info popup is draggable. A swipe moves it (kept on screen) and a slower pan moves it freely. Taps still close it, and a tap on the stars or the description behaves as before. A swipe that starts outside the popup still closes it. Long-press on the stars and on a missing cover keeps its function, so hold-and-drag is not used.

# v8.7.6 · 2026-10-23

### Fixed

- ISO date format for month now '01' instead of '1'

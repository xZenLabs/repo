# v9.1.0 · 2026-11-25

### New
- Long-press a row in the "Mark book finished" list to change the date the book was finished.
- The date can be moved to another year if the statistics DB has reading data in that year. The book is then ticked as finished there and unticked in the original year.
- "Restore last read date" button: goes back to the book's last reading entry in the statistics DB. If that entry is in another year, the book moves back to it.
- Rows with a hand-set date carry the usual "*" marker.

# v9.0.0 · 2026-11-18

### New
- **Cards look**: a new card-based appearance for the popups, switchable under Settings ▸ Appearance ▸ Look (Classic stays the default). It covers Reading insights, Book progress, Reading habits, the Reading calendar, the Book progress calendar, Achievements and the 8-week trend. Huge, huge thanks to: @NijatTagizada who created this layout #88 
- Section order: arrange the sections of the Reading insights and Book progress popups, and switch individual sections on or off.
- Optional reading speed row (pages/min | words/min) in Book progress. #108 

### Fixed

-  Chapter count divider show only if the Dividers set to Normal

# v8.7.11 · 2026-11-07

### Fixed 

- The white vertical line cutting through the day numbers in the Book progress calendar is gone, because the day number is now drawn on top of the “+%” and progress bar layer

# v8.7.10 · 2026-11-04

### Fixed

- The Achievements info dialog appearing behind the list when SimpleUI is installed #87 (Thanks: @NijatTagizada )

# v8.7.9 · 2026-10-28

### Changed
- All-time "pages read" is now counted per book/page/day, the same way as Last 7 days, the monthly and yearly totals and the streak periods. A page read on several days counts once per day, so the all-time total always matches the sum of the per-day totals.
- After updating, run "Reload data" once to refresh the cached all-time figure.

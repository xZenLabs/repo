# v9.3.0 · 2026-11-27

### New
- Radar chart style for the Week view (Cards look only, see #112 Thanks again: @NijatTagizada): one spoke per day, clockwise from the oldest day. Zero reading sits at the centre, the week's highest value on the outer ring, today's point is hatched, and upcoming days have no point.
- Radar week card layout: chart on the left, values with deltas stacked on the right. Bars and Line with dots keep the old layout. Tapping a day label opens that day's books, and a long press on today's label opens today's timeline.
- "Day labels" setting (Week > Day labels: Dates / Day names), shared by bars, line with dots and radar in both week views. Dates is the default; Day names shows Mon … Yesterday, Today.
- pt_BR added (#113 Thanks: @danieldcastro)

# v9.2.0 · 2026-11-25

### New

- Achievement cards in the Cards look now show each achievement's description under its name. #111 Thanks: @NijatTagizada 
- Locked achievements with a numeric goal show their progress (e.g. 19 / 24 or 01:53 / 05:00) plus a full-width progress bar.
- New Fonts → Achievements group with separate fonts for the title, description/date/progress, big value and label. The Classic look shows only the title font.

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

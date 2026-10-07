# v2.0.2 · 2026-10-07

## Fixes
- **Missing covers:** books now get their cover even when the file name doesn't match the title (e.g. `Author - Title.epub`, ISBN-style names), when the book is no longer in History, or when the Cover Browser plugin is turned off.
- Covers that aren't cached yet load in the background and appear after a few seconds, instead of freezing the screen.
- Titles on cover-less books now wrap inside their box instead of spilling over neighbouring days.

## Improvements
- Much larger touch areas for the month arrows and the close button (monthly and yearly views).
- Page-turn buttons change month; Back closes the calendar.
- New **Missing covers report** in the Cover Calendar menu: lists any book without a cover and why.

## Updating
You need to manually replace the cover calendar plugin as the updater in the plugin is broken

# v2.0.1 · 2026-07-24

## Covers should now extract automatically

Covers are now extracted on demand when they're missing. The plugin previously only read covers from KOReader's existing cache. **Your first open after updating may be slow** while it works through your books, but the results are saved and every open after that is instant.

## Also fixed

* "Check for updates" failed with a redirect error and could never find new versions

# v2.0 · 2026-07-23

## Yearly overview

A new **Year** button opens a yearly overview: twelve month rows of the covers of every book you finished. Switch between all 12 months or 6 months with a button in the yearly overview. The 6-month view shows bigger covers, and you use the arrows in the top left to scroll through months, or years. Tap any book in the month row to jump straight into the monthly overview.

## Finished / Read modes

A toggle in the yearly overview switches the rows between books you finished that month and everything you read that month. Read mode lists a book in every month it was actually read, so a long book spanning three months shows up in all three. Set the minimum time a book must be read within a month to qualify in Settings — 5 minutes, 30 minutes or 1 hour.

## Configurable stats

Both the monthly header and the yearly overview show three stat slots you choose yourself: books finished, books read, pages, pages/day, time read (in hours+minutes or days+hours), average minutes/day, days active, current streak or longest streak.

## Also in this update

* New **Today** button jumps back to the current month, shown only when you've navigated away
* Settings reorganised into **Monthly calendar** and **Yearly overview** groups
* Fixed: some cover rendering issues

# v1.0.0 · 2026-07-02

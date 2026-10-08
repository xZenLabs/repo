# v7.2.1 · 2026-10-08

### Fixed
- **Book progress calendar:** the daily "+%" now shows how far that day moved you in the book (position change since the previous reading day), so it matches the Book progress popup and the daily values add up to it. Today uses the live reading position.

# v7.2.0 · 2026-10-08

### New
- 12-month option for the reading heatmap range.
- "Days of the week" bar chart (reading time per weekday).
- "You read most around HH:MM" peak-hour line.
- Tap the "When you read" / "Days of the week" charts to switch between time and percent.

### Changed
- Heatmap sections renamed: "Reading calendar" and "When you read" (translated in all languages).
- Legend aligned to the right; thin separators between sections.

# v7.1.4 · 2026-10-07

### Fixes

- Clearing a book's rating in the Book info popup now works everywhere: the stars no longer reappear in the popup or in the book lists, and match the file manager.

# v7.1.3 · 2026-10-07

### Changes

**Manual books**
- The series and its number are now entered in a single field, written as `Dune #2` (or `Dune #2.5`). Existing entries are shown in the same format when edited and need no migration.
- The date field now comes before the series field, so it stays visible when the on-screen keyboard is open.

# v7.1.2 · 2026-10-07

### Changed

**Wording**
- Clearer English labels in the Insights popup: "daily avg time", "daily avg pages", "Reading time per month", "All time", "Books per month".
- Book lists no longer say "books read" where they actually show books you read from, not only finished ones ("No books", "All books: %1", "%1: %2 books").
- Matching label fixes and shorter forms in German, French, Portuguese, Ukrainian, Chinese and Hungarian. The German list title no longer repeats the count.
- Removed unused all-caps strings from the language files.

**Manual books**
- Tapping a book opens its Book info popup, long-press opens Edit/Delete.
- The book editor no longer opens the keyboard automatically; it appears when you tap a field.

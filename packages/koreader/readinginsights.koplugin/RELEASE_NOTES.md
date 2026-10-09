# v7.3.0 · 2026-10-09

### Changed

**Reading streak popup**

- Added a **Last read** line (left-aligned) right under the calendar, followed by the divider line. It shows the most recent reading day, also when the current streak has lapsed.
- Removed the date-range row under the "Current streak" / "Best streak" headers, because it only described the daily streak and was misleading when only the weekly streak was alive.
- Tapping the **days | weeks** cells of the current or best streak now shows both the daily and the weekly length with their date ranges. A weekly range ends on the last day of its final week.
- Tapping the streak title still opens the streak history popup.
- New "Last read: %1" string translated in all bundled locales; README updated.

**Achievements**

- Achievements now show the **date they were actually earned**, instead of the date the achievement check last ran.
- Earn dates are computed by replaying the reading history in a single chronological pass, so newly earned achievements get their real date.
- Dates saved by older versions are corrected once, on the next full reload (long press on the title bar). Dates are only ever moved earlier, never later.
- The long-press reload now keeps the "Reloading data..." message visible for the whole reload and ends with a "Data reloaded" message. If new achievements were earned, the message shows how many.

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

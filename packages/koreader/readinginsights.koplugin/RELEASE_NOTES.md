# v7.0.0 · 2026-10-06

### Changed

- Added star ratings (0–5) for books, read from each book's own sidecar file.
- Book lists can now show a choice of right-hand column: date, reading time, pages read or rating. The choice is remembered per list.
- New sort orders: rating (highest/lowest first). Unrated books always go last.
- Long-press a book in the rating column to set its rating with a five-star popup (tap or slide).
- Manually added books can now be rated too, via a new Rating button in the add/edit dialog.
- Book list cache keys updated so the new data shows up right away.

# v6.17.0 · 2026-10-06

### Changed
- Faster book lists
  Book lists opened from the insights popup (month, year, all books, finished books) are now cached, so repeat opens no longer re-run the full-history query.

# v6.16.0 · 2026-10-05

### Changed
- Achievements and Reading Goal are now two separate sections and can be turned off individually.
  - Achievements have a new cell for the latest achievement earned.
  - Reading Goal now has a second cell showing the completion percentage.

# v6.15.0 · 2026-10-04

### New

Tapping a day on the reading streak calendar now opens a list of the books read that day, titled with the date, book count and total time, with the time spent on each book. Tapping a book opens its statistics, and days with no reading show a notice instead.

# v6.14.9 · 2026-10-04

On Book progress: "Started" tap now always shows the full date with weekday, matching the "Expected finish" format.

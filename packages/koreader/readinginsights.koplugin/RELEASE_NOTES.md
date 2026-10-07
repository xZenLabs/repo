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

# v7.1.1 · 2026-10-07

### Changed
Improved wording across the Insights popup: shorter and clearer labels such as "daily avg time", "daily avg pages", "Reading time per month", "All time" and "Books per month". The book lists now say "No books" and "All books: %1" instead of the misleading "books read", and wording and word order were also fixed.

# v7.1.0 · 2026-10-07

### Changed

**Book lists**

- Tap on a book now opens its Book info popup; long-press opens its statistics page (previously the other way round).
- Removed long-press rating editing from the period book lists. Rating is now edited from Book info.
- Hand-added finished books open Book info too (title, author, rating; the rating is saved in the manual list).
- Removed the * marker next to the date of hand-added books in the finished-books list.

**Book info popup**

- Star rating shown above the title; long-press the stars to set, change or clear it.
- Ratings are written to the book's own sidecar (summary.rating), so books unrated in the file manager get stars there too. If the book's file can't be located, the rating falls back to the plugin's own file.
- Next to rating the finished date shown.
- New pages/time line pinned to the bottom of the popup, e.g. 860 pages · 12:56 reading time. It is level with the bottom of the cover and shadow, or one large padding below the text when the cover is off. The description gets correspondingly fewer lines.
- Without a cover (switched off in settings) the popup shrinks to the width of its longest line, including the stars and the stats line.
- A book without a cover image shows an empty frame with a diagonal line through it.
- Works for any book in a list, not only the open one: metadata, cover and description are read from the book's file. Author and series fall back to the statistics database.
- Long-press on the popup while the cover is missing shows a diagnostic message with the md5, the file found and the cover error.

**Manual book dialog**

- Added optional "Series" and "Book number in series" fields under Author (accepts 2 / 2.5 / 2,5), shown as a "Series / #N" line under the title in the manual list, with translations for all locales.

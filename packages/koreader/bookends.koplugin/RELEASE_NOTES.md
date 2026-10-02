# v5.29.1 · 2026-09-29

Submitting a preset to the gallery now always asks who to credit and for its description, pre-filled so you can check them. Before, a preset installed from the gallery and then changed could go out under the original author's name without asking.

# v5.29.0 · 2026-09-28

**New**

- The preset gallery has two new sorts, *This week* and *This month*, showing which presets people have been installing lately. *Popular* still ranks by installs of all time.

# v5.28.0 · 2026-09-27

**New**

- Full-width progress bars can now be placed relative to the lines of text at the top or bottom, instead of at a fixed distance from the edge of the screen. Turn on *Position relative to line text* in a bar's settings and it keeps its place beside the text, even on a screen where the text comes out bigger or smaller. The new *Inverted header* preset in the gallery uses it to look the same on any device.

# v5.27.0 · 2026-09-27

**New**

- The background fill can now be set separately for the top and bottom of the screen. In the preset menu, *Top background* and *Bottom background* replace the single background colour, so you can fill just one of them or give each its own colour. Presets that used one background colour keep it on both.
- Slovak translation, thanks to @misko903.

# v5.26.0 · 2026-09-24

**New**

- `%genre` and `%genres` show a book's genres, taken from its keywords (the field in KOReader's Book information). `%genres` lists them all, separated by commas, and `%genre` shows the first. `[if:genres]` hides a line for books that have none.
- `[if:chap_page=odd]` lets a line alternate on the page within the chapter, so the pattern starts again at every chapter. `[if:page=odd]` still follows the book's own page.
- `%session_pages_advanced` shows how far you've got this session, counted in stable page numbers when the book has them. It starts at 0 and only goes up when you pass the furthest page you've reached, so paging back doesn't count. `%session_pages` is unchanged.

**Fixes**

- The book page no longer draws over part of KOReader's menu when a status bar updates while the menu is open, for example when toggling Wi-Fi from the menu.
- Fixed an error box when opening a book on Kindles with a warm light, if the warmth couldn't be read at startup.
- Calibre columns (`%calibre{...}`) now survive KOReader's wireless Calibre sync, which was wiping them.
- Calibre columns now also work in large libraries, where they could go missing, and when KOReader's home folder is set with a trailing slash.
- Whole-number Calibre columns, such as a word count, now print in full rather than as `1.23457e+06`.

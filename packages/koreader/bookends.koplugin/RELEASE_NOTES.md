# v5.27.0

**New**

- The background fill can now be set separately for the top and bottom of the screen. In the preset menu, *Top background* and *Bottom background* replace the single background colour, so you can fill just one of them or give each its own colour. Presets that used one background colour keep it on both.
- Slovak translation, thanks to @misko903.

# v5.26.0

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

# v5.25.0

**Fixes**

- Fixed a crash when turning the top or bottom status bar on while another plugin is hosting the Bookends menu. The settings dialog now opens over the menu instead of replacing it in that case.
- `%sysused` now reports correctly on older Kindles such as the Paperwhite 3, where it was counting reclaimable disk cache as used memory and sitting close to full. Thanks to @ksaMask123 for tracking this down and fixing it.

**Changes**

- `%sysused` renders as `84M` rather than `84 MiB`, matching `%ram` and the Bookshelf plugin. Lines using it will be a little shorter.

# v5.24.0

**Calibre columns in your status bar**

If your library is managed by Calibre, `%calibre{name}` now shows any column from it, using the column's lookup name: a custom column `#mood` renders with `%calibre{mood}`. Text, list, number, date, yes/no and multi-value columns all work. Three standard fields come through the same way: `%calibre{pubdate}`, `%calibre{publisher}` and `%calibre{rating}`. Conditionals work too, so `[if:calibre{mood}="cosy"]` does what you would expect.

Nothing is read unless one of your lines actually uses the token.

**Fourteen new tokens**

Book details that were only available on the Bookshelf home screen now work in the reader as well: `%status` and `%status_label`, `%rating` and `%rating_number`, `%description`, `%size`, `%added`, `%opened`, `%favourite`, `%author_count`, `%authors_short`, `%quote` and `%quote_source`, plus `%sysused` for memory.

**`%spacer`**

A new elastic gap that pushes everything after it to the far edge of the line, so `%author%spacer%book_pct` puts the author hard left and the percentage hard right without any fiddling with widths.

**Fixes**

- A long chapter title in a centred or right-hand region could run off the left edge of the screen with its first words missing. This happened when that region had no neighbour in the same row, so nothing forced it to truncate. It now truncates against your Bookends margins (#108)
- Updates could fail on a slow connection. The download was capped at 60 seconds regardless of how it was progressing, so a download that was merely slow failed the same way a dead one does
- When an update does fail, the message now says why (timed out, no response, or the actual error), instead of just "Download failed." A partly downloaded file can also no longer be left behind to confuse the next attempt
- `%wifi_icon` now works as another name for `%wifi`, so a line copied from Bookshelf no longer shows the token's own name

**If you use Bookshelf too**

Bookshelf can now show its status line across the top of the reader. When it does, your top row and any top-anchored progress bar shift down to make room. The switch is in Bookshelf; there is nothing to set up here.

# v5.23.1

**Fixes the in-app updater**

Installing an update crashed KOReader before it could finish. Bookends unpacked the downloaded file using a KOReader helper that was removed from KOReader itself in mid-2026, so on current versions that call failed and took the reader down with it. It now unpacks using the same library KOReader uses internally.

The download was never the problem, so nothing was left half-installed — the previous version stayed in place and came back on restart.

**If you're on v5.23.0 or earlier you'll need to install this one by hand.** The updater is the thing that was broken, so it can't update itself. Download the zip below, unzip it, and copy the `bookends.koplugin` folder over the existing one in your KOReader `plugins` directory. Updates after this one work normally again.

Everything in [v5.23.0](https://github.com/AndyHazz/bookends.koplugin/releases/tag/v5.23.0) is included — auto preset by file type, the progress-marker fix, the new tokens, and Ukrainian and European Portuguese translations.

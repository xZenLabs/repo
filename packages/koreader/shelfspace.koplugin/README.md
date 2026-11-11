<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <img src="assets/logo-light.svg" width="140" alt="ShelfSpace: books on a shelf with one empty slot">
  </picture>
</p>

<h1 align="center">ShelfSpace</h1>

<p align="center">
  See where your e-reader's storage went, and free it up.<br>
  A plugin for <a href="https://github.com/koreader/koreader">KOReader</a>.
</p>

<p align="center">
  <a href="https://github.com/ghepting/shelfspace.koplugin/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/ghepting/shelfspace.koplugin"></a>
  <a href="LICENSE"><img alt="MIT license" src="https://img.shields.io/github/license/ghepting/shelfspace.koplugin"></a>
</p>

<p align="center">
  <img src="assets/library.png" width="260" alt="The Library tab: a chart of where the storage went, and the files, largest first">
  <img src="assets/select.png" width="260" alt="Selecting files, with a Delete bar floating over the list">
  <img src="assets/duplicates-compare.png" width="260" alt="Comparing the copies of a book to choose which to keep">
</p>

ShelfSpace answers "where did my space go?" and lets you do something about it, from inside KOReader:

- **See it.** A chart of books, KOReader's own data, other files and free space, with your library under it, largest first.
- **Find the big things.** Search, filter by file type or by what you have (or have not) read, and sort by size, name, date or last opened.
- **Clear it safely.** Select what you want gone and delete it in one go. Every delete asks first, and only books and pictures KOReader can open can be deleted.
- **Clean KOReader up.** Its rendering cache, update downloads, crash logs, old screenshots and the reading progress of books that are gone.
- **Find duplicates.** The same book in two formats or twice over, shown side by side so you choose which copy stays.

It uses only KOReader's own APIs, so it is meant to work on every device KOReader runs on. It is built for colour e-ink as well as black and white: colour is only ever there to help you find your way, never the only cue.

## Install

1. Download `shelfspace.koplugin.zip` from the [latest release](https://github.com/ghepting/shelfspace.koplugin/releases/latest).
2. Unzip it into KOReader's `plugins` folder and restart KOReader.
3. Open **Tools › ShelfSpace**.

To update later, you can do it from inside ShelfSpace when you choose to: see [About and updates](#about-and-updates). It never checks or installs anything on its own.

## Using it

Three tabs: **Library**, **KOReader**, and **Duplicates**, which only appears when you have some. Held upright, each tab has its chart or summary over its list; held sideways (on a tablet, or a reader you rotate), the summary moves into a column on the left and the list gets the full height beside it.

### Library

At the top, the chart and its legend: books, KOReader's data, other files and free space. They only show where the space went. The info icon after **Other** explains what that space is and why it is left alone.

Under it, your files, largest first. Each row has a tile for its type, a colour for its kind, how far through a book you are, its size, and a checkbox.

- **Open things.** Tap a folder to go in; the first row in a folder is `../`, to go back up. Tap a file, or press and hold any row, for its card: type, size, where it is, when it changed, when you last opened it and your progress, with **Open** and **Book info**. For the book you have open there is **Close book**, so you can delete it.
- **Search** (the magnifier) looks by name through the folder you are in and everything under it. Once you have searched, the button shows your search and tapping it clears it.
- **Filter** by file type, or by **Show**: books you have finished, or never opened, wherever they are. What is narrowing the list appears as chips with a ✕, each undoing just that. When nothing matches, you are told why and given a button that undoes it.
- **Sort** by size, name, date or last opened; the arrow beside it flips the direction.

#### Deleting

Every row has a checkbox on the right. Select the ones you want, or use the **Select all** line above them, which selects the deletable rows on the page you are looking at (so a delete is never of rows you have not seen). That line always shows the total you have selected, across every page of the list you are looking at, with its size: "Select all · 15 selected · 668.0 MB". A bar floats over the bottom of the list, just above the page controls (which stay whole, so you can always see which page you are on), with **Cancel** and **Delete**; nothing moves under your finger when it appears. Paging and sorting keep your selection; opening another folder, searching or changing a filter clears it, so a Delete only ever acts on rows you can see.

You always get a confirmation first, naming what goes and how many books lose their reading progress. Rows that cannot be deleted are greyed out with a padlock instead of a checkbox, and tapping it tells you why. If a file or folder is locked only because ShelfSpace does not recognise it, its card (press and hold the row) says so and points to KOReader's file manager, which can delete it after asking once its **Show unsupported files** setting is on. With that on, the card has **Show in file manager**, which takes you to the file there. ShelfSpace never changes that setting for you.

### KOReader

What KOReader can rebuild or no longer needs: the rendering cache, update downloads, crash logs, screenshots, and the reading progress of books that are gone. It works like the Library: select rows, use **Select all**, and the same bar offers **Clear**. The list pages like the Library's, so it fits any screen size. With nothing selected, a bar at the bottom offers **Clear all** for everything listed. When there is nothing to clear the tab says **ALL CLEAR**, and there is nothing to select. Either way you are asked first, with a warning that screenshots and reading progress cannot be recovered.

### Duplicates

Shown with a count when a book is in the library more than once. It opens on how much clearing the extras would free, then lists each book as a card with its copies: the one that stays is marked ✓, the others ✕.

- **Same file** means identical bytes. **Same book** means the same name in another format, or with a "(1)" on the end. Spellings and capitals do not matter, so `Dune.epub`, `dune.KEPUB.EPUB` and `DUNE.fb2.zip` are one book.
- A file with nothing in it (0 bytes) is never offered as the copy to keep. Next to real copies it is tagged **Empty** in the delete colour, and a set of only empty files is not listed at all, since there is nothing to choose between.
- Open a set to compare its copies. Back is beside the book's name (in a sideways layout, at the top of the copies). Each copy is one row: a tile for its file type, its name, how far through you are ("Unread", "40% read" or "Finished"), then where it is and when it was added, then its size and a radio button. Tags at the right of a row say what sets a copy apart: **Suggested** (purple), and in blue most read, newest, smallest, an older format, or fixed layout.
- A line over the rows says which copy stays ("Keeps Foundation.epub", the name in green). The copy to keep has a green tint and a filled green radio; every other copy has the magenta-red tint of a delete and an empty radio, so on a screen with no colour they still differ by the filled radio. A set with more copies than a page holds pages, and the same line says which are showing ("Copies 1–7 of 9"). The book you are reading, or the copy you have read most, never goes. After that: the format that reads best on e-ink (EPUB, then MOBI, then reflowable formats, then fixed layouts such as PDF), then the copy nearest the top of your library, then the newest. Tap another copy to keep that one instead.
- What deleting will do is on the bar that floats over the bottom of the page, above the page controls, as everywhere else: how much it frees, **Keep all** (which leaves the set alone from then on; those are under **Kept on purpose** in the menu) and **Delete** the extra copies. The confirmation names what it keeps and what it deletes. A copy answers a tap anywhere on its row.
- When the last set is dealt with the tab says **You're all caught up**, in green, and offers **Kept on purpose** if you chose to keep some sets as they are.

It is one book at a time on purpose, so every deletion is something you have looked at.

## Safety

Deleting is permanent: there is no trash. So ShelfSpace is conservative.

- Only books and pictures KOReader can open (and the covers and metadata that go with them), and folders holding nothing else, can be deleted. Anything it does not recognise is locked, with the reason shown.
- System folders, KOReader's own folder and the book you are reading are always locked.
- Every delete asks first and names what goes.
- If the library matters to you, keep a copy elsewhere.

## File types

ShelfSpace knows every format KOReader opens, in any case (`.epub`, `.EPUB` and `.ePub` are the same), and gives each a tile with its own letters and a colour for its kind. The type filter and the duplicate finder count a format's other spellings as one.

| Kind | Colour | Formats |
| --- | --- | --- |
| Books | indigo | epub (also `.kepub.epub`, `.epub3`), mobi (`.prc`), fb2 (`.fb2.zip`), fb3, pdb, azw |
| Documents | cyan | doc, docx, docm, odt, rtf, txt, md, html (`.htm`), xhtml, htmlz, chm, and `.txt.zip`, `.md.zip`, `.html.zip` and the like |
| Fixed layout | orange | pdf, djvu (`.djv`), xps |
| Comics and archives | purple | cbz, cbt, cbr, zip |
| Pictures | olive | jpg (`.jpeg`), png, bmp, webp, gif, tif, svg and the other image types KOReader shows |
| Folders | gray | |

A format KOReader does not register on your build (for example `.azw3`, `.kfx`, `.text`, `.markdown` or `.oxps` in KOReader's 2026.07 nightlies) is listed as a locked file until you set an "open with" for it in KOReader.

## About and updates

The ShelfSpace mark at the top left of the screen opens a menu (the ✕ at the top right closes ShelfSpace). It holds **About**, **Check for updates**, **Changelog**, **Kept on purpose** (when you have set some aside) and **Exit ShelfSpace**.

- **About** shows which ShelfSpace this is (version, release date and commit), what it is running on, and QR codes for the repository and for reporting a problem, with your device and versions already filled in.
- **Check for updates** asks GitHub for the latest release, only when you tap it. If there is a newer one it tells you what changed, and **Update now** downloads it, checks it against the release's size and checksum, installs it over the plugin and offers to restart KOReader.
- **Changelog** shows the notes of every release, newest first. It is fetched from GitHub the first time you open it and kept on the device, so after that it reads offline; **Refresh** pulls newer releases.

You can do all of that without opening ShelfSpace: in KOReader's Tools menu, ShelfSpace is a submenu with **Open ShelfSpace** (or **Close**), **About**, **Check for updates** and **Changelog**. Bookshelf's start menu can launch it too: Add to menu, Plugin, ShelfSpace.

## On a Bookshelf shelf

If you use the [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) plugin, ShelfSpace adds two modules (Bookshelf's word for a thing that stands among the books on a shelf). They only show how full the device is; they never scan or delete anything. Tapping one opens ShelfSpace. Without Bookshelf they do nothing, and ShelfSpace works as before.

- **ShelfSpace storage** is a card with the storage bar drawn as a shelf of spines. It sizes itself to the space it is given.
- **ShelfSpace ornament** is a small ornament that stands on the shelf with the free space on a tag above it. It is a conical flask, a glass of water, a whiskey glass, a decanter, a stack of books, a pillar candle, or an inkwell and quill. Every one but the stack is full when the device has plenty of room and empties as it fills; the candle burns down. The stack goes the other way: it grows as the device fills.

To add one, long-press a shelf's tab in Bookshelf, then Modules, **Add module…**, and the **ShelfSpace** tab. For the ornament you then pick which one, from a grid of small pictures. Long-press it on the shelf and choose **Settings** to **Swap…** it later, or to **Hide label** (the tag with the number) or **Show label** for that one ornament. **Width** in the same menu sets how many book widths it takes; it starts at one.

## Tested on

| Device | KOReader | Status |
| --- | --- | --- |
| Kobo Libra Colour | v2026.07.1 and v2026.07.2 | Works (the colour screen), including installing an update from the About card |
| KOReader desktop emulator (macOS) | nightly 2026.07.2 | Works |
| Kindle Paperwhite 6 (12th gen) | v2026.07.2 | Works, [reported by a user](https://github.com/ghepting/shelfspace.koplugin/issues/56) |
| Android | not stated | Works, [reported on Reddit](https://www.reddit.com/r/koreader/comments/1xfe6r4/i_made_my_first_koreader_plugin/) by a user |
| Kobo Clara Colour | not stated | Works, [reported on Reddit](https://www.reddit.com/r/koreader/comments/1xfe6r4/comment/19rt1oz4v5tgh/) by a user |

Anything else is untested. If you try it on another device, please [tell us how it went](https://github.com/ghepting/shelfspace.koplugin/issues/new?template=device_report.yml). The colours were designed for how a colour e-ink screen washes them out, from the emulator and a wash that approximates it, so reports of how they look on your device are especially welcome.

## Screenshots

<details>
<summary>All screens</summary>

| Library | Books, biggest first | Filters |
| --- | --- | --- |
| <img src="assets/library.png" width="260"> | <img src="assets/books.png" width="260"> | <img src="assets/filter.png" width="260"> |

| Search | Select several | File details |
| --- | --- | --- |
| <img src="assets/search.png" width="260"> | <img src="assets/select.png" width="260"> | <img src="assets/details.png" width="260"> |

| Delete | KOReader data | Clear several |
| --- | --- | --- |
| <img src="assets/delete.png" width="260"> | <img src="assets/koreader.png" width="260"> | <img src="assets/clear-several.png" width="260"> |

| File types | ShelfSpace menu | Locked rows |
| --- | --- | --- |
| <img src="assets/formats.png" width="260"> | <img src="assets/menu.png" width="260"> | <img src="assets/locked-rows.png" width="260"> |

| Why it is locked | | |
| --- | --- | --- |
| <img src="assets/locked-card.png" width="260"> | | |

| Sets of copies | Compare and choose | Confirm |
| --- | --- | --- |
| <img src="assets/duplicates-list.png" width="260"> | <img src="assets/duplicates-compare.png" width="260"> | <img src="assets/duplicates-confirm.png" width="260"> |

| Kept on purpose | Changelog | About |
| --- | --- | --- |
| <img src="assets/duplicates-kept.png" width="260"> | <img src="assets/changelog.png" width="260"> | <img src="assets/about.png" width="260"> |

</details>

Taken in the KOReader desktop emulator at Kobo Libra Colour proportions, on a made-up library and an 8 GB device, so the totals are not a real one's. The colour screenshots are softened with `tools/kaleido-wash.sh` to look the way a colour e-ink screen (Kaleido) shows them, which is paler than a monitor. On a screen with no colour, ShelfSpace is black, white and grays.

## How it works

The last scan is kept in KOReader's cache folder (`cache/shelfspace/scan.lua`). The next one only reads folders whose modification time changed. KOReader's own data folder is always read afresh, since its files change in place. Delete the file to force a full scan.

## Development

You need a KOReader to run it in: the [desktop emulator](https://github.com/koreader/koreader) (`./kodev run`), or any KOReader install. Link the plugin into its `plugins` folder:

    ./dev.sh /path/to/koreader/plugins

The logic runs under plain `luajit`, without KOReader. It covers what may be deleted and why, every file type in any case, how a selection collapses, search, sort and the filters, the duplicate finder and what it keeps, reading progress, the themes, the chart's geometry, the icons, KOReader's data tab, the release check and installer, the changelog, and the gestures ShelfSpace shares with KOReader:

    tests/run.sh

Screenshots are taken by `tools/screenshots/run.sh /path/to/KOReader.app`. It builds a sample library and a made-up 8 GB device, drives ShelfSpace through every screen in the desktop emulator, checks it as it goes (what may be deleted, every file type, duplicates, the filters), and washes the colour screenshots with `tools/kaleido-wash.sh`. Add `--readme` to put the washed ones in `assets/`. Every screenshot in this repository goes through that wash; run `tools/kaleido-wash.sh shot.png` on any other colour capture, once.

`tools/screenshots/sizes.sh /path/to/KOReader.app` opens ShelfSpace at the screen sizes of common e-readers (from 600 × 800 up to 1440 × 1920, 167 to 300 dpi, upright and sideways) and checks that every tab fits, with a screenshot of each.

`tools/make-wordmark.py` draws the name under the logo as outlines from a font file; the result is already in `shelfspace.koplugin/shelfspace/icons.lua`.

### Contributing

Pull requests are squash-merged, so the title must be a conventional commit: `feat:`, `fix:`, `docs:`, `chore:`, `test:`, `refactor:` (`feat!:` for a breaking change). Releases are automatic: release-please keeps a "release" pull request open from those titles (a `fix` bumps the patch version, a `feat` the minor one) and merging it tags the release and attaches `shelfspace.koplugin.zip`.

## License

[MIT](LICENSE)

# v5.2.1

- New option under the wallpaper image pickers: Invert wallpaper in night mode (off by default), so a light wallpaper turns dark when the shelf is in night mode.
- Fix: Colours you pick for the progress bar, shelf menu background, badges, bookmarks, the selected shelf button and text now show in colour on colour screens instead of grey.
- Fix: A colour picked in night mode, or with the shelf theme pinned to light or dark, now shows as the colour you picked rather than its opposite.
- Fix: Titles on generated covers no longer get cut short when they would fit at a slightly smaller size (#457).
- Fix: "First unread in series" on spine shelves no longer faces out a second book when a series runs across a page break (#458).

# v5.2.0

- "Extract page counts" lays books out at your own reading settings, so its counts match what you see when reading, and shows them as each book's page count. It opens with a dialog to pick the sources to try, in order: publisher page numbers, Hardcover editions, your reading settings, a Calibre page column such as #pages (#405), and page counts in file names. You can fill in only missing counts or recount every book, or delete scanned counts. Progress shows in the status line while the shelf stays usable, and the Pages sort uses the counts.
- Ornament packs: a folder of ornaments inside bookshelf.ornaments is a pack. A new ornaments browser under Background and colours shows every ornament, with a tab per pack, so you can switch single ornaments or whole packs on and off, or delete them.
- If you didn't have bookends installed, the bookshelf font picker was a basic fallback - bookshelf now has its own font picker for anyone who doesn't also have bookends installed.
- Battery micro-module, with the level, KOReader's battery icon and the cover battery where there is one. Tap it for battery statistics (#342).
- Quote of the day module can read quote files in settings/bookshelf/quotes (#258), and you can leave out a book or a highlight colour (#368).
- "My review" in a book's reviews tab shows and edits the personal review KOReader keeps for the book (#238, #315).
- A "Series or title" sort puts series and standalone books in one alphabetical order (#437).
- New setting in the library & search menu: leave genres and tags out of search (#371)
- New setting in the behaviour menu if you want to keep the floor to ceiling shelf view without collapsing it when you swipe down - imaginatively called 'stay in full screen shelves when swiping down' - you can still press the currently reading button to pop the top panel back open (#366)
- New option to choose a custom wallpaper folder, to use alongside bookshelf's standard folder (#419).
- The book description in the book popup uses your Bookshelf UI font, or KOReader's own UI font when following it (#284, #233).
- In the shelf editor, "Source" is now "Source / grouping", and its list is split into book shelves and grouped shelves (series, authors, genres and so on).
- Spacing, drop shadows and rounded corners no longer grow with a DPI override, so large DPI layouts keep more room for covers and text.
- Scrollbars are drawn as a slim rail along the edge, and the book popup's tabs stay on one row on larger DPI settings.
- Faster page turns and shelf switches, most of all with a wallpaper. Spine shelves and two-column lists redraw less of the screen.
- The Recent shelf shows books you've read from outside your home folder (#305).
- Covers no longer disappear from the shelf and the top panel after a page turn when a library's metadata was scanned before its covers (#451).
- With true cover aspect ratio on, a folder or group with its own image takes that image's shape (#402).
- Unpacked EPUB folders are detected as such and no longer show up as dozens of small books.
- Spine widths match the page count shown for a book: one with publisher page numbers no longer keeps a wider spine from an earlier page count scan.
- Fix: On a spine shelf, choosing a second genre or tag from the top panel shows its own books instead of the first one's.
- Fix: Switching shelves in full screen with the status line off no longer leaves the old shelf button's fill behind.
- Fix: Tapping a shelf button over a wallpaper no longer flashes it black and white.

# v5.1.5

- Collection shelves can sort by "Collection order", the order you've arranged the collection in KOReader, and an "Edit collection order" button beside it opens KOReader's arrange screen (#441).
- Spine titles too long for a thick spine wrap onto a second line (#440).
- "Ignore The, A, An when sorting" in Library & search: turn it off to sort titles and series exactly as written (#428).
- A spine's thickness no longer changes once you've read the book in a large or small font. Run "Extract page counts" once to update books you've already opened (#387).
- New in the accent colours: "Micro-module border" (#424) and "Transparent shelf menu", which lets the wallpaper show behind the shelf buttons.
- Page chevron taps now use the page-turn animation, like swipes (from @imanubdesigner's PR #447).
- On a spine shelf, opening a folder spills its books onto the shelf in labelled runs instead of showing subfolders as thin book spines (#420).
- "First in series" and "First unread in series" follow each book's own series on author shelves, and books there show their series numbers again (#444).
- The gap under a lifted spine book blends into the shelf instead of showing as a black bar (#446).
- Expanding a short shelf, or zooming out on it, no longer leaves the first books unreachable (#369).
- Collapsing an expanded spine shelf keeps your place instead of going back to page 1.
- Switching shelves no longer leaves part of the old top panel on screen (#423).
- The wallpaper follows night mode when it's switched by another plugin that doesn't broadcast the change correctly, and switching no longer flashes the old colours first (#426).
- Bold and italic are kept on wrapped title lines in list view (#379).
- With "Flash buttons and menu items" on, the page buttons no longer flash a patch of the wallpaper when tapped.

# v5.1.4

- Micro-modules keep their outline after being tapped (#429).
- "Menu search" works as a start menu item (#438).
- The reading streak module's "Reading insight" tap opens the reading progress popup. It did nothing at all before.
- Bookshelf paces itself against an OPDS catalogue that limits requests, rather than emptying the shelf and reporting the server as unreachable (#434).
- With the status line turned off, the full shelf no longer leaves a gap where it would have been.
- Recent opens as a list and Genres shows ribbons, for readers who have never changed their shelves.

# v5.1.3

Fixes for 5.1.2.

- Tapping the page counter no longer closes KOReader, with a wallpaper set (#436).
- The shelf follows a rotation you made while reading (#435).
- Spines keep their colour on colour screens (#430).
- The About screen no longer reports a second copy of Bookshelf when only one is installed.
- "Author on spine" can be turned back off (#439).
- A background no longer shows as a negative when night mode is set by a gesture or another plugin.

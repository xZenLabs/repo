# v5.3.0 · 2026-10-02

- Theme packs: a pack can now bring its own wallpaper, planks and colours as well as ornaments. Choose a whole look from the new Shelf theme row in the Bookshelf menu, above Wallpaper, ornaments and colors (which was Background and colors): under Auto, Light and Dark it lists No theme pack and each theme pack you have installed. Choosing one sets its wallpaper, plank, colours, light or dark, and its ornaments, switching other packs' ornaments off. No theme pack puts your own look back, and anything you changed in the meantime stays as you left it. A pack you copy in shows the next time you open the menu, and Add theme… says where its folder goes and where to find ready-made ones.
- Long-press an ornament on the shelf to adjust it: Size, Padding (below zero it tucks behind the books beside it), Anchor (bottom stands it on its shelf, top hangs it from the shelf above, or from the top panel on a page's top shelf), Height from that anchor, Mirror, and a Tap action. Place moves it earlier or later in the order, Swap picks another piece for that spot, and Shuffle all (or a gesture set to "Bookshelf: shuffle ornaments") deals a new order. Changes follow the ornament onto every shelf.
- Zoom, a tap action for ornaments: shows the piece full screen, with a note about it when it has one.
- Ornaments stand in a fixed pattern for each frequency setting and come round in the same order every time, so your shelf stays put when you add books or restart. Wide pieces are no longer left out: they are sized to fit and the books move over to make room.
- Ornaments you add go to the front of the order so you see them, and show up within a few seconds without leaving the shelf. Set Wallpaper, ornaments and colors > New ornaments to Last to keep your shelf as it is.
- A new wallpaper picker, with a large preview of each wallpaper and tabs for yours and each pack's. A tap shows it on the shelf behind straight away.
- A built-in oak plank, used unless you've picked a plank colour of your own, and a Shelf plank picker under Wallpaper, ornaments and colors: Plain color, Oak, or any plank a pack brings, each shown as the shelf draws it. If plank designs are slow on your device, switch them off under Settings > Advanced > Performance tweaks.
- A Color theme row at the top of Accent colors: your own colours, or a pack's.
- Softer shadows around the books on spine shelves, and rounded corners where face-out covers meet the shelf.
- Everything of yours is now in one folder, koreader/settings/bookshelf: settings, page counts, Hardcover links, wallpapers and ornaments, so backing up that folder backs up bookshelf. Your files (ornaments in icons/bookshelf.ornaments too) move there by themselves on the first start. Caches go to koreader/cache/bookshelf.
- Swipe down on the top panel for a bigger panel and one shelf row fewer; swipe up to give the row back (#465).
- Two more Face out reasons for spine shelves: Unread standalone (unread books in no series) and In a collection (the books in a collection you choose, such as a To read list) (#470).
- Extract page counts for one folder: long-press it (or a series, author, genre or collection stack) and choose Extract page counts… (#459).
- Shelf labels can use icons from your koreader/icons folder, as the start menu already could: Insert icon… when naming a shelf now offers the SVG icon folder (#469).
- The quote of the day draws from every book's highlights, not only the 25 books you opened last. Scan library for highlights, in its settings, counts them all at once.
- The reading goal can add books you read outside KOReader to the year's count, under its settings. Coming from SimpleUI, your physical books number comes across.
- Settings > Behavior > Bookshelf gestures: switch off any of bookshelf's own gestures, or all of them. "Swipe down leaves full screen shelves" has moved in there.
- OPDS books show their series in the top panel and on their covers when the catalogue sends it (Grimmory, BookLore and OPDS 2.0 catalogues) (#478).
- Calibre metadata is also found in the folder above your home folder, where Calibre puts it at the root of the device (#475).
- Tap empty space on a spine shelf to put a lifted book back.
- The Ornament collection shows ornaments only, with a tick box on each and Select all and Select none for the tab you're on, and is quicker when switching lots on and off.
- For pack makers: a pack can include an ornaments.json to arrive placed, and a theme folder with a theme.json, wallpaper, planks and colours to make it a theme pack. Details in the README.
- Fix: an edge swipe along the top or bottom, or a corner long-press, that you've given an action in KOReader's gestures now runs that action on the shelf (#476).
- Fix: a new book's spine shows its title and colours once its details are read, instead of its file name (with authors switched off, OPDS downloads showed the author) (#477).
- Fix: on a filtered shelf, a collection (or series, author and so on) you come back to from a book no longer shows books the filter leaves out (#479).
- Fix: on a Series shelf showing standalone books too, sorting by author mixes the standalone books in with the series instead of putting them all at the end (#351).
- Fix: tapping a Book stack folder with HW dithering on no longer leaves a noisy strip beside the stack on colour screens (#448).
- Fix: the daily reading goal's "min" is now translated (#474).
- Fix: the device no longer goes to sleep in the middle of Extract page counts (#459).
- Fix: soft edges of PNG ornaments no longer come out darker than drawn.
- Fix: the reading goal counts a book in the month and year you marked it finished, not when you last opened it, so a book finished in December no longer counts towards the new year.
- Fix: time left, reading time and speed for a book whose title or author changed (a Calibre resend, say) now match KOReader's, instead of coming from the book's old statistics.
- Fix: Disable spine mode shadows now takes effect straight away instead of on the next page.
- Fix: uninstalling bookshelf along with its settings no longer deletes the Hardcover sync plugin's settings too.
- Fix: on a KOReader older than v2025.08, bookshelf shows one menu line saying to update KOReader instead of crashing.
- Fix: Full screen shelves image set to None now says None, instead of Same as default.

# v5.2.3 · 2026-09-28

- Fix: A very large PNG ornament no longer crashes KOReader when you open the ornaments browser. Ornaments over 8 megapixels are now left out, with a note in the log; 1000-2000 px on the longest side is plenty (#471).

# v5.2.2 · 2026-09-27

- Fix: With "Return to file browser" as the end of document action, finishing a book goes straight back to bookshelf again instead of flashing KOReader's file browser first (#460).
- Fix: Sorting by Progress now works on shelves that also have a status filter, instead of falling back to title order (#463).
- Fix: The skip to end button on spine shelves now reaches the last page on the first tap (#463).
- Fix: Extract page counts no longer undercounts FB2 books (#461).
- Fix: Brackets in Chinese titles on spines are now turned to match the vertical text (#462).
- Fix: The clock and battery in the full screen micro-modules view now keep up with the time instead of staying as they were when it opened.
- Slovak translation now says "doplnok" instead of "plugin", matching KOReader (from @misko903's PR #467).

# v5.2.1 · 2026-09-26

- New option under the wallpaper image pickers: Invert wallpaper in night mode (off by default), so a light wallpaper turns dark when the shelf is in night mode.
- Fix: Colours you pick for the progress bar, shelf menu background, badges, bookmarks, the selected shelf button and text now show in colour on colour screens instead of grey.
- Fix: A colour picked in night mode, or with the shelf theme pinned to light or dark, now shows as the colour you picked rather than its opposite.
- Fix: Titles on generated covers no longer get cut short when they would fit at a slightly smaller size (#457).
- Fix: "First unread in series" on spine shelves no longer faces out a second book when a series runs across a page break (#458).

# v5.2.0 · 2026-09-25

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

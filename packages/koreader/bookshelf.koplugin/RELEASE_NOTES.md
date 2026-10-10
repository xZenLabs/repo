# v5.4.0 · 2026-10-10

- Each shelf can now have its own theme (#495). Choose one in the new Theme library: a card for each theme, and the shelf behind changes as you tap. Shelves you leave alone use your Default theme.
- Any theme can be edited. Change its wallpaper, plank, colours or ornaments and the changes stay with that theme; Reset in the Theme library puts it back.
- Your own wallpaper, plank and colours are now a theme of their own, Custom theme, and choosing a pack no longer overwrites them. There is also a new built-in Plain theme: no wallpaper, Oak plank, default colours.
- Every ornament pack can be chosen as a theme.
- Your shelf looks the same after updating: a pack you were using becomes your Default theme, and your own settings become Custom theme.
- One Theme menu replaces Shelf theme and Wallpaper, ornaments and colours. Shelf style (long-press a shelf) also starts with a Theme row.
- Shelf of shelves: a new shelf source that holds other shelves, as many levels deep as you like, each with all the options of any shelf. On Spines it shows the books from all of them (#489).
- Taking a face-out book off a spine shelf now shows it in 3D, pulled off the shelf and turned so you see its pages and boards.
- Ornaments no longer stand in the same places on every page, and each shelf keeps its own ornaments in its own order. Swap and Shuffle this shelf only change the shelf you're on.
- Custom text below covers: Settings > Cover display > Show text below covers > Custom… builds the line from tokens, e.g. %book_pct · %size for how far you've read and the file size.
- Show text below groups: a separate line under series and other stacks, so you can have titles under books and the author under series (#486). Choose None, Author or Custom… in Settings > Cover display.
- Panel shading is now in Theme > Wallpaper and part of the theme, so a pack can bring its own. Two new options sit with it: Blur wallpaper behind panels, and Panel behind Covers shelves for the same solid panel list view has (#483).
- The shelf editor applies each change as you make it, so Close replaces Cancel and Save.
- The Kobo shelf is now a shelf source: add a shelf and choose Kobo library. The Kobo setting under Advanced is gone.
- Other plugins can now add their own shelf sources (#452). See SOURCE_API.md.
- Moved: Extra wallpaper folder is now under Settings. Colours > Colours for: Light | Dark switches the set you're editing without turning on night mode. Transparent is now a choice in Colours > Shelf menu background.
- For pack makers: plank_solid plank ends; in theme.json a "hero" ornament for the pack's card and panel_shading, panel_blur and covers_panel; a per-piece "trim" in pack.json.
- Fix: on a shelf with a filter, opening a series or other stack shows all its matching books, not only the first (#485).
- Fix: in list view, a book marked finished without being opened shows a full progress bar (#487).
- Fix: books from Calibre-Web no longer start their description with its RATING, TAGS and SERIES lines, books already downloaded included (#490).
- Fix: on a new KOReader install with no home folder set, Home shows the device's books instead of none.
- Fix: closing a picker while its search keyboard was open no longer leaves the keyboard behind with KOReader looking frozen.
- Fix: an ornament in the bottom-left corner no longer takes taps meant for the start menu button.
- Fix: Transparent panel shading no longer makes the shelf menu transparent too. If you had that look, it is kept as Shelf menu background: Transparent.
- Fix: with a plank design, hanging ornaments stay on the wall instead of overlapping a plank, and plank ends are no longer cut short after an animated page turn.
- Fix: switching a shelf to another style and back no longer changes the size of the top panel.
- Fix: covers added by a fallback cover patch no longer disappear after the first draw (#500).
- Fix: under Most recently read on a series shelf, adding a book no longer counts as reading it: unread books, and the series they join, no longer jump to the front.
- Fix: every top panel progress bar style (Rounded, Metro, Wave, Pacman) now draws without Bookends installed; the default Rounded bar was square without it.
- Fix: a UI font with no italic file no longer fills the log with font errors (#501, thanks @Tsukumi233).

# v5.3.1 · 2026-10-03

- Fix: a series, author, genre or collection opened from book details shows all of its books again, instead of only those matching the shelf you opened it from (#480).
- Fix: on a spine shelf, the D-pad reaches every book on the page, and up and down move between shelves. Before, it stopped after the first few books on each shelf.
- Fix: on devices without a touchscreen (#361):
  - the page arrows, page number and start-menu button highlight as you move between them;
  - the book details tabs switch when you press on them;
  - the highlight in the shelf editor follows the D-pad instead of staying on the first button;
  - Back closes Adjust shelf/top panel size, the same as Cancel.

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

# v5.1.2

Fixes and polish for 5.1.

- Returning to the shelf after closing a book is much quicker (#422).
- Shelves showing folders open much faster (#409).
- The hero no longer glitches when you switch to a shelf with nothing in it (#423).
- Shelf colours no longer come out inverted when night mode is switched by something other than KOReader (#426).
- The shelf boards keep their wood colour with the shelf theme pinned to Light or Dark.
- Spine mode follows KOReader's "Folders and files mixed" setting.
- "Recently added" faces out that many books across the shelf, rather than that many on every screen.
- Face out the first, or the first unread, book of a series on a shelf with no series grouping (#425).
- The label under a cover follows the Panel shading setting.
- Tidier outlines in the shelf menu, and the drilled-in view now matches the top level.

# v5.1.1

A fix-up release for 5.1.0.

- The bundled wallpaper is actually installed now.
- Spine folders open much faster.
- Face out the next unread book in a series, not just the first.
- A face-out reason ticked on its own now works; "Unread" alone never did.
- "Pages" in list rows is translatable, and so is the rest of the progress line (#418).
- The top panel's menu items say "top panel" rather than "book detail view".
- New installs open on Home / Recent / Series / Genres.
- Russian, and the shading and speed labels that shared one word across unrelated menus (#416, thanks @d1-m4ss).

# v5.1.0

**A picture behind the shelf.** Wallpaper, chosen per shelf or as a library default, with a separate picture for full screen shelves where a backdrop that works behind the top panel is often too busy. Drop images into KOReader's `settings/bookshelf/wallpapers` folder and they turn up in the list; the menu always shows you the path, and one picture is bundled to start you off. Panel shading keeps the top panel and footer buttons legible over whatever you pick, from transparent through to solid.

**Background and colours.** A new menu at the top level holding the wallpaper, the background colour, the panel shading, the shelf theme and the accent colours. The shelf theme is new: Light, Dark, or follow the device, independently of KOReader's night mode, so you can keep the reader dark and the shelf light. Text ink sets the colour of the shelf's own text, black by day and white at night unless you say otherwise.

**Spine titles read top to bottom.** That is how British and American books are printed. Continental European spines run the other way, so Library & search now has a setting for it. Spine shelves will look different on upgrade.

**Ornaments take PNGs, and you say how often.** The frequency is per shelf, next to Author on spine: None, Rarely, Often or Always. Above None, a page is promised a piece every so often whether or not a wide enough gap happens to fall there, so a densely packed shelf still gets some. A row end offers as much width as the row can spare, so a broad ornament stands at full height instead of being quietly skipped, and a row that cannot fit a book beside one carries the ornament alone. Pieces take turns, so everything in the folder gets a share.

**The footer counts what it can stand behind.** A spine shelf fits a variable number of books to a row, so it shows a book range rather than a page number. Tapping it asks for whichever is on screen: a page number on a cover or list shelf, a book number on a spine shelf.

**A tidier menu.** Icons on the top-level entries. The shelves menu leads with editing, so a tap opens the editor and a long-press shows or hides. The accent colour list is grouped instead of running as one long column.

**A better first launch.** A fresh install now opens on a shelf that shows what Bookshelf is for, with a quote of the day in the top panel.

Two things were renamed, so the menus read differently: the hero card is now the **top panel**, and the expanded shelf is now **full screen shelves**.

Fixes:

- Restarting KOReader or leaving a book no longer causes an extra screen refresh on Kobo greyscale devices (#408)
- "Check for updates" now looks at the copy of Bookshelf that KOReader is actually running, so a second copy installed elsewhere stops reporting an old version
- A series whose name starts with "The", "A" or "An" now files under its real letter (#412)
- An OPDS category that held one entry can grow again on refresh (#411)
- A folder tile shows the book the folder opens with (#409)
- Every line of a list row takes the ink colour, not just the first
- The start menu's close button is visible again with a light shelf theme on a device in dark mode
- A colour reads the same percentage in the top menu and in the shelf's own dialog
- An ornament dropped into the folder appears without restarting KOReader
- Toggling night mode repaints the shelf once rather than in instalments
- A rounded cover corner shows what was actually behind it instead of a guess
- Bookmark glyphs sit over the cover label plate rather than under it
- An OPDS download's filename is sanitised the way KOReader's own browser does it

Under the hood, mostly around the spine shelf:

- The spine planner's entry list is cached, shared between drawing a page and working out where the pages fall, and kept across page turns. Pagination no longer balances every row in the library just to count pages, which was 585ms on a Paperwhite 5 at about 1200 books.
- A cover's shadow blends only the part the card leaves showing, and the shelf recess shades one rectangle rather than two thousand a paint. Together about 230ms off a cover tap on the same device.
- The cover cache's memory budget now follows the device's own memory instead of one fixed number.
- The new-file check backs off when the shelf is idle and pauses entirely with Wi-Fi off.
- The top panel's text composites through its own render rather than a column stencil, which is what lets it sit over a picture.

Translations: Russian and Slovak added, Spanish polished. Thanks to @d1-m4ss, @misko903 and @JortonMV.

# v5.0.8

Sorting by Title now ignores a leading "The", "A" or "An", and uses Calibre's Title Sort where a book has one (#401). Shelves sorted by title will reorder on upgrade.

Fixes:

- On a Series shelf that also shows standalones, books not in a series no longer sort to the end (#400)
- Covers are no longer grainy on Kobo and Onyx greyscale devices
- Ornament SVGs are no longer ignored when their viewBox uses commas, or when they have none at all
- A series named Calibre-style ("Dark Tower, The") now reads the right way round on its card

# v5.0.7

Books sideloaded after you have opened a book now appear on the shelf on their own, instead of needing a swipe-down refresh

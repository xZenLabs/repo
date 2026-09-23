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

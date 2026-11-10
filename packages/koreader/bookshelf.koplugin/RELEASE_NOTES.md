# v6.4.2 · 2026-11-09

- Comics from OPDS catalogs that serve CBZ files as ZIP now download as CBZ and show on the shelf (#592)
- Coloured text keeps its colour over a wallpaper or on a Dark shelf, on colour screens
- In night mode, the colour picker's swatches show their own colours, and a picked colour is saved as the one shown
- On Android in night mode, text and swatch colours are no longer inverted
- The status line shows the current time straight after waking (#596)
- Performance improvement for the first page turn after waking or restarting
- Performance improvement for Spines shelves with covers facing out
- Performance improvement for page turns through covers not seen before
- Performance improvement for expanding and collapsing the shelf

# v6.4.1 · 2026-11-08

- Book sizes > Equal height: a new option for spine shelves (long-press the shelf > View mode). Every book stands at the same height while keeping its own width, so landscape books facing out show their full cover, uncropped.

# v6.4.0 · 2026-11-08

- Decades: a new grouped source (shelf settings > Source > Grouped > Decades) stacks your books by the decade they were published, with Unknown last. "A decade" makes a shelf of just one.
- %published{format}: the full publication date in your own layout, like %published{%d %B %Y}. A book whose date has no month or day shows the shorter form.
- Book sizes in a spine shelf's settings: Varied, or Same to stand every book at one size.
- Series boxes can now be Cover, Plain (no picture) or Spines (the books spine-out, with the first cover printed across them) (#577).
- Series boxes in Covers and List too (long-press the shelf > View mode > Series boxes): each series gets one tile, on a shelf of books and inside an author or any other group (#503).
- Spine text size: Bookshelf settings > Text size > Spine text. Spines get thicker to fit larger text.
- Inside a Shelf of shelves, tap the shelf's name in the breadcrumb to open its settings.
- Shelves from other plugins' sources can now use Spines view, when the plugin offers it (#588).
- Genres from calibre only, under Read calibre metadata.calibre: genres come from calibre's tags alone, without the book file's old ones (#583).
- The top panel's description can be justified (#586, thanks @ferorborja).
- List view rows no longer have the small arrow on the right (#589).
- Faster page turns: the next pages are made ready while you read, and turning back to a page you just left is much quicker.
- Faster shelf switching and startup, most noticeable on older Kindles.
- Series and folder stack covers are resized more smoothly.
- Performance improvement for shelves of series or folder stacks, such as Series and Decades
- Performance improvement for author/title/series sorted shelves during metadata scans
- Performance improvement for page turns while KOReader reads new books
- Performance improvement for page turns on long shelves with ornaments off
- Performance improvement for Latest added and Home shelves with a status filter
- Performance improvement when the home folder is the top of the device (#590)
- Bookshelf now frees its memory when it's closed.
- Fix: books with no series number now come after the numbered ones, by title (#587)
- Fix: a spine page or series box could lay out differently when you came back to it
- Fix: disabling or deleting the shelf on screen left the next shelf wearing its theme
- Fix: Hardcover's first-published year was used even with Use Hardcover metadata off
- Fix: some EPUB 3 books showed no publication date
- Fix: Crop to fill with a very wide or very tall wallpaper
- Fix: Delete folder lost the reading progress of books it couldn't delete
- Fix: on a full disk, ornament changes stopped saving and a cover could be saved cut short
- Fix: a swipe down over a Bookshelf popup opened two KOReader menus
- Fix: covers extracted while KOReader was busy with a long scan didn't show until the page was turned
- Fix: spines flickered while publication dates were read in the background
- Fix: the colour picker's No background tile cut its label short
- Fix: the search box in Bookshelf's pickers (themes, icons, collections and others) went square while typing

# v6.3.3 · 2026-11-05

- Fix: tapping the page arrows in the book menu's Cover tab, after searching online for covers, crashed KOReader (#585)
- Fix: the "Refreshing library…" message didn't show, or showed cut off, on some Kindles such as the Paperwhite 6 (#584)

# v6.3.2 · 2026-11-03

- Wallpaper scaling: Stretch (as before), Crop to fill, or Fit to screen, from the new Scaling button in the wallpaper picker. For pictures whose shape doesn't match your screen (#578).
- The wallpaper picker shows each picture in the shape of your screen, as it will look with the current scaling. In portrait, the picture on screen is the one used: page through to choose.
- New sort: Publication year, the same year as the %published token. Books whose year hasn't been read yet sort last, then move into place once it has (#580).
- The book menu's Edit tab shows the publish date beside your rating and Hardcover's, with where it came from. Tap it to correct it with a date picker.
- With Use Hardcover metadata on, a linked book's publication year is Hardcover's first-published year.
- Long-press your star rating in the book menu to clear it.
- Random book's "All books" now includes your Kindle library books, if you have a Kindle Virtual Library shelf.
- Fix: books added by Scan all library metadata didn't show in their series until KOReader was closed and opened again (#581)
- Fix: changing a book's rating or status, removing it from history or changing its cover also cleared its stored page count and publish date

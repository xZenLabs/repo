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

# v6.3.1 · 2026-11-02

- Design tweak to book menu header
- Further improvements to compatibility with other plugins drawing over bookshelf (#572)
- Performance improvements for shelf of shelves with nested filters
- Performance improvements for page count extraction

# v6.3.0 · 2026-11-02

- New token %published: a book's publication year, from calibre, the OPDS catalog (kept when the book is downloaded) or the book file (EPUB, FB2, MOBI, AZW3, comics, PDF). For example, `%authors_short [if:published](%published)[/if]` adds the year after the author, and nothing when a book has no date (#566).
- Delete folder… in a folder's long-press menu. Move, Rename and Delete now sit beside the book count (#456).
- Fix: dialogs from some other plugins, opened from KOReader's menu over the shelf, were only partly drawn (#572)
- Fix: the book menu showed a placeholder instead of the cover for books shown as plain spines (#575)
- Fix: "Only books without a page count" counted books again that already had a count from being opened, or that had been read since their last scan (#573)

# v6.2.0 · 2026-11-01

- Image contrast (Settings > Image contrast): Covers and ornaments contrast boost deepens the darks and lifts the lights of covers, spines and ornaments, which can help on screens with few greys. Wallpaper contrast and brightness adjust the wallpaper on its own, and are also in Theme > Wallpaper. All off by default.
- Swipe left or right on the shelf behind a Bookshelf menu or slider to turn its page, so a change can be seen on more books without closing it.
- A tap outside a slider closes it and keeps the value.
- Footer bar (Settings > Behavior): Show, Hide (the shelf uses the space), or Invisible buttons (the buttons still work where they were, and moving into them with the keys shows them).
- Fewer full-screen flashes: closing KOReader's menu over the shelf, closing the Theme library, and moving between shelves with different themes.
- OPDS: a catalog book's publication year is available in %calibre{pubdate} (#569, thanks @amycardoso).
- Modules on a shelf can update every minute (on_minute), and a plugin adding a card to the home shelf works with modules switched off.
- Read calibre metadata.calibre is no longer marked beta.
- Fix: menu options added to a shortcuts folder disappeared after being switched on or off (#571)
- Fix: KOReader's menu could get stuck open after using a Bookshelf slider or the Theme library
- Fix: a shelf with no wallpaper could show the wallpaper of another shelf
- Fix: opening a face-out book on a spines shelf lost the shadow of the plank above, and is quicker
- Fix: select rings had black corners on Android in night mode

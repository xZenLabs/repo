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

# v6.1.1 · 2026-10-31

- Fix: Minor layout issue with some nested library windows

# v6.1.0 · 2026-10-31

- A new look for Bookshelf's menus: the book menu, shelf editor, pickers and ornament menu share one style and the Bookshelf UI font, with cards, a close X on the title, and sub-menus that open as pages inside the menu, with Back and a breadcrumb.
- Tap the current shelf's button to open its editor (Settings > Behavior > Bookshelf gestures to turn off; long-press still works).
- Shelf editor: a shorter front page, with View mode beside Source and Filters beside Sort. Shelf order lists every shelf to move up or down; tap one to edit it. Modules shows how many the shelf has, and on a spines shelf opens a page of them.
- Filters: Genres can be any of (OR), all of (AND), or leave out (NOT); Collections can be left out. Picks show as tags you tap to remove. Folders are added from Bookshelf's own folder list. Author, series and filter lists sort A-Z or by most books.
- The Theme library sorts A-Z, Newest or Last used.
- Book menu: long-press an action on the Edit tab to rearrange or hide it. If any Hardcover reviews include spoilers, there's now an option to show them.
- Search results have their own view mode settings (long press the search icon), which also applies to an author or series opened from them.
- Size settings are a slider with step buttons.
- Ornament menu redesigned: Pin to a spot, Hide/Show, and Swap offers any piece from any pack. The ornament library opens far faster with large collections (about 32 s to under a second on a Paperwhite 5 with 443 pieces).
- QR codes: About links to the user guide, and Add theme pack and Add ornaments to the shop, to open on a phone.
- Faster first visit to a shelf after a restart: the cover cache keeps the covers you use, and large ornament renders no longer affect cover cache. Devices with little memory (under 384 MB) use a smaller cover cache to improve reliability when ram is tight.
- Keyboard and page-button devices show a focus ring throughout, and can reach modules and ornaments on a shelf to open their menus.
- Home now shows books flattened and sorted by Added/opened by default, unless you have changed its settings.
- A theme pack's missing parts (wallpaper, planks, colours) now come from Plain rather than your Custom theme.
- Modules from other plugins can now size their own modules, reach their own plugin and add a module to the home shelf.
- Fix: KOReader crashed opening a folder on a shelf whose name has an icon and text
- Fix: the shelf bar keeps its order in right-to-left languages (#559)
- Fix: KOReader's menu and brightness gestures work while the shelf editor or a Bookshelf menu is open
- Fix: Edit selected's Apply works alongside other UI's that modify KOReader menus (#567)
- Fix: a fresh install's first page shows its ornaments
- Fix: modules on spine shelves start at their own width, and a wide one no longer pushes the books onto the next page
- Fix: + Add shelf on a list matches the panel's colours
- Fix: a long file path in the book menu stays on one line
- Fix: a shelf's icon shows in the shelf editor's title instead of its [icon=...] code

# v6.0.4 · 2026-10-27

- Fix: Module card colours on PocketBook colour screens (#565)
- Fix: Border colours stay in colour on colour Kobo and Kindle screens
- Fix: Black screen after waking with Sleep screen anti-ghosting on
- Fix: Fewer full-screen flashes closing Shelf style and Filters
- New: Search in the collection editor (#488)

# v6.0.3 · 2026-10-26

- Fix: Paint shelf after sleep resume on some devices (#551)
- Fix: Status line tap keeps full screen when swipe back is off (#554)
- New: Micro modules > On the shelf switch

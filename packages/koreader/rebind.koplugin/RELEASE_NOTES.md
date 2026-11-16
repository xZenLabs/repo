# v2.4.0 · 2026-11-16

## [2.4.0](https://github.com/rameezk/rebind.koplugin/compare/v2.3.0...v2.4.0) (2026-11-15)

Rebind can now fix your covers as well as your metadata.

Lots of books show up in the library as a blank tile, or with a blurry cover from the wrong edition. Now the picker shows the cover from the matched book next to the one your book already has. You can see both, compare them, and choose. Rebind always keeps your book's original cover inside the file, so you can undo the change later.

### Adding a cover

- If a book has no cover, the picker shows the cover from Hardcover, Open Library or Inventaire, with its size in pixels.
- That cover is selected from the start, so applying the picker adds it to the book.
- Rebind only offers JPEG or PNG covers that are big enough and shaped like a book cover. Anything else is skipped, so you never get a tiny or stretched image.

### Replacing a cover

- If a book already has a cover, the picker shows it on the "book" tile, next to the matched book's cover.
- Your current cover stays selected. Nothing changes unless you tap the other cover.
- The library thumbnail and the first page of the book both show the new cover after you apply it.

### Getting the original back

- Rebind keeps the cover your book had before Rebind first changed it, inside the EPUB.
- When a book has a kept original, the picker shows an "original" tile. Select it and apply to put the original cover back.
- If the book had no cover before Rebind added one, the tile reads "no cover", and applying it removes Rebind's cover.

### Previewing a cover

Hold any cover tile to see it full screen, with where it came from, the edition, its size in pixels and its file size. Tap "Select this cover" to choose it, or "Back" to keep what you had.

### Covers in a batch

- "Rebind N sure matches" now also adds a cover to any book that doesn't have one yet. Books that already have a cover are left alone.
- The summary afterwards tells you how many books got a new cover.
- Tap any book in the review list to open its picker with the cover field, just like rebinding a single book. That is where you replace a cover or get the original back.



### Features

* add missing covers when rebinding sure matches ([#152](https://github.com/rameezk/rebind.koplugin/issues/152)) ([800ee82](https://github.com/rameezk/rebind.koplugin/commit/800ee82acab43cd8d2bb96db7b5c93c703146762))
* hold a cover to preview it full screen ([#150](https://github.com/rameezk/rebind.koplugin/issues/150)) ([78122ea](https://github.com/rameezk/rebind.koplugin/commit/78122eab47d48429edda5d16e20c564a7b92c24a))
* offer the Hardcover cover for a book that has none ([#148](https://github.com/rameezk/rebind.koplugin/issues/148)) ([22a614e](https://github.com/rameezk/rebind.koplugin/commit/22a614eabdeea8c665a141d9b9ec1bc1b3f759e5))
* offer the Open Library and Inventaire cover for a book that has none ([#151](https://github.com/rameezk/rebind.koplugin/issues/151)) ([e2e45ef](https://github.com/rameezk/rebind.koplugin/commit/e2e45ef967c88b5c27d990100a0df05dea3d4917))
* replace a book's cover with the Hardcover cover and keep the original ([#149](https://github.com/rameezk/rebind.koplugin/issues/149)) ([c5b2268](https://github.com/rameezk/rebind.koplugin/commit/c5b2268568e34adbe574483ba77cb395e44a6303))
* restore a book's original cover from the picker ([#153](https://github.com/rameezk/rebind.koplugin/issues/153)) ([0835c3d](https://github.com/rameezk/rebind.koplugin/commit/0835c3dcc1069abb8ed4cc4567d6dbd40b6f1fe1))
* say how many books got a new cover after rebinding sure matches ([#161](https://github.com/rameezk/rebind.koplugin/issues/161)) ([3183ad7](https://github.com/rameezk/rebind.koplugin/commit/3183ad7762ca13cd8dbc1833ba84fdec2d2c86a3))


### Bug Fixes

* choose covers in the picker opened from a review row ([#160](https://github.com/rameezk/rebind.koplugin/issues/160)) ([ec6ab5b](https://github.com/rameezk/rebind.koplugin/commit/ec6ab5b7502fce2869b491b2fad276495f367ac3))

# v2.3.0 · 2026-11-11

## [2.3.0](https://github.com/rameezk/rebind.koplugin/compare/v2.2.0...v2.3.0) (2026-11-11)

Rebind can now work through a whole folder of books at once.

Until now you rebound one book at a time. That is fine for the odd book, but slow when you have just copied a dozen new books onto your device. Now you choose several books, Rebind looks them all up, and you get one review list. Every sure match can be rebound with a single tap, and you go through the rest one by one in the same picker you already know.

### Starting a batch

- Tools → Rebind → Rebind several books…
- Long-press a folder and tap "Rebind books in this folder"
- Select books in the file browser's select mode, even across folders
- Bind "Rebind several books…" to a gesture

### Reviewing and rebinding

- Books land in the review list as sure matches, books to review, and books that are done.
- "Rebind N sure matches" writes each sure match exactly as its picker would, using one Save as for the whole batch, and shows progress with "Stop after this book".
- A summary at the top counts what happened. A book that could not be written or moved goes back to review with the reason.

### Safeguards

- Rebind asks before looking up more than 300 books, and tells you roughly how long it will take.
- It asks before you close the review list with books still unfinished.
- If the connection drops, the remaining books are marked "Lookup failed" straight away instead of each waiting out a timeout. Tap one to try again.
- The book open in the reader is never touched.
- Your device stays awake while a batch is looking up or writing, so it does not sleep and lose Wi-Fi halfway through.

### Also new

Long-pressing a book in Collections, History or file search now shows the Rebind button, just like the file browser.


### Features

* ask before big or unfinished batches and fail the rest when the connection drops ([#129](https://github.com/rameezk/rebind.koplugin/issues/129)) ([4ca38bf](https://github.com/rameezk/rebind.koplugin/commit/4ca38bff2e354c8a5778bc1802656f915e70e4ff))
* choose several books, look them up and review them in one list ([#126](https://github.com/rameezk/rebind.koplugin/issues/126)) ([3ca7cd1](https://github.com/rameezk/rebind.koplugin/commit/3ca7cd160d743f12ec2cfab3067a55a7e75fca31))
* keep the device awake while a batch is working ([#130](https://github.com/rameezk/rebind.koplugin/issues/130)) ([34006f4](https://github.com/rameezk/rebind.koplugin/commit/34006f44858f92a8a6815f9dca45cc0b1baab0ab))
* rebind a book from collections, history and file search ([#124](https://github.com/rameezk/rebind.koplugin/issues/124)) ([be863ab](https://github.com/rameezk/rebind.koplugin/commit/be863abc5d11e1e469f5977a63e86eccea5b5f90))
* rebind every sure match in a batch with one tap ([#127](https://github.com/rameezk/rebind.koplugin/issues/127)) ([573e93f](https://github.com/rameezk/rebind.koplugin/commit/573e93fcb79c01af677bf866a9589976456cff05))
* start rebinding several books from a folder, a selection or a gesture ([#128](https://github.com/rameezk/rebind.koplugin/issues/128)) ([e14dbcb](https://github.com/rameezk/rebind.koplugin/commit/e14dbcba2d6b7f51c1771ba56f2f8c5acdae7736))

# v2.2.0 · 2026-11-09

## [2.2.0](https://github.com/rameezk/rebind.koplugin/compare/v2.1.0...v2.2.0) (2026-10-29)


### Features

* choose and order lookup providers in settings ([#99](https://github.com/rameezk/rebind.koplugin/issues/99)) ([1868981](https://github.com/rameezk/rebind.koplugin/commit/1868981fb81964616156ba315498d01a0ca7c37b))
* look a book up in one provider with edited search terms ([#103](https://github.com/rameezk/rebind.koplugin/issues/103)) ([f67e35e](https://github.com/rameezk/rebind.koplugin/commit/f67e35edfd4c5c155cf8bd68c06a932cbeace916))
* look books up in Inventaire when Hardcover and Open Library have no match ([#102](https://github.com/rameezk/rebind.koplugin/issues/102)) ([70bb756](https://github.com/rameezk/rebind.koplugin/commit/70bb756bede892252392d693083ea2ead9386e85))
* look books up in Open Library when Hardcover has no match ([#98](https://github.com/rameezk/rebind.koplugin/issues/98)) ([bea7562](https://github.com/rameezk/rebind.koplugin/commit/bea75625a599095414a34b55d7e29416d7a7a1bc))
* name the lookup provider in the picker and list fields it had nothing for separately ([#96](https://github.com/rameezk/rebind.koplugin/issues/96)) ([13f794e](https://github.com/rameezk/rebind.koplugin/commit/13f794e67abbde1b00b0ada17b41c38561db6896))


### Bug Fixes

* stop KOReader closing when opening lookup providers or rebinding a book ([#105](https://github.com/rameezk/rebind.koplugin/issues/105)) ([a2719f7](https://github.com/rameezk/rebind.koplugin/commit/a2719f78cec91c4826c76f908ecde0684621b911))

# v2.1.0 · 2026-10-07

## [2.1.0](https://github.com/rameezk/rebind.koplugin/compare/v2.0.0...v2.1.0) (2026-10-07)


### Features

* pick an edition automatically when a book matches by title and author ([#85](https://github.com/rameezk/rebind.koplugin/issues/85)) ([ac567e1](https://github.com/rameezk/rebind.koplugin/commit/ac567e1a2230013439828315b3f6da7082dd421a))
* tidy the picker screens so lists close from the header and long labels fit ([#83](https://github.com/rameezk/rebind.koplugin/issues/83)) ([b4fe5ae](https://github.com/rameezk/rebind.koplugin/commit/b4fe5ae01ef728c3d16241b8c9cb050c28e43746))

# v2.0.0 · 2026-10-07

## [2.0.0](https://github.com/rameezk/rebind.koplugin/compare/v1.6.0...v2.0.0) (2026-10-07)

Rebind 2.0 redesigns its interface so fixing a book takes less scrolling, fewer taps and less guessing.

- **Far less scrolling.** Each field is now a short list of values instead of rows of buttons, so a whole book fits on one or two screens of a 6" e-reader.
- **Only what needs a decision.** Fields that already match Hardcover are folded away, so you only look at the ones that differ.
- **You know where a value came from.** Each value is tagged book, Hardcover, custom, translated or removed, and machine translations are shown in italics so they stand out.
- **Mistakes are caught before anything is written.** A name clash at the destination is flagged before Apply instead of after the book is saved, and closing only asks to discard when you've changed something.
- **Renaming and sorting are in one place.** Backup, folder and filename settings moved to one Save as screen. It shows the exact destination path and remembers your choices, and the "Move into" popup after Apply is gone.
- **Templates you can judge at a glance.** Each folder and filename template is shown as it will look for this book, not just as a pattern.
- **Write your own templates.** When none of the ready-made templates fit, write a custom folder or filename template. Tap to insert tokens like Title, Author and Series #, check the Example preview as you go, and use Help to see each token's value for this book.
- **Rename or move on its own.** Apply now renames or moves a book even when its metadata doesn't change.
- **Works without Hardcover.** Choose "Don't use Hardcover", or carry on when the plugin is missing or a lookup fails, and edit every field by hand.
- **New field:** first published, saved as the book's year.

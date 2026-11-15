# v6.5.2 · 2026-11-15

## Fixes

- Changing the favourite icon (heart, star or rating) or a cover mark's "Show on spine shelves" switch now updates spine shelves straight away, instead of after a restart (#605)
- Section and series labels on spine shelves no longer go missing or sit behind the books after turning a page (#606, thanks @tku137)
- Kindle library: books marked as read on the Kindle now show as finished, and title and author corrections made in KOReader are kept (#607, thanks @bezlant)

# v6.5.1 · 2026-11-14

## New

- Turkish translation
- Favorites can be sorted by Collection order, then arranged by hand: long-press a book on the shelf to move it

## Improvements

- Hardcover ratings round to the nearest half star (3.9 now shows 4 stars, 3.3 shows 3½)

# v6.5.0 · 2026-11-14

## New features

- Collection shelves you arrange yourself (#390): Source > Your own collection picks a KOReader collection or makes one. Long-press a book to arrange: swipe it a place at a time, or long-press another book or ornament to swap them. Tap another book to arrange that one instead. Add ornaments among the books and move them the same way.
- Hardcover works without a sync plugin, or with either one (#603): give Bookshelf a Hardcover API key in Hardcover enrichment > Hardcover API key
- Auto-link all books now runs in the background while you use your device, with progress in the status line. It pauses when you open a book and carries on when you come back to the shelf.
- Sort by time left (#602)
- Rating stars can take a colour of their own (#594)
- The top panel's rating row has its own options (#484)
- Each cover mark can show on covers, spine shelves, or both (#597)
- Reading goals show as many goals as the cell has room for: all in a row, two rows of two, or a stack
- Plugins can give their book menu button an icon of their own (#604, thanks @ghepting)

## Improvements

- Choosing a Hardcover book or edition shows covers, two to a row, inside the Hardcover menu
- The book menu has a Hardcover link card, says which book it is linked to, and has clearer labels
- Faded books are see-through, and fade on spine shelves too
- Spine-out series boxes show titles on every spine, or on none
- "Instant book close (beta)" is now "Close books in the background"

## Fixes

- Reload metadata no longer removes a book's cover
- Better handling of book detection under certain folder configurations
- A search with no matches no longer shows "Set home folder", and says "No matches" on a filtered shelf
- After Select multiple adds books to a collection or takes them off, a shelf showing that collection updates straight away
- KOReader no longer fails to start when a device restart leaves an empty cached file behind

## Performance

- Performance improvement for switching between shelves
- Performance improvement for shelves of shelves

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

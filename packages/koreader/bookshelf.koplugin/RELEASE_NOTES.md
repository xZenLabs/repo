# v6.6.0 · 2026-11-22

## New

- **Vocab Word** module: a word from your Vocabulary builder list, with its dictionary definition and the sentence you looked it up in. Tap the word for KOReader's dictionary popup, or mark it "I know it" to drop it. If Vocabulary builder is off or has no words yet, the card says how to fill it (#263, thanks @xerraires)
- Extract page counts now counts unopened books at your Characters per page default, so their count no longer changes the first time you open them
- The see-through parts of a PNG wallpaper now show Color behind wallpaper instead of black (#612)
- Faded books stay readable over a busy wallpaper, and pick up the blur when Blur wallpaper behind panels is on
- New Settings > Advanced > Performance tweaks > **Compiled code cache** switch. Bookshelf turns it off by itself if it fails to start twice in a short time

## Fixes

- A start that froze right after the shelf appeared, until the cache folder was emptied by hand, now clears its own start-up caches (#621)
- Series boxes on a grouped spine shelf stay inside their author or folder group (#620)
- Countdown counts dates after 2038 correctly on Kobo and older Kindles (#616)
- A Kindle home folder set to /mnt or / no longer shows every book twice (#619)
- Opening the previous book from the file browser's menu or gesture while the shelf is open returns to the shelf on close
- Android: Restart after an update no longer shows KOReader's crash screen
- Hardcover: the edition list no longer crashes KOReader when the hardcoverapp plugin is installed (#624, thanks @will-darwin)
- Faster first load of the shelf for anyone who has ever used KOReader's hash sidecar location
- Translations: "Read now" and the single Series button now translate separately from the "Read" date and the Series group (#618, thanks @johannesbehr)

# v6.5.3 · 2026-11-19

## Fixes

- Taps made while a book is opening no longer turn pages once it appears, on devices where opening a book is slow (#610)
- Kavita: books downloaded over OPDS show their description instead of the file type (#613, thanks @Charliechin)
- The analog clock's date is no longer cut off in the top panel on high-resolution screens set to Auto DPI (#615)

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

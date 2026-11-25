# v6.6.1 · 2026-11-25

## Fixes

- Fix potential crash using KOReader menu search when accented or non-Latin characters are truncated (#629, thanks @tku137)
- Search ignores capitals in accented and non-Latin text (#627, thanks @pgrekovich)
- A book that never finishes rendering no longer holds up the page-count scan

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

# v1.3.2 · 2026-11-12

Hotfix: fixes KOReader crashing on start, or when opening Data shard, with Chinese, Japanese and other multi-byte highlights; windows such as the OPDS Add catalog form now open in front of lists; colour-screen popup refresh. Devices stuck restarting recover by updating. See CHANGELOG.md.

# v1.3.1 · 2026-11-09


### Fixed

- The reader's bottom settings panel: the step bars (line spacing and the other bars made of steps) did not react to taps. They now call KOReader's own control directly, so every step, the fine-tune and the "more" buttons work.

# v1.3.0 · 2026-11-09


Everything since 1.1.2: KOReader's own windows in CyberUI's style, a rebuilt book details page, eddies that pay for reading, and a lot of smaller fixes.

### Added
- **KOReader's own windows are in CyberUI's style.** Notices, questions, button menus, the on-screen keyboard and text entry, lists (contents, bookmarks, history), the selected-text menu, the edit-highlight dialog and the dictionary. Also the note and text viewer (paged text, icon and warning buttons), number, two-number, date and time pickers (big values with steps and a slider, columns for a clock), lists to choose one from, forms with several fields, information lists (book details, statistics), sorting windows (a step up and down on each row), the folder chooser (a Choose this folder button), progress windows, QR codes, the keyboard language picker, the Wi-Fi list (strength icons, secured or open, the connected network first, Disconnect and Edit) and the book status page. KOReader still builds and runs every one, and each stays where it was in front of or behind other windows; anything CyberUI does not know is shown as KOReader made it.
- **A switch for each kind of window.** **KOReader dialogs** in System > Home turns it all off and opens a page with a switch for notices and questions, the selected-text menu, button menus, keyboard and text entry, lists, the dictionary, pickers, viewers, the Wi-Fi list and the reader panels, so a problem with one kind can be switched off alone.
- **The keyboards can be put away.** A HIDE handle on the keyboard, and a tap beside it puts it away; in CyberUI's own typing panel the text stays, with Save and Cancel left, and a tap on the field brings the keyboard back. New key plates: cut corners that alternate along a row, outlined digits, a warning-coloured backspace, a bracketed space bar.
- **Gigs and eddies can be turned off** in System > Gigs, after three "are you sure" windows. Off, nothing pays, the Gigs tile becomes the shop and every look can be worn. Turned back on, any look that was not paid for goes back to the free one, and eddies and purchases are kept. The gig settings have their own tab.
- **Every book pays eddies**, not only gigs: about a tenth of an eddy per page, paid as you read and when you finish. Only books started from the beginning count.
- **A small board of gigs.** The board offers 5 unopened books at a time (3, 5 or 10 in System > Gigs), drawn at random and drawn anew every week (3, 7 or 14 days). Gigs pay two to four times the plain rate, and a book's price grows by a quarter per week it has waited, up to double after a month.
- **Roll a gig** for 20 eddies to swap it for another book (hold a gig on the board).
- **Series from the books' own details.** Collections has a Series switch listing every series found in the books' metadata (two or more books), each opening its books in series order.
- **Edit a book's details.** Title, authors, series, series number, genres and language, one row each. Changes are KOReader's own custom metadata, so the book file is untouched and KOReader and other plugins show them too.
- **Group the library by genre.** Group by > Genre uses the books' genres (a book with several appears under each).
- **Rename a collection.** Holding a collection offers Rename and Delete; saved filters and views follow the new name.
- **Highlights, notes and bookmarks pages.** The counters on a book's details are buttons: each opens a CyberUI list of that kind, newest first, and a tap on an item opens the book at that place.

### Changed
- **The book details page gives the synopsis the room.** Cover, title, author and series, genres and size, two small chips, then the whole synopsis, and one row at the bottom: Open (or Take gig) with Edit info and More. Rename, move, delete, forget and show folder moved into More.
- **Eddies are paid for reading, not for turning pages.** A page counts once it has been on screen for 15 seconds. Pictures and files under 50 pages no longer pay or appear as gigs, and a never-opened book's length is capped at 800 pages. Prices are exact: a 300-page book pays 30 eddies at the plain rate. Gigs already taken keep their price and what they paid.
- **The keyboard has accented capitals and a locked Shift.** The accented layer covers Portuguese, Spanish, French, German, Turkish and Polish letters and has its own Shift; tap it twice to lock it.
- **Buttons never lose their words or icons.** Button rows size to their labels and wrap (Cancel and Paste were being cut off), a button that has only an icon keeps it, known verbs (open, rename, delete) get icons and destructive ones the warning look, and plugin lists keep the glyphs, switches, arrows and small lines their entries carry (ZenOS's settings, for one).
- **Keyboards from other plugins keep working.** Keys that type a word (suggestions) keep their words.
- **The menu's lists are taller**, up to 80% of the screen; System > Home > Menu height sets 50, 65, 80 or 90%.
- **Lumen and tint are sliders** in the menu's Deck and Controls pages and in KOReader's frontlight window.
- **Saving the ID card asks where**, with a folder picker, and reports a folder that cannot be written to.
- **The settings panel and the selected-text menu in books are in CyberUI's style**, going back to KOReader's look with their switches.
- **Ink Away's quick menu opens as a CyberUI sheet** from its tab in the menu, docked at the top there and centred over a book, and its tab shows the pen.

### Fixed
- KOReader quit to the device's own system when a swipe began on the tab bar.
- In a book, KOReader's drop-down menu stayed over a plugin's dialog opened from it (Bookends' settings, for one); it now steps aside.
- The selected-text menu showed blank buttons on KOReader versions that build it differently; it is recognised on any KOReader and keeps every icon.

# v1.1.2 · 2026-11-01

## Fixed
- **Night mode no longer crashes KOReader on colour screens.** On a Kindle Colorsoft or a Kobo Clara Colour, turning on night mode (or going home from a book while it was on) closed KOReader, and it kept closing at every start. Covers are now drawn in the screen's own pixel type.
- **No more freeze on phones.** CyberUI no longer follows linked folders or Android's own data folder while it looks for books, and stops after a few thousand folders.
- **ZenOS:** its Home tab in the toolbar now goes to CyberUI home when CyberUI is the chosen home screen.

## Changed
- A list of choices too long for the screen (the collections when adding a book to one, filters, and the like) is now split into pages with previous and next buttons, so every entry can be reached.

Thanks to everyone who reported these.

# v1.1.1 · 2026-10-31

## Fixed
- Choosing a folder no longer ends in "Something went wrong" and a crash. This hit
  Statistics scope (Add a folder), Library opens in, and moving books to a folder.

Thanks to everyone who reported it.

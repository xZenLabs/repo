# v1.5.0 · 2026-11-23

Speed everywhere: starts, book opens and closes, library pages and sorting, with the jack-in card up the moment you tap. Also the eddies on every book's dossier, and the fixes that were waiting as 1.4.1.

### Added

- **Switching to SolarUI asks first**, so a stray tap never swaps the whole look.
- **Every book's dossier shows its eddies**: a bar of its ten payouts and the finish, what it has paid out of its price, the next payout, what is still to earn, and how its pages are counting (tap it to see the rule), compact enough to leave the synopsis its room. The Gigs page's Active tab now lists every book that is paying, not only gigs, each with the same bar.
- **Long press on the < and > of a list** goes to its first or last page.

### Changed

- **Faster everywhere.** Closing a book back to home no longer rebuilds KOReader's file browser hidden under it (nor lets CoverBrowser extract covers for it): the browser lists its folder only when it is actually shown. Opening a book draws only the jack-in card, which now goes up the moment you tap, before KOReader even looks the book up, and stays until the book appears. Turning library pages no longer sorts the whole folder again, and KOReader starts to home sooner: fewer modules load at start, CyberUI's own are kept compiled (together in one file) after their first load, icons are drawn from saved copies, and the home screen shows the last counts until the library has been looked through. Changing the sort order is about a third quicker, page turns redraw less, a book reopened shows its cover on the jack-in card without drawing it again, and opening a book from home no longer sets off a needless full memory clean-up a moment later. Going Home while home is already shown no longer redraws it (and flashes the screen) unless something on it changed. Less memory too.
- **Pages count by how much is on them, not by a fixed 15 seconds.** A book is measured once when it opens, and a page counts once its words could have been read, even very fast: in a large font or at a quick pace, pages count in a couple of seconds, while flipping through still pays nothing. Comics and scans count by your own pace in that book. Page turns do no extra work.

### Fixed

- **KOReader opened to the plain file browser instead of CyberUI** after a KOReader update or on a fresh install (CoverBrowser's "database updated" notice at start left the file browser on top of home), and the top menu did not open until a book was closed.
- **KOReader crashed** when going home from a book while the top menu waited for a plugin's window (Reading style, for one), and the top menu could stop opening in books after changing such a plugin's settings.
- **The page turn keys did nothing in styled lists**, such as Rakuyomi's chapters, history or the table of contents.
- **A swipe down closes a styled list** again, as it does in KOReader.
- **KOReader crashed when opening System, About** on newer KOReader versions, whose QR codes are made differently now.
- **Progress under covers in the library** now fills to the exact share; it showed only empty or full.

# v1.4.0 · 2026-11-16


A twin: CyberUI and SolarUI, the new Art Nouveau garden home, switch with one tap.

### Added

- **The twin switch.** A plaque at the top of System, half cyberdeck and half garden, and a tile in the menu's Controls tab, hand home over to SolarUI at once and back. Only the UI in charge opens at start, comes back after a book and styles KOReader's windows, menus and sleep screen; each keeps its own settings. Without SolarUI the switch offers to install it.
- **Corner to home.** A Home setting makes holding the bottom-right corner in a book open CyberUI's home, and the corner follows whichever twin is in charge.

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

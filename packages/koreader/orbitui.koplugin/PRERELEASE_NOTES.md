# v1.5.0-beta.2 · 2026-11-24

### Your next BookOrbit milestone on Home

The optional **BookOrbit achievements** card now shows your latest award alongside the milestone you are closest to earning. See how many books, pages, reading hours or streak days remain. For other goals, the card shows the current count and target. The summary uses your existing BookOrbit plugin login and works without a separate API key or server changes. Tap the card to browse the available badges.

### Bookshelves and Android covers

- Bookshelf 6.6.0 keeps series boxes inside their author or section group and preserves cover contrast over wallpaper.
- In Android safe mode, reopening a shelf skips books already checked for a cover when their file size and modification time match. Adding a custom cover, changing the book file or choosing **Refresh metadata** triggers another check.
- Library metadata lookup skips per-book hashing when the hash-sidecar storage contains no custom metadata.

### Home and reading statistics

Home skips redundant repaints while a full-screen window is open. Reading-day statistics handle UTC offset changes, and finished-book actions let you correct a status or exclude a book from goals. This release also includes updated date formatting and Czech and Chinese translations.

The milestone and cover handling were tested on a physical HiBreak. All 96 navigation taps in the Library and Manga comparison reached the expected view. The cover optimization applies to Android safe mode.

To update, enable **Include preview releases** under **OrbitUI → System & maintenance → Updates**, check for updates, then restart KOReader. For a manual install, download **orbitui.koplugin.zip** below. The stable channel offers **1.4.0**.

# v1.5.0-beta.1 · 2026-11-21

### Select text with FingerTips

Touch and drag to see the line above your finger. After lifting your finger, drag either handle to adjust the selection. The floating bar uses your six OrbitUI shortcuts, including actions provided by KOAssistant. FingerTips is bundled and enabled by default on touchscreens. An enabled standalone copy takes priority and existing FingerTips preferences carry over. You can turn it off under **OrbitUI → Integrations → Reader panel & X-Ray → FingerTips text selection**.

### Revisit words from your books

Add **Vocab Word** to the Bookshelf start menu to review words saved in KOReader’s Vocabulary Builder. It uses your installed dictionaries offline and can show the original sentence and book. Tap the word to open its dictionary entry or mark it as known to remove it from rotation. Opening the module picker skips the dictionary lookup.

### Home, Reading log and shelves

- Home can adapt text contrast to the wallpaper. The Reading log adds a monthly books/pages chart and shows your pace towards the annual goal.
- Bookshelf 6.5.3 discards taps queued while a book opens. The reviewed SimpleUI 3.1.0 updates include statistics-card actions, clock date formats and subview navigation fixes.
- Optional Library and Manga diagnostics measure the time to first paint on the device.

To update, enable **Include preview releases** under **OrbitUI → System & maintenance → Updates**, check for updates, then restart KOReader. For manual installation, use the attached **orbitui.koplugin.zip**. The stable channel offers **1.4.0**.

Tested in KOReader 2026.07.1 on an emulated Tolino Vision Color with a local dictionary and an EPUB. Physical Bigme and Kobo checks are still open for this beta.

# v1.4.0-beta.7 · 2026-11-18

Tap **Reading streak** on Home to open the new **Reading log**. See reading time and pages over the last seven days, explore a twelve-week calendar, and tap a day to see which books you read. The Goal tab follows the goal already configured on your dashboard.

**BookOrbit achievements** is a new optional Home card. The connected BookOrbit plugin supplies the latest earned badge and the next goal. To browse the full catalogue of earned and remaining badges on BookOrbit 3.8.0 or later, add a read-only BookOrbit API key. The card keeps the last results available offline.

### Library and search

- Library and Manga do fewer filesystem checks when preparing large shelves. The Next shelf preloads progress in short steps so you can keep navigating.
- Manga folder boxes retain their display order without sorting books twice. Library folder matching, typo-tolerant search and word suggestions do less work.
- You can clear a rating by tapping the selected star again. The BookOrbit Want to Read action now shows its feedback dialog reliably.

### Home and file browser

- Closing a book refreshes enabled reading statistics even when Home is already waiting to rebuild. Empty book modules avoid unnecessary page redraws. A fix found during emulator testing also keeps lightweight modules from crashing Home when their first item appears.
- The file browser has independent shadow settings for list and mosaic views, stacked folder covers in lists, and a reading progress bar that uses the available row width.
- Includes the latest reviewed SimpleUI 3.1.0 fixes and translation updates. Bookshelf is at 6.5.2.

Update through OrbitUI’s preview channel or install the attached **orbitui.koplugin.zip**. The stable channel continues to offer 1.3.0.

# v1.4.0-beta.6 · 2026-11-16

## What’s new

- **Hide Home pages.** Open **OrbitUI → Home → Layout & modules** to hide a page and bring it back with its configured modules.
- **Hide books from reading history.** Use **Hide from history** in History. Restore books from **Hidden books** in the Recent Books source settings. OrbitUI also excludes those books from its ongoing reading lists.
- **File browser views.** SimpleUI 3.1.0 adds per-tab view and sort options, updated list rows and a flat view that includes books in subfolders. Open **OrbitUI → Dock & interface → File browser appearance** for the file browser’s settings.
- **Bookshelf 6.5.2.** Spine marks such as the favorite icon update after a setting change. Kindle read flags and custom title and author metadata are handled more accurately.

Enable **Include preview releases** under **OrbitUI → System & maintenance → Update OrbitUI**, check for updates, and restart after installing.

Tested with KOReader 2026.07.1 in the Tolino emulator. Physical Bigme and Kindle testing is pending.

# v1.4.0-beta.5 · 2026-11-15

## Text selection shortcuts

- Select text and open **More… → Customize text selection menu**. Tap any of the six positions to choose what goes there.
- Use actions offered by installed plugins, including **Hardcover quote** and KOAssistant quick actions. A KOAssistant shortcut follows the chosen action when the plugin reorders its list.
- **More…** continues to show the full list for the current selection.

To update in KOReader, enable **Include preview releases** under **OrbitUI → System & maintenance → Update OrbitUI**, check for updates and restart after installing.

Tested with KOReader 2026.07.1 in the Tolino emulator, with KOAssistant and a test button that uses the same label mechanism as Hardcover. Physical Bigme testing is pending.

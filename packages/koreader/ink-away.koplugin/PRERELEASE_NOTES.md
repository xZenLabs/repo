# v4.4.4 · 2026-11-13

Test build. Fixes finger taps going dead or turning into undo on the Kindle Scribe after writing with the pen. Also adds the long-press bookmark on the page number, the panning map on colour readers, hidden-folder picture picking, and remembering the last notebook page. Full list in CHANGELOG.md.

# v4.4.3 · 2026-11-09

**This is a prerelease.** To get it from inside Ink Away, turn on Settings, Updates, "Tell me about prereleases", then install it from there. Or download `ink-away.koplugin-v4.4.3.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder. You can go back to the latest release from Settings, Updates at any time.

Everything in 4.4.2, plus:

**New**
- **Two pages side by side** for a PDF, CBZ or other fixed-page book, also when all its pages are single ones. In the book's Ink Away menu: always or only in landscape, with the first page on its own if it has a cover, and optionally for every PDF. Ink stays on the page you drew it on.
- **Annotate on a viewer plugin's page**, such as Panels+ (comics panel by panel), with the ink kept as on the book's own pages. An experimental integration API designed by Kristan Laimon (#80); see `docs/INTEGRATION.md`. Drawing there needs a Panels+ build with Ink Away support; the current stable Panels+ doesn't have it yet.
- **Labels for highlight colours**: say what each colour means to you. Use Labels in the highlight colour sheet (#81).
- **Notebooks reopen on the page you left**, imported PDFs included.

**Changed**
- Make room: the box snaps to the nearest place a room can start as you draw or move it. In books given their first room from this version on, an inline element such as italics is one more place it can start.

**Boox**
- Ink Away finds the firmware's pen layer on more firmware (it lives on `ViewUpdateHelper` on the Note X3 Pro), and pages no longer freeze after writing. By lisontowind (#82). The Boox then draws the pen's ink itself while you write. This needs a KOReader nightly and Palm rejection on.
- Fast refresh while drawing asks the panel about six times a second instead of up to 25, which piled up and left the ink behind the pen.
- After the pen rests, only what changed is redrawn, not the whole page.
- Test pen and touch now says whether the pen layer was found, why not, and which pen calls the firmware has. A photo of it helps a lot if you report a problem.

**Fixed**
- Ink on the right-hand page of a two-page view (the MuPDFtwoPages plugin) no longer disappears when you leave the pages.
- Connecting Google Drive on an Android phone or tablet no longer fails with "No connection" (IA-S101) after you allow it in the phone's browser.
- With a colour theme, the active tool and icons on coloured buttons no longer show as a pale square on some KOReader versions.
- Colour swatches and pen tiles no longer cover the corners of their black ring.
- Make room no longer says it "could not make room there" when only page numbers changed.
- The sticker sheet turns its pages with the page turn buttons (#79).
- With the Paper Dots plugin set to show only on the page, its texture stays while annotating.
- A comic book is no longer offered the editable PDF export.
- On a reader with a D-pad, tapping a text field in a sheet no longer fails.

Tested in the desktop emulator; on-device testing is still going on. If something misbehaves on your reader, please open an issue.

# v4.4.2 · 2026-11-07

**This is a prerelease.** To get it from inside Ink Away, turn on Settings, Updates, "Tell me about prereleases", then install it from there. Or download `ink-away.koplugin-v4.4.2.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder. You can go back to the latest release from Settings, Updates at any time.

Everything in 4.4.1, plus two Make room fixes:
- A sticker given the book's first room stays in one piece (its parts came apart when the book loaded again).
- "Rooms in this book" lists a room across the page as a band, not as space on the right.

# v4.4.1 · 2026-11-07

**This is a prerelease.** To get it from inside Ink Away, turn on Settings, Updates, "Tell me about prereleases", then install it from there. Or download `ink-away.koplugin-v4.4.1.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder. You can go back to the latest release from Settings, Updates at any time.

## New
- Cloud sync with Dropbox or Google Drive (Library, ⋯, Cloud sync): notebooks, book notes, ink on books, pens and more, kept the same on all your readers.
- Boox: the firmware draws the pen's ink while you write (#37). Pen and input, "Draw with Boox's pen layer" turns it off.
- Android: lighter screen updates while drawing. Pen and input, "Lighter screen updates" turns it off.
- Handwritten notes on highlights (#77).
- Make room in a book's text for stickers, pictures and notes.
- Stickers, pin a selection to its page, copy part of a page, and tap a highlight to change its colour.
- An Ink Away icon in KOReader's top menu bar, and Settings in four tabs.

Cloud sync and the Boox pen layer could only be tested in the emulator, so reports with your device's name are very welcome.

# v4.2.2 · 2026-10-19

**This is a prerelease.** To get it from inside Ink Away, turn on Settings, Updates, "Tell me about prereleases", then install it from there. Or download `ink-away.koplugin-v4.2.2.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder. You can go back to the latest release from Settings, Updates at any time.

Send your notebooks to a phone or computer over Wi-Fi, highlight while reading with the pen's side button, a fix for Kobo pen buttons, and every menu and dialog in Ink Away's own style. A prerelease, as the pen and Wi-Fi parts could only be tested in the emulator: reports from Kobo, Kindle Scribe and other pen readers are very welcome.

## Added
- Phone or computer (Wi-Fi). In the library's ⋯ menu: a QR code to scan with a phone or computer on the same Wi-Fi opens a page served by the reader itself, with no account and no internet. It lists your folders, notebooks, drawings and pictures, and gets any of them as a PDF, a PNG or an Ink Away file, with a progress bar and Cancel on both sides. Only Ink Away's own folders can be reached, and sharing stops when you close it or after 15 minutes of nothing happening. On a Kindle the firewall is opened for it and closed again after.
- Add files from your phone or computer: turn on Allow adding files and send PDFs, pictures and Ink Away files from the page. They arrive in Library › Imported, each kind in its own folder: PDFs become notebooks you can write on, then Pictures, and Notebooks and drawings. Ink Away can ask to open a notebook as soon as it arrives.
- The page on the phone takes your theme colour (Ink Away green on a grey reader).
- Pictures in the library: the pictures you sent show in the library, where they can be viewed, renamed, moved and deleted. Imported and its folders open like any other folder.
- Add image has Sent from your phone (the pictures in Imported › Pictures) and Get from your phone or computer (the QR code).
- Highlight while reading with the pen's side button (part of #39): no need to open the annotation mode. Hold the pen's side button and run the pen over a line of text: it becomes the reader's own highlight, made by the same smart highlighter. It uses whichever part of the pen is set to Highlighter in Gestures and pen buttons. Without the button the pen turns pages and selects text as before. It can be turned off in the reader's menu, Tools, Ink Away.
- The eraser shows its size and shape (#43): the Eraser sheet shows it at its real size on screen, and while erasing a ring shows exactly what it will clear. It is gone as soon as the pen lifts.

## Changed
- Every menu and dialog is now in Ink Away's style: messages, questions, typing a name, the lists of templates and notebooks, the arrowhead size and the progress of an export. Picking a picture, a PDF or a folder is a grid with picture thumbnails. Short notes like "Nothing to undo" show at the top of the screen and never get in the way of the pen.
- Holding a card in the library or a tab in the overview opens a sheet with icons instead of a plain list.
- The main buttons in Add image, Settings, File, the page menu, Layers, the pen menu and Export have icons.
- The library bar has one + New button (drawing, notebook or folder) instead of three, so a folder's full name fits next to it.
- The library's ⋯ menu is a sheet, with a line under each choice saying what it does.
- Covers on Bookshelf moved from Settings to the cover sheet itself (a long press on a notebook on the shelf): Use for new notebooks.
- Shorter, one-line explanations in Add image and on the QR code sheet.

## Fixed
- Kobo pen buttons did nothing (#13): with palm rejection off (the default on a Kobo), the eraser end and the side button drew like the tip, even though Test pen and touch saw them. They now do what Gestures and pen buttons says with palm rejection on or off.
- Choosing an action for the side button no longer mentions a "Second side button" that Kobo pens don't have.
- A new drawing, notebook, copy or folder made while looking at Imported (or from an imported notebook) went into Imported; it now goes in the library, as Imported only holds what you sent.
- After picking a picture from Sent from your phone, the top of that grid stayed over the toolbar.

- Drawing on the first Kobo Elipsa is much faster: the pen now uses its handwriting mode (#45, thanks to maks, #48).

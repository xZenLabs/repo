# v4.5.3 · 2026-11-25

A fix for big notebooks that would no longer open, plus night mode, Kobo and Simplified Chinese. If a notebook of yours showed "main function has more than 65536 constants", update and it opens again, with nothing lost.

### Added

- **Ink Away in Simplified Chinese**, by gytwo (#88).

### Changed

- **Ink Away's controls follow KOReader's night mode** by default (Appearance: System), so they go dark with the rest of KOReader. Light and Dark still keep the look you chose (#89).

### Fixed

- **Big notebooks open again, and there is no size limit anymore** (#92). A notebook of some 70 pages of handwriting could stop opening with "main function has more than 65536 constants": Ink Away keeps a notebook as one file of Lua tables, and LuaJIT only reads a file with fewer than 65,536 tables and texts in one piece. Such a notebook now opens as it is, with every page and stroke, and big notebooks, drawings and book ink are saved in parts that any Ink Away version reads, so pages and strokes have no limit. Small files are written exactly as before.
- **On a Kobo, pictures put on a book no longer show up as books** in Kobo's own library. Your own stickers, inserted pictures and screen clips are kept in the book's KOReader folder, which Kobo looks through. They are now kept under a name Kobo doesn't read as a picture. Pictures from earlier versions are renamed the next time their book is opened, and Kobo drops them from its library the next time it looks (at a USB connection). The annotations stay exactly as they were.
- **In night mode, colours in Ink Away's menus show as themselves.** A yellow sticker in the sticker sheet looked blue, and rounded buttons such as Done had square corners. Sticker and picture previews, swatches, pen samples and the theme colour now look right in every look (#89).

**Install:** download `ink-away.koplugin-v4.5.3.zip` below, unzip it, and copy the `ink-away.koplugin` folder into KOReader's `plugins` folder, replacing the old one. Or update from inside Ink Away: Settings, Updates. Guide: https://ink-away-docs.vercel.app

**Full changelog:** https://github.com/EmirErtorer/ink-away.koplugin/compare/v4.5.2...v4.5.3

# v4.5.2 · 2026-11-16


### Added

- **Your notebooks and drawings on SolarUI's shelf.** Ink Away now keeps the pictures of your notebooks and drawings for any home screen that asks for them, not only Bookshelf, so SolarUI's notebook shelf shows them in its own covers and opens each one on the page you left. Bookshelf keeps working as before.

# v4.5.1 · 2026-11-16

A hotfix for exact-line rooms on KOReader 2026.07 and older.

### Fixed
- A book could stop opening after its first exact-line room, on KOReader 2026.07 and older or with a book first opened before August 2026 ("invalid order function for sorting"). Places of both styles now move, a book already caught opens again with its highlights back where they were, and a highlight that points at nothing can no longer stop any book opening on an older KOReader.

Full changelog: https://github.com/EmirErtorer/ink-away.koplugin/blob/main/CHANGELOG.md

# v4.5.0 · 2026-11-14

Ink Away 4.5.0 is the stable release of everything since 4.4.0: the 4.4.1 to 4.4.4 test builds, now tested on readers, plus rooms on any line, a quicker way to Make room and a folder path in the library. The big ones are cloud sync, Make room in a book's text, stickers, handwritten notes on highlights and the Boox pen layer.

With work by Kristan Laimon (the integration API for viewer plugins, and fixes), Xinjie (lisontowind, the Boox Note X3 Pro), SimeDev42 (screen clips), jebbster88 (the panning map) and Sebas Moran (the pen plugin note). Thank you all.

Highlights:
- **Cloud sync with Dropbox or Google Drive.** Connect on the reader with a QR code and your phone. Choose what to sync (notebooks and drawings, book notes, ink on books, imported PDFs and pictures, exports, screen clips, your pens and preferences) and when (after closing a notebook, after a pause, on a timer, on sleep, or Sync now). It never loses work: backups for 30 days, conflicts kept twice, deletions never win over edits, earlier versions can come back, and every problem has a code that says what to do. Automatic syncing can cost battery, so the sheets say so and Manual only turns it all off. Notebooks made on another reader keep their page size.
- **Make room in a book's text.** Draw a box and the text moves out of it, to the pixel, without changing the font, for stickers, pictures and notes. Anything selected has Make room in its menu too. Rooms keep their size at any font or Zoom, what is in them follows when the text moves, and the book's file is never changed. EPUB and other reflowing books.
- **Exact lines** (an option in the Lasso's sheet): a room can start on any line, not only at a paragraph, using a private copy of the book in Ink Away's cache. Your book's file and its md5 stay as they are. Slower than ordinary rooms, as the book is loaded again when a room needs a new line.
- **The Lasso button holds Make room.** A small triangle in its corner; hold it to choose the Lasso or Make room, and the button keeps your pick.
- **Stickers:** post-its in many shapes and any colour, speech bubbles, marks, tape and your own pictures, with what you write on them moving along.
- **Handwritten notes on highlights:** pick Handwritten note in KOReader's highlight menu or in the colour sheet and write in a small window; the note lives in the book's notes and shows as a note in KOReader's lists.
- **Highlights:** tap one to change its colour, and give each colour a label ("Important", "Look this up").
- **Pin to this page:** a pinned item stays on its page number when the text reflows.
- **Screen clips:** copy part of a book page (Image tool, Clip the page, or a two-finger swipe) and paste it into a notebook. Old clips are cleared after a week, which you can change.
- **Boox pen layer:** the firmware draws the ink while the pen moves, as Boox's own notes app does, also on the Note X3 Pro. Android only sends the part of the screen that changed.
- **Ink Away in KOReader's top bar:** an icon with a quick menu for annotating, book notes, clips, the library and sync.
- **Two pages side by side** for PDFs, comics and other fixed-page books, with ink staying on its page.
- **Notebooks open on the page you left them on.**
- **Bookmark a page** with a long press on the page number at the bottom, with any tool in hand.
- **Library path:** the top bar shows Library › 2026 › November and you can tap any folder in it.
- **Settings in four short tabs**, so it never scrolls.
- **Panning on a colour reader** no longer lags: a small map shows where you are and the page is drawn when you stop.
- **Viewer plugins** such as PanelsPlus can let Ink Away draw on their view (experimental, see docs/INTEGRATION.md).
- Ink Away tells you when an old pen plugin has replaced KOReader's input.lua, and how to put it back.

Fixes:
- Kindle Scribe: finger taps no longer stop working or turn into undo after writing with the pen.
- Kindle: the grey of a book page around a black pen stroke no longer flickers black or white while you draw.
- Boox: Fast refresh no longer leaves the ink behind the pen, only what changed is redrawn after the pen rests, and the Note X3 Pro no longer freezes pages after writing.
- Ink on the right page of the MuPDFtwoPages view no longer disappears, and Paper Dots keeps its texture while annotating.
- Picture and folder pickers list hidden folders when KOReader shows them.
- Comic books export as pictures, not as an editable PDF, and text fields work on readers with a D-pad.
- Colour themes: no more pale squares on active icons, and no white corners on swatch rings.
- Fixed during the test builds: the "Preparing this book for rooms" note stuck on Kobo, a crash from a late cloud sync answer, Google Drive sign-in on Android, sync safety copies on Kindles, and several Make room and screen clip glitches. The full list is in CHANGELOG.md.

To update from inside Ink Away: Settings, Updates, Install. Or download `ink-away.koplugin-v4.5.0.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder.

# v4.4.0 · 2026-10-31

Ink Away 4.4.0 is the stable release of everything since 4.3.0. The big one is Export: your annotations now leave the reader as an editable PDF, a PDF of any book, or images. Plus Ink Away in ten languages, a toolbar you can move to the left or right, PDFs opened as notebooks from KOReader's own menus, and KOReader's gestures working inside Ink Away.

Highlights:
- **Editable PDF.** Annotate a PDF while you read, then export it: you get a copy of the original with your ink and highlights as real PDF annotations. The text stays selectable, the file stays about the size of the original, and any PDF viewer can edit or remove your annotations. Text boxes, pictures and fills can't be annotations, so Ink Away lists them first and either leaves them out or keeps the ink of just those pages as a picture over the page.
- **Any book as a PDF.** Export an EPUB, MOBI or other book you annotated as a fixed PDF, laid out as you read it now, with your ink, shapes and highlights where they are on the screen. The text sits under each page, so you can search, select and copy it. Export the pages with ink, a range or the whole book. Pages are pictures, so long books make big files.
- **Images.** Save pages as PNGs (the page you are on, the pages with ink or a range, one file each in a folder), or only your ink on white or transparent pages. A progress bar shows the way and Stop ends an export and deletes what it wrote. Find Export in Book ink settings, or under Tools, Ink Away.
- German, Greek, Spanish, French, Italian, Polish, Brazilian Portuguese, Portuguese, Russian and Turkish. Set KOReader to the language and restart. Spanish and the translation system are by Sebas Moran.
- Settings, Toolbar side: top, left or right on the canvas, for palms that kept hitting the toolbar.
- Long-press a PDF in KOReader's file browser, or open it and use Tools, Ink Away: Open as Ink Away notebook. New, From a PDF now uses KOReader's own file list, without the .sdr folders.
- KOReader's gestures (the light, a refresh, a screenshot) work inside Ink Away. Hold Back in the library to jump to the top folder.
- A small coffee button beside the dark mode button in Settings, for anyone who wants to say thanks.
- A highlighter over a page picture no longer covers the text under it in exports.

To update from inside Ink Away: Settings, Updates, Install. Or download `ink-away.koplugin-v4.4.0.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder.

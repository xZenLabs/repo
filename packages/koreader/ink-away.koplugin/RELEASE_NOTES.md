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

# v4.3.0 · 2026-10-24

Ink Away 4.3.0 is the stable release of everything since 4.2.0: the 4.2.1 and 4.2.2 prereleases, plus the pen's eraser end and side button while reading, Convert to text online, and fixes for the Kobo Elipsa, Elipsa 2E and Sage.

Highlights:
- Send notebooks and drawings to your phone or computer over Wi-Fi, and add PDFs and pictures from it, with a QR code and nothing to install.
- Highlight with the pen's side button and erase with its eraser end while reading, without opening the annotation mode.
- Convert to text online (experimental): read handwriting with your own AI service, and check and fix the text before it replaces the writing. Thanks to acidkill.
- Zoom and Pan buttons at the left or hidden, arrow buttons for long sheets like Settings, and every menu in Ink Away's style with icons.
- Faster drawing and erasing on the Kobo Elipsa (thanks to maks), Elipsa 2E and Sage, and Kobo pen buttons that work with palm rejection off.

To update from inside Ink Away: Settings, Updates, Install. Or download `ink-away.koplugin-v4.3.0.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder.

## Added
- Highlight while reading with the pen's side button (part of #39): hold it
  and run the pen over a line of text, and it becomes the reader's own
  highlight, made by the same smart highlighter, without opening the
  annotation mode. It uses the part of the pen set to Highlighter in Gestures
  and pen buttons; without it the pen turns pages and selects text as before.
  It can be turned off in the reader's menu, Tools, Ink Away.
- The pen's eraser end erases while reading, without opening the annotation
  mode: highlights and Ink Away's ink it runs over go. It can be switched off
  in the book's Ink Away menu (#59).
- The zoom and Pan buttons can sit at the left, out from under a resting
  right palm, or be hidden: Settings, Zoom and Pan buttons (#63).
- Convert to text online (experimental): Convert to text can use your own
  online service instead of reading on the reader. Switch it on in the Text
  tool's sheet and set the address, key and model; it is off by default.
  Thanks to acidkill (#61, #62).
- Convert to text shows what was read to check and fix before it replaces the
  writing; erased writing and hidden layers are no longer read.
- The eraser shows its size and shape (#43): the Eraser sheet shows it at its
  real size on screen, and Show the eraser while erasing (off by default, as
  e-ink leaves a trail of rings, #47) puts a ring under the pen.
- Phone or computer (Wi-Fi): get your notebooks and drawings onto a phone or
  computer, or add PDFs and pictures from one, with nothing to install. Open
  it from the library's menu, Export, or Add image; the reader shows a QR code
  and an address, and any phone or computer on the same Wi-Fi opens a page in
  its browser. The page lists your folders, documents and pictures, and gives
  each document as a PDF, a PNG (drawings) or its Ink Away file. PDFs and PNGs
  are made when you ask for them, a page at a time so the reader stays
  responsive, with progress and Cancel on both sides. The reader serves the
  page itself: nothing goes over the internet or through anyone's server. The
  address holds a secret that changes each time, and sharing stops when you
  close it, when the reader sleeps, when Wi-Fi goes, or after 15 minutes of
  nothing happening. The page takes Ink Away's theme colour (green on a reader
  without a colour screen).
- Adding files from the page, with "Allow adding files" on (on when opened
  from Add image, off otherwise, and switchable either way). Everything sent
  arrives in Library › Imported, each kind in its own folder: PDFs become
  notebooks you can write on in Imported › PDFs (the PDF itself is kept once),
  pictures go to Imported › Pictures, and Ink Away files to Imported ›
  Notebooks and drawings. The reader asks whether to open notebooks that
  arrive, saying where they are (notebooks arriving together share one
  question, and "Don't ask again" leaves a note). Pictures can be made smaller
  on the phone first (Original, Large, Medium or Small, showing how much
  smaller). Every file is checked by what it is, against size limits and the
  space left, and only kept once whole; an Ink Away file is read as data only
  and loses any reference to files elsewhere on the reader.
- Pictures in the library: JPEGs and PNGs in a library folder (Imported ›
  Pictures, for one) show as picture cards. Tap one to see it full screen;
  hold it to rename, move or delete it (deleted pictures wait in the trash).
- Add image has clearer choices: From this reader, Sent from your phone (the
  pictures in Imported › Pictures, as a grid), Get from your phone or computer
  (the QR code, ready to receive), Search online and Background.

## Changed
- Every menu and dialog is in Ink Away's style: messages, questions, typing a
  name, the lists of templates and notebooks, the arrowhead size and an
  export's progress. Picking a picture, a PDF or a folder is a grid with
  thumbnails, and short notes like "Nothing to undo" show at the top of the
  screen, out of the pen's way.
- Holding a card in the library or a tab in the overview opens a sheet with
  icons, and the main buttons of Add image, Settings, File, the page menu,
  Layers, the pen menu and Export have icons.
- The library bar has one + New button (drawing, notebook or folder) instead
  of three, so a folder's full name fits beside it.
- A sheet too tall for the screen, such as Settings, has arrow buttons above
  and below its scrollbar: a tap scrolls most of a screenful, where a drag on
  e-ink often moved a toggle or slider instead.
- The library's ⋯ menu is a sheet like the others, each option with a line
  saying what it does: Phone or computer (Wi-Fi), Write on a PDF from this
  reader, the order, and Trash.
- The cover style new notebooks get on Bookshelf is now set from a notebook's
  long press sheet ("Use for new notebooks", which was "Use for all") rather
  than in Settings.

## Fixed
- Kobo pen buttons did nothing with palm rejection off, the default on a Kobo
  (#13): the eraser end and the side button drew like the tip. They now do
  what Gestures and pen buttons says, with palm rejection on or off, and the
  side button's choices no longer mention a second side button Kobo pens
  don't have.
- Kobo Elipsa (the 2021 model): drawing keeps up with the pen and a finger. It
  trailed well behind, as each screen update held up the reader until the
  screen had taken it; now a helper makes the updates, with the screen's own
  handwriting mode on, as in Kobo's notebooks. Thanks to maks (#45, #48).
- The page turn buttons turn the pages of grids and sheets as well as the
  page: the library, folder icons, sent pictures, the guide, search, the trash
  and lists (#53). They did nothing there.
- Book notes after the Book notes folder (or a notes notebook) was renamed or
  moved in the library (#54): each book opens its own notes where they are now,
  instead of starting new ones in a new Book notes folder, and new books' notes
  go into the renamed folder. Notes left behind this way before are found again
  the next time their book opens them. Nothing in the notes themselves changes.
- Kobo Elipsa, Elipsa 2E and Sage: the eraser keeps up over a notebook's lines,
  a book or a picture (#47, #50). Each point asked the screen for its slower grey
  update, which held the eraser up; it now erases with the fast one, and the
  lines or picture under it show again as it lifts.
- Kobo Elipsa (the 2021 model): the highlighter and other see-through pens keep
  up with the pen too (#50). The helper that makes the screen updates now also
  makes the grey ones a stroke needs, so they no longer hold up the reader. A
  helper busy with a slow update is waited for instead of being given up, and
  after a failure the next stroke tries it again, so drawing no longer stays slow
  until Ink Away is reopened.
- A new drawing, notebook, copy or folder made while in Imported went into
  Imported; it goes in the library now, as Imported only holds what was sent.
- After picking a picture from Sent from your phone, the top of that grid
  stayed over the toolbar.

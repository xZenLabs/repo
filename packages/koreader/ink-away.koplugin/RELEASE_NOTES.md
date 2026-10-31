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

# v4.2.0 · 2026-10-16

Ink Away 4.2.0 is the stable release of everything since 4.0.1: the 4.1.0 and 4.1.1 prereleases, now tested on a Kobo Libra Colour and a Kindle Scribe, plus coloured library folders, typing on a physical keyboard and fixes for the book toolbar and the Scribe's pen.

Highlights:
- Notebooks and drawings on [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) shelves, with six notebook covers and twelve picture frames.
- Library folders in twelve colours, with an icon from your KOReader.
- Type into text boxes on a Bluetooth or USB keyboard.
- Text boxes at any angle, text and highlight colours, checklists, alignment and line spacing.
- The book toolbar can fit in the margin, the reader's page turn buttons work, and the eraser takes away highlights.
- Pen pressure as a Beta setting, and a long list of pen fixes for the Kindle Scribe, Kobo Libra Colour, Sage and Elipsa, and Android readers.

To update from inside Ink Away: Settings, Updates, Install. Or download `ink-away.koplugin-v4.2.0.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder.

## Added
- Library folders in colour: hold a folder for Colour and icon, then pick one
  of twelve colours and, if you like, an icon for its front. The icons are
  the ones in your KOReader: its own, Ink Away's, and any SVG or PNG you put
  in the koreader/icons folder. The look is kept in the library, so updates
  leave it alone, and each folder is drawn once, so the library opens as fast
  as before. Renamed and moved folders keep their look.
- Typing on a physical keyboard: a Bluetooth or USB keyboard that KOReader has
  set up types into text boxes, with Shift, Caps Lock, Backspace, Delete, the
  arrows, Home and End, Enter for a new line and Esc to finish the box. Ctrl+Z
  and Ctrl+Y undo and redo, Ctrl+A selects all and Ctrl+C, Ctrl+X and Ctrl+V
  copy, cut and paste. When KOReader counts the keyboard, the on-screen one
  stays away, as in KOReader's own text fields.
- Go to the contents page: in the page menu of a notebook that has one, and
  as an action for any gesture or page turn button, with Back to return.
  The guide now says how links are followed: a tap with Pan, or with a
  finger while palm rejection is on, on ink, shapes and pictures alike.
- On colour screens ink keeps its colour in KOReader's night mode: blue
  stays blue instead of turning yellow, and dark ink turns light so it reads
  on the dark page. Keep colours in night mode in Settings turns it off.
- In annotation mode the eraser takes away the highlights it crosses, as it
  does ink, in one undo step with whatever ink it cut. A long press on a
  highlight (with a finger while palm rejection is on, or with the lasso)
  offers to remove it. Until now a highlight could only go from KOReader's
  own menu once Ink Away was closed.
- The reader's page turn buttons work in Ink Away: they turn a notebook's
  pages, and the book's in annotation mode, where they did nothing before.
  Gestures and pen buttons can give them another action.
- Refresh the screen by hand: a long two-finger swipe down redraws the whole
  screen with a full refresh, so anything a quick refresh missed shows and
  the faint marks of fast drawing go. Any gesture can be set to it in
  Gestures and pen buttons, and Settings has a Refresh the screen button,
  in annotation mode too.
- The first time a finger drags on the page with palm rejection on, a note
  says why it doesn't draw: the pen draws and a finger moves the page, and
  palm rejection is in the pen menu, Pen and input. It shows once.
- Notebooks on a Bookshelf shelf. With the Bookshelf plugin installed, a
  shelf can show "Ink Away notebooks": a new shelf shows every notebook's
  cover front facing, and a tap opens it in Ink Away. Without Bookshelf
  nothing changes.
- Six cover styles for the shelf: Front page (the notebook's first page, with
  a spiral and its name on a coloured band), Hardcover, Composition book,
  Reporter pad, Kraft with window and Legal pad. The first time, your
  notebooks get a mix of all six, so you see what there is. A long press on a
  notebook on the shelf picks its style and colour, which follows its tab
  colour until you pick another; "Cover on the shelf" in a notebook's menu in
  the library does the same, and "Covers on Bookshelf" in Ink Away's settings
  sets the style new notebooks start with. A notebook keeps its cover through
  renames, moves and the trash.
- Covers are quick and never draw your strokes again. The first page on a
  cover is a picture Ink Away keeps of it as you close the notebook or turn
  from that page, only when it changed; writing on any other page leaves the
  cover alone. A notebook not opened since has its first page drawn once in
  the background, small and only while no notebook or book is open. The long
  press sheet opens at once, also for a notebook with smudges.
- Drawings on a Bookshelf shelf. A shelf can show "Ink Away drawings": each
  drawing hangs face out in a frame, and a tap opens it in Ink Away. There
  are twelve frames, from old to modern: Gilded Baroque, Louis XVI, Dutch
  Ripple, Carved Victorian, Arts and Crafts, Art Deco, Museum Mat, Floating
  Frame, Minimal Metal, Painted Box, Canvas Wrap and Instant Photo, each in a
  few finishes (gold, antique gold or silver gilt, oak or walnut, and so on).
  A new drawing gets a frame and finish at random, all twelve before any
  comes again. A long press on a drawing on the shelf picks its frame and
  finish, as does "Frame on the shelf" in a drawing's menu in the library.
  A drawing keeps its frame through renames and moves.
- The frames are as quick as the notebooks' covers: each was carved and lit
  once ahead of time and comes as small pieces that are fitted round the
  drawing, so a cover takes moments and the frame fits any drawing's shape.
  The drawing on a cover is a picture Ink Away keeps as you close it, only
  when it changed. With Bookshelf's "True cover aspect" on, the frame hugs
  the drawing in its own shape; with it off (Bookshelf's default, which shows
  every cover 2:3) the drawing fills a 2:3 frame, trimmed a little at its
  sides, so it is never stretched.
- Text boxes turn to any angle. While a box is open, drag the ring on the stem
  above it round its middle; it snaps to quarter turns. A box picked out with
  a hold or the lasso turns with the selection's handle and its quarter turn
  button too. A turned box is edited turned, with the caret, selection and
  grips following its lines, and pages, thumbnails and exports show it the
  same. The eraser and taps find it where it is drawn.
- Text colours. On a colour screen a word or a selection can be coloured
  (black, two greys, red, orange, green, blue, purple and up to three colours
  of your own from the colour wheel); a grey screen offers the greys.
- Highlight colours. Text highlights come in yellow (the default, which
  highlights made before take too), orange, blue, green and pink, plus up to
  three of your own; hold one you added to remove it. A grey screen keeps
  its grey, and on a dark paper a highlight is toned down so white letters
  read on it. Exports show the colours as the screen does.
- The Format sheet has tabs: Text (styles, size, colour, highlight and Plain
  to clear them), Paragraph (alignment, lists, line spacing, direction and the
  font) and Edit (copy, cut, paste, select all and today's date).
- Alignment: left, centre or right, for each box.
- Line spacing: tight, normal or loose, for each box.
- Reads down and Reads up turn a box on end, for a book's margins: a new box
  stands where it was tapped, an older one where it shows, and a line too
  long for the page there is shortened.
- The book annotation toolbar can fit in the book's margin: "Fit the toolbar
  in the margin" in Book ink settings (off by default) makes it as wide as
  the margin on its side, with its icons sized to it, so it stays clear of the
  text. It stays thick enough to tap, so a narrow margin needs widening in the
  reader's settings; PDFs and comics keep the usual toolbar.
- Checklists: a list with a box before each line. Tap a box to tick it, with
  the text open or closed (one undo step); a ticked item greys out.
- A second tap on a word in the text being written selects it, and the
  keyboard stays to type over it.

## Changed
- Pen pressure is now "Pen pressure (Beta)" in Pen and input, and starts off,
  also on readers that had it on. It shows on readers with a pen: the Kindle
  Scribe and the Kobo Elipsa, Sage, Elipsa 2E and Libra Colour. Another reader
  shows it once Ink Away has seen a pen on it. It works with Palm rejection
  on. While it is off the pen's pressure is not read at all: Pencil and
  Calligraphy keep an even width, and Ballpoint and Fountain follow your
  writing speed, as they do with a finger.
- The Format sheet stays open while you pick options, so several can follow
  one another; Done, Format or a tap outside brings the keyboard back. The
  font can be changed there too, so it is at hand over a book while writing.
- A text box's grips are sized for a finger: about 9 mm to hit on any reader,
  just outside its corners so a tap near a letter still places the caret, and
  always whole on the screen. Dragging the band around the frame moves the box
  too.
- A tap away from a text box only closes it. It used to start a new box where
  you tapped and bring the keyboard straight back; a tap on another box still
  opens that one.

## Fixed
- Over a book with the toolbar along the bottom, a tool's settings opened at
  the top of the screen. They now open just above the toolbar, as they open
  beside it on the other sides.
- On the Kindle Scribe a resting palm took the pen again once a book had been
  opened, until KOReader was restarted: the pen stopped being recognised near
  the hand and drew stray lines. Opening a book, the reader sleeping or some
  popups pause KOReader's input, and after that Ink Away no longer kept the pen
  and the palm apart. It now does, whatever came before.
- On KOReader 2026.07.1 and later, a touch panel that also reports a resting
  hand as a single point can no longer move or lift the pen.
- A page with smudges could take ten times longer to open after an export or
  after Bookshelf covers were drawn: the smudge's drawing was left running
  slowly. It now runs at full speed whatever was drawn before.
- With "Fit the toolbar in the margin" on, the book's toolbar ended right
  where the text began. It now leaves a little space before the text.
- With the screen turned upside down (a Kobo Libra Colour held with its
  buttons on the left, for one) the page under Ink Away was dark: strokes
  showed as white boxes and the eraser drew white, over a book and in
  drawings alike. The page shows as it does the right way up.
- A page added to a book's notes named the notebook in the strip above it
  instead of its chapter, so it looked like another notebook had opened. It
  names the chapter it belongs to now.
- Opening a book's notes in a new chapter, adding a page and writing only on
  that one moved the notes to the chapter before when the notes closed, and
  the chapter opened on an empty page the next time. The chapter's page now
  stays when a page after it has notes, and goes with the empty pages after
  it when they are all left empty.
- On a pen reader a tap with the lasso did nothing (or said "Nothing inside
  the loop"), so what was cut or copied could not be pasted and a picture,
  shape or text box could not be picked out with a tap. A tap with the pen
  now does what a finger's tap does.
- A tool menu dragged out of the way went back to where it opens as soon as
  an option was picked in it, and a menu opened from it (Pen type, the colour
  wheel, a font) opened in the usual place too. Both now stay where the menu
  was dragged, kept whole on the screen; a menu opened later starts in its
  usual place.
- Over a book, Pen after the highlighter and another tool (the eraser, say)
  gave the highlighter back. It gives back the pen you had before the
  highlighter.
- On Android readers (a Boox, for one) "Nothing to undo" could start showing
  on every tap, with a finger or the pen, until Ink Away was closed. When the
  system took a touch away in the middle of a stroke, Ink Away later handed
  KOReader a finger that was no longer there, so every tap after it read as a
  two finger tap, which is Undo. A touch the system takes away now goes for
  Ink Away too.
- A shape being dragged out with a lowered opacity, or in a pale colour,
  showed a broken outline or none at all until a menu opened: the quick
  refresh that keeps the outline up with the pen shows only black and white.
  The outline is now drawn in the page's ink while it is dragged, and the
  shape takes its colour and opacity when it is placed.
- On colour e-ink a grey pen did not show while writing: the quick refresh
  used for live ink shows only black and white, and a grey has no colour to
  show. It now writes in the page's ink and turns grey when the pen lifts, as
  every pen does with "Colour while drawing" off, which on a dark paper now
  writes in white instead of black.
- Ballpoint and Fountain lines no longer turn thin when the pen lifts. A
  straight stroke is kept as its two ends, and its tapered ends' thinness was
  drawn all along it on the page, in thumbnails and in exports, so the width
  you pressed disappeared. Notes written before show at their proper width.
- Each lift of the pen drew the whole stroke again from its saved copy with
  the Ballpoint, Fountain and Calligraphy, and with the Pencil when pressure
  was on, which could make writing lag on a Kindle Scribe (with the Pencil it
  took about twenty times the rest of the lift). A lift now draws only what it
  changes: the thinning end of a Ballpoint or Fountain stroke, and nothing for
  the others. That end now shows on the screen at once; it often waited for
  the page's next full redraw before. A page full of Ballpoint or Fountain
  writing draws faster too.
- On a Kindle Scribe the ink could fall seconds behind the pen, and letters
  written quickly came out straightened. Ink Away asked the screen for a
  refresh at every point the pen reported, more than the Scribe's display can
  show, so the requests queued up. The live ink is now shown at a steady pace
  of up to fifty refreshes a second, as on colour readers.
- On a Kobo Sage or Elipsa the ink showed as scattered dots and dashes while
  writing, and the whole strokes only appeared when the screen was redrawn
  (closing the toolbar, say). Their display drops many of the tiny updates
  sent at every point of the pen. The live ink is now shown at a steady pace
  there too, and each stroke is shown whole once more as the pen lifts. Black
  ink is shown then in the same quick mode it was drawn with, so the screen is
  free sooner for the next letter.
- Closing Ink Away took the pen away from whatever had it before: another
  plugin that draws with the pen lost it until it was opened again, and with
  two Ink Away windows open (a book's notes and its annotation), closing one
  left the other without palm rejection, so the hand drew lines. Closing a
  window now gives the pen back to the one under it, or to the plugin that
  had it.
- On a Kobo the pen's eraser end highlighted and its side button did nothing,
  whatever Gestures and pen buttons said: Ink Away read a Kobo pen's buttons
  as a Kindle Scribe's. The eraser end now erases and the side button
  highlights, each as set in Gestures and pen buttons, also with
  pencil.koplugin's input.lua installed. The setting for a second side
  button is gone, as no Kobo or Kindle pen has one.
- On a Kindle Scribe with pencil.koplugin's input.lua installed, the pen's
  side button did nothing. It does what Gestures and pen buttons says again.
- On Android readers (a Boox, for one) the pen's eraser end was ignored until
  the pen had drawn once, taken for a resting hand. It erases from the first
  touch now, with KOReader 2026.08 or later. The pen's side button still
  can't work there: KOReader doesn't pass it on to plugins on Android.
- On colour e-ink (Kobo Libra Colour and others) a shape being dragged out no
  longer falls behind the pen. Each move asked the screen to redraw the whole
  shape's box, and the screen queued every one of them; now each new outline
  waits for the last to show, so it stays with the pen at any size.
- On a Kindle Scribe a hand resting on the screen could draw lines, or keep the
  pen from drawing, until a stroke or two were written with the hand lifted.
  When the touch screen took the edge of the hand for a pen, Ink Away took it
  for the real pen. Only the pen's own digitizer is the pen now, and a hand on
  the screen while the side button is held is never taken for it either.
- A pen stroke that starts on a floating button (zoom, Pan, the toolbar's
  chevron, the pen or layer strip) is drawn instead of lost. A pen that lifts
  within about 1.3 mm of where it landed, and within KOReader's hold time,
  still presses the button.
- On colour e-ink, moving, resizing or turning a text box and dragging out the
  export area keep up with the finger, as shapes now do: each refresh waits
  for the panel to show the last.
- With "Erase whole strokes" on, the eraser takes a text box it touches unless
  text is protected, and a picture when "Erase pictures" is on. It used to
  leave both alone whatever the settings said. As with a filled shape, rubbing
  out writing on top of one keeps it. "Protect text from eraser" is in the
  Eraser's sheet now as well as the Text sheet.

Full changelog: https://github.com/EmirErtorer/ink-away.koplugin/blob/main/CHANGELOG.md

# v4.0.1 · 2026-10-10

**Updating:** on 4.0.0, open Settings, Updates in Ink Away and install it from there. On 3.3.0 or older, download `ink-away.koplugin-v4.0.1.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder, as before.

Two fixes for pen and colour readers.

## Fixed
- With palm rejection on (the default on pen readers), a text box's Done and
  Format buttons answered neither the pen nor a finger, so the keyboard could
  not be closed. Both work now, and a finger tapping away closes the box.
- Colour ink on colour e-ink settles to its true colour once the pen rests.
  Pale colours such as pink could stay invisible, and blue could stay cyan,
  until something else redrew the page.

# v4.0.0 · 2026-10-10

**Updating from 3.3.0 or older:** download `ink-away.koplugin-v4.0.0.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder, as before. From 4.0.0 on, Ink Away can update itself: Settings, Updates.

The biggest update yet: write on your books, a whole new set of pens, layers,
dark mode, paper colours, a guide and updates from inside Ink Away.

## Added

#### Write on your books
- Annotate any book KOReader opens (EPUB, MOBI, FB2, PDF, DjVu, CBZ and more):
  pen, eraser, shapes, text and pictures right on the page.
- Ink follows the text: on a reflowing book each stroke is anchored to the words
  it was written beside, so it stays with them when you change the font size,
  margins or orientation. On PDFs and comics it keeps its place on the page.
- Smart highlighter: a highlighter stroke over text becomes KOReader's own
  highlight, in the pen's colour, and shows in your highlights list. Strokes that
  run into the margin, wobble or cross lines still snap; over empty space it
  stays ink.
- Book notes: a notebook for each book, with a page per chapter, in a window
  over the page that expands to full screen.
- The annotation toolbar can sit on any side of the screen and folds away.
- Erasing over a book cuts strokes where you rub; "Erase whole strokes" brings
  the old eraser back.
- Annotations live beside the book's own KOReader data and follow the book when
  it is moved or renamed. KOReader's Reset keeps them; deleting a book, or
  "Delete all annotations on this book", puts them in the trash for 30 days.
- The book gestures are set up for you (swipe up or down the right edge, or
  two-finger swipes when those are taken), with a notice saying which you got.

#### Pens
- Pen pressure on pen readers (Kindle Scribe, Kobo stylus): the line follows
  how hard you press. Switch it in Pen and input.
- New pens: Ballpoint, Fountain and Calligraphy (with its own nib angle).
- See-through pens that blend with the page: Highlighter (text stays black on
  top), Marker and Watercolor.
- Smudge, which moves ink (and only ink) and mixes colours the way paint does.
- A compact pen case: up to 20 saved pens, each shown at its real size, "+" for
  a new pen of any kind, and hold to move, copy or remove one. New readers start
  with Fineliner, Ballpoint, Pencil, Calligraphy, Highlighter, Watercolor and
  Smudge.
- A floating pen strip with your first saved pens, and the pen's colour under
  the Pen button.

#### Layers
- Drawings can be drawn in layers, up to five. File, Layers turns them on, and
  what is drawn so far becomes the first layer.
- A small strip at the right, shown only while layers are on, adds a layer and
  picks the one to draw on; tap that one to show or hide it, rename, move,
  merge down or delete it. Turning layers off merges them into one drawing.
- Only the layer you draw on is touched: the lasso, both erasers and the paint
  bucket leave the others alone, and the eraser shows the layers under it as
  it goes. A stroke under other layers stays under them while it is drawn.
- Hidden layers are left out of exports and thumbnails.
- No layer is kept as a picture of its own, so drawing stays as fast as on a
  plain page.

#### Gestures and pen buttons
- Choose what each gesture and pen button does, from one list of actions, with
  a warning when two would clash.
- By default, holding the pen's side button turns it into a highlighter.

#### Look
- Dark mode for Ink Away's toolbars, menus and library: Light, Dark or
  following KOReader's night mode. Your page and colours are never changed.
- Paper colours: twelve papers on colour screens (cream, sandpaper, legal pad,
  kraft, blueprint, chalkboard and more) and white or black on grey ones. The
  ruling and grid take the paper's shade so they always show, black ink and text
  turn white on a dark paper, and exports come out on the same paper.

#### Help
- A guide: short cards on what a glance doesn't show, by topic, each with
  "Show me".
- A notice the first time Ink Away opens, with the book gestures you got.
- Test pen and touch, in Settings: shows how your pen, its buttons and your hand
  arrive, handy for bug reports.
- Check for updates: Settings, Updates shows the latest release and, apart from
  it, any newer prerelease, with their notes, and installs them after checking
  the download. Once a day, only on Wi-Fi that is already on, Ink Away looks by
  itself and puts a dot on the Settings button when there is something new. You
  can always go from a prerelease back to the latest release, never to an older
  one.

#### Android and Boox
- On a Boox, Ink Away asks the screen for its fast refresh while you draw.
- On Android readers whose pen KOReader still reports as a finger (before
  KOReader 2026.08), the pen draws again instead of scrolling the page, and a
  tip explains slow drawing on readers that need a setting changed.

## Changed
- Settings are tidier: pen settings live in Pen and input, every setting is in
  one place, and Settings fits a Paperwhite without scrolling.
- Watercolor is smoother and three times faster.
- See-through pens on grey e-ink refresh only what changed as you draw.

## Removed
- Acrylic and Stipple are no longer in the pen picker (drawings that use them
  still show them).

## Fixed
- A stroke ends exactly where the pen lifted (it could stop short).
- A quick drag on a slider no longer moves the whole menu.

## For developers
- The code passes luacheck, and the tests (about 3,800 checks, many on
  KOReader's real drawing, zip and network code) run on every push.

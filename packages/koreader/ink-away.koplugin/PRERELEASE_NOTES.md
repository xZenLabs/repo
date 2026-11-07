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

# v4.2.1 · 2026-10-18

**This is a prerelease.** To get it from inside Ink Away, turn on Settings, Updates, "Tell me about prereleases", then install it from there. Or download `ink-away.koplugin-v4.2.1.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder. You can go back to the latest release from Settings, Updates at any time.

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

# v4.1.1 · 2026-10-16

**This is a prerelease.** To get it from inside Ink Away, turn on Settings, Updates, "Tell me about prereleases", then install it from there. Or download `ink-away.koplugin-v4.1.1.zip` below and put the `ink-away.koplugin` folder in KOReader's plugins folder. You can go back to the latest release from Settings, Updates at any time.

Notebooks and drawings on Bookshelf shelves with drawings in twelve frames,
pen pressure as a setting that starts off and a round of pen and page fixes.
A prerelease, as the pen and colour fixes could only be tested in the
emulator: reports from pen and colour readers are very welcome.

## Added
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

## Changed
- Pen pressure is now "Pen pressure (Beta)" in Pen and input, and starts off,
  also on readers that had it on. It shows on readers with a pen: the Kindle
  Scribe and the Kobo Elipsa, Sage, Elipsa 2E and Libra Colour. Another reader
  shows it once Ink Away has seen a pen on it. It works with Palm rejection
  on. While it is off the pen's pressure is not read at all: Pencil and
  Calligraphy keep an even width, and Ballpoint and Fountain follow your
  writing speed, as they do with a finger.

## Fixed
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

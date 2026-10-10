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

# v3.3.0 · 2026-10-05

The biggest update so far: Ink Away is now a proper notebook app, with a library, a binder-style browser, search, a trash, links and a contents page, and handwriting you can turn into text on the device.

## Your notes, organized
- No more Save button: every drawing and notebook is its own file and saves itself as you go. The File menu has rename, duplicate, export and new.
- A library with folders (and folders inside folders), thumbnails and + Drawing / + Notebook / + Folder buttons. Rename, move, duplicate or delete without a computer.
- Browse: a folder's notebooks as colored tabs beside their pages, like a binder. Star pages, filter by stars, move or copy pages between notebooks.
- Search by name, or inside pages for typed text, converted handwriting included. Results are remembered, so the next search is instant.
- A trash: deleted notebooks, drawings, folders and pages wait 30 days and come back exactly where they were.
- Choose what Ink Away opens on: the last document, the library or your notebooks.
- Old drawing and notebook project folders move into the library on their own.

## Notebooks
- Pages can have titles, stars and their own paper.
- New papers with previews: blank, lined, grid, dotted, isometric, margin ruled and Cornell, plus planners (handwriting practice, checklist, two columns, storyboard, music, daily, weekly, week columns, monthly, meeting notes, habit tracker).
- Save a page as a template and start new pages from it.
- Links: link anything to a page in this or another notebook; tap to jump, Back to return.
- Contents page: built from your titled pages in one tap, every line a link, updated whenever you like.
- PDF export: titled pages become bookmarks, links keep working, and a whole folder can be exported as one PDF.
- Drawings can include their grid when exported.

## Writing and editing
- Convert to text: lasso printed handwriting and it becomes a text box, read by a small model on the device. Nothing is sent anywhere. English letters and digits for now.
- One selection for everything: lasso strokes, shapes, pictures and text, then move, resize, rotate, flip, duplicate, recolor or change opacity and thickness from one small menu. Cut, copy and paste across pages and notebooks.
- Hold to straighten: hold the pen still at the end of a stroke and a rough line, box, ellipse or triangle snaps clean. Writing is left alone. Replaces Shape assist.
- Eraser mode that removes whole strokes.
- A more forgiving lasso: overlapping ends, grazed writing, text and pictures are picked up.
- Lasso has its own toolbar button with a new icon; Pan is a round button above the zoom control (tap again to return to your tool).
- The pen can tap the toolbar and menus.

## Gestures
- Two-finger tap: undo. Two-finger double tap: redo.
- Two-finger swipe: turn pages. Long two-finger swipe up: open your notebooks (or the library from a drawing).
- Hold Prev or Next: jump to the first or last page.
- With palm rejection on, "Finger on the page" makes a finger navigate or do nothing while the pen writes.
- Zooming out stops at the page width.

## Color screens
- A theme color, Ink Away green by default, or black, a preset or any color.
- Color ink shows in color while you draw; a toggle brings back the black preview.
- Colored binder tabs.

## Faster, with fewer flashes
- Saving big notebooks about 90% faster (only changed pages are written).
- Closing a 120-page notebook practically instant; the page overview opens about a third faster.
- Drawing 12-28% faster per point.
- Page turns refresh only the page and the bar; a stroke is no longer refreshed again on lift.
- Fewer flashes in the library and browser, none on color screens.
- Dragging a selection follows the finger smoothly.
- Android (Boox and others): drawing, erasing, shapes, the lasso and panning no longer refresh the screen for every pen sample, which made writing slow there. Not yet tried on a real Boox, so feedback is welcome. Kindle and Kobo work as before.

## Fixes
- Undo puts a moved lasso selection back.
- Moving no longer picks up shapes you had erased.
- Long menus on small or landscape screens slide over the toolbar instead of scrolling.

## For developers
- The canvas, once one 11,500-line file, is now 27 feature files with shared helpers, so a feature can be changed or added in one small file. A good time to fork it.
- A test suite of around 2,300 automated checks (including pixel-exact tests on KOReader's real drawing code), performance benchmarks and an e-ink refresh audit. Tests are not part of the download.

# v3.2.0 · 2026-10-02

Everything since 3.1.0 in one stable release.

## New
- **Landscape mode.** Remembered between sessions, and exports come out landscape.
- **Paste and copy in text boxes.** Long-press for a Paste bubble; Copy / Cut / Paste in the format menu. Uses KOReader's clipboard.
- **Background remover** for images, plus refreshed text controls.

## Pen
- Small handwriting no longer turns into straight lines.
- Kindle Scribe: strokes no longer join up when your hand rests on the screen.
- Quick writing no longer connects neighbouring letters.

## PDF
- Exporting long PDFs no longer crashes. Pages are saved one at a time, with a progress bar you can stop.
- Faster page turns, with fewer flashes.

## Colour screens
- Much faster drawing: ink shows instantly in black and settles to colour when you pause. Coloured pens no longer slow down at larger sizes.

## Fixes and speed
- The eraser no longer removes notebook lines.
- Menus open around 40% faster, strokes draw with far less work, and landscape is as fast as portrait.
- Typing no longer zooms the page when you tap away, and a new text box no longer starts with a stray letter.
- Toolbar taps no longer lag after closing a menu.

# v3.1.0 · 2026-09-25

The big new thing this release: you can add pictures to your drawings.

## Add pictures to your canvas
- Open the image tool and either pick a file or search for a picture without leaving the app.
- Search runs on Wikimedia Commons by default (it's the quickest), with Openverse one tap away when you want a wider mix. No account or setup, and it only goes online when you actually search.
- Optional "transparent PNG only" filter, and a full-resolution toggle if you'd rather keep the original than a scaled-down copy.
- A picture you add drops in already selected, so you can move, resize, rotate or duplicate it straight away.

## Stylus
- The pen's side button now switches to lasso select, so you can grab and move things without going back to the toolbar.

## Save
- If you use the Bookshelf plugin, you can now save a drawing straight to your bookshelf ornaments as cover art.

## Fixes
- Smoother colour panel, more reliable palm rejection, and menus that no longer stick around after you close them.
- Fixed the notebook bottom-bar font.

# v3.0.0 · 2026-09-22

A big release: reliable palm rejection, a top-to-bottom redesign of the drawing interface, and a lot of work to keep everything fast.

## Palm rejection
Rest your hand on the screen while you write — only the pen marks the page.
- Enabled automatically on Kindle Scribe and reMarkable. On Kobo and other stylus readers you can switch it on in Pen Settings.
- Tells a real pen from a resting palm reliably, so no more stray lines drawn between your hand and the pen tip.
- The rear eraser and barrel button keep working as expected.

## Redesigned drawing interface
- Every tool menu in the toolbar has been reworked to be cleaner and easier to use.
- The canvas now runs edge to edge — every drawing and notebook page fills the full width of your screen, with no grey border.
- Hide the toolbar for a distraction-free, full-screen drawing experience.
- Zoom moved out of the toolbar into a floating control in the bottom-right corner. It fades away on its own when your pen gets close, so you can draw underneath it, and comes back afterwards.
- The Shapes menu was rebuilt with large, clear icons, a single Fill toggle, and the line, arrow and curve variants tucked into one place instead of a cluttered row of buttons.

## Faster and lighter
- The canvas no longer slows down as strokes pile up.
- Lower memory use for notebooks, quicker undo, and smoother panning and zooming.
- Memory is reclaimed when you start a new drawing or notebook, without needing a restart.

## Fixes
- Consistent notebook UI and a fix for a crash in Settings.
- Tool menus now update in place when you switch tools instead of flickering.

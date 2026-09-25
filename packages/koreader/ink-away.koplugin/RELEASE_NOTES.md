# v3.1.0

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

# v3.0.0

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

# v2.2.0

- Add images (as many as you want) with move, resize, rotate, flip, duplicate and send-to-front.
- Shape assist snaps rough strokes into clean lines, rectangles, circles and triangles that stay fully editable.
- Any shape can be tapped or held to move, rotate, flip, duplicate, recolour, resize or delete.
- Paint-bucket fill now sticks to its shape
- Faster shape and image dragging, no image-move flash, cleaner triangle snapping, and no black corner on free rotation.

# v2.1.1

Bug fix

Fixes toolbar icons appearing as danger/triangle placeholders on some devices (notably a first install on Kindle Scribe). The toolbar now loads its icons directly from the plugin instead of relying on KOReader's shared icon folder, which on a first run was not yet registered when KOReader looked for the icons. This was intermittent because it depended on whether that folder already existed from a previous run, which is why reinstalling appeared to fix it.

No other changes. If anything looks off with the toolbar, please comment.

# v2.1.0

Install by unzipping into your KOReader `plugins` folder.

## New: text notes
- Add text boxes anywhere on a drawing or notebook page and type with the on screen keyboard.
- Rich formatting on the word under the cursor or a selection: bold, italic, underline, strikethrough, highlight, larger or smaller size, and bullet or numbered lists.
- Font picker that previews every installed font in its own typeface, plus a default text size.
- Grid line snapping on ruled notebook pages and on the drawing grid: each line sits on the ruling, and the text size follows the line spacing so lines are never skipped.
- Word level undo and redo while editing, and word by word undo of a finished box.
- Long words wrap instead of overflowing, and the box grows to fit its text.
- Move and resize boxes, tap to place the caret, drag to select.
- Protect text from the eraser: optional toggle so the eraser clears ink but leaves your text, both on screen and in exports.
- Text saves in projects and exports to PNG, JPEG and PDF.

## Toolbar and notebook
- Redesigned toolbar with clean vector icons instead of text labels.
- New Redo button next to Undo.
- Notebook page strip now uses arrow buttons and a dedicated add page icon that tracks the page number width.
- Notebook ruling style, spacing and strength are remembered for the next notebook.

## Fixes
- Reopening a text box no longer shifts it down.
- Eraser and text now render the same on screen and in exported PDF and PNG.

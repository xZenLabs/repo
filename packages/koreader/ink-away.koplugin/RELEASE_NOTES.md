# v2.1.1

Bug fix prerelease.

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

# v2.0.1

A small stability update on top of 2.0.0

Fixes
- Shapes no longer get dropped or turned into a different shape when you switch tools or pick a new shape before the last one has fully registered. A shape you draw now always stays the shape you drew.
- Lasso select is steadier: shapes no longer vanish when you switch to it, the loop is more forgiving about what it picks up, and the extra popup after selecting is gone.

# v2.0.0

A big update built around a new notebook mode, plus a lasso tool and clearer file folders.

New
- Notebook mode: open a fresh multi page notebook, or open any PDF as a notebook and write on every page. Paper styles: lined, grid, dotted, margin and Cornell, with adjustable line size and strength.
- Get around fast: turn pages, tap the page number to jump to any page, or open a thumbnail overview grid to move around at a glance. Duplicate, reorder and delete pages.
- Export a notebook to a real paged PDF (white or warm sandpaper paper). Choose all pages, only the pages you wrote on, or a range, and optionally number the pages. Exporting also keeps an editable copy so nothing is a dead end.
- Lasso select, on the canvas and on notebook pages: draw a loop around ink, shapes or fills, then drag the whole group, duplicate it, or delete it.
- Tidier saving: separate folders for drawing images, drawing projects, notebook PDFs and notebook projects. Existing projects are sorted into the new folders once, safely, with nothing deleted. Saving a drawing also keeps an editable copy of the same name.
- Ink Away now sits at the top of the Tools menu.

# v1.4.0

Stable 1.4.0. Highlights since 1.2: symmetry mode (vertical, horizontal, four way), a brush maker for building your own brushes, open an image as a background and draw over it, arrows (straight or curved, single or double headed), export the whole page or a chosen area, adjustable grid strength, optional ghosting cleanup, and a smoother, faster experience throughout. New in 1.4.0: the eraser leaves the background picture alone by default, with a toggle in its menu to erase the background too. Colour: your ink now shows in colour on colour screens (it was drawing in grey before), and the pen menu gains a colour wheel for picking any colour, plus saveable custom colour swatches.

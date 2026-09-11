# v1.5.0

A big update built around a new notebook mode, plus a lasso tool and clearer file folders. This is a prerelease for testing on device.

New
- Notebook mode: open a fresh multi page notebook, or open any PDF as a notebook and write on every page. Paper styles: lined, grid, dotted, margin and Cornell, with adjustable line size and strength.
- Get around fast: turn pages, tap the page number to jump to any page, or open a thumbnail overview grid to move around at a glance. Duplicate, reorder and delete pages.
- Export a notebook to a real paged PDF (white or warm sandpaper paper). Choose all pages, only the pages you wrote on, or a range, and optionally number the pages. Exporting also keeps an editable copy so nothing is a dead end.
- Lasso select, on the canvas and on notebook pages: draw a loop around ink, shapes or fills, then drag the whole group, duplicate it, or delete it.
- Tidier saving: separate folders for drawing images, drawing projects, notebook PDFs and notebook projects. Existing projects are sorted into the new folders once, safely, with nothing deleted. Saving a drawing also keeps an editable copy of the same name.
- Ink Away now sits at the top of the Tools menu.

Please try the notebook flow and the lasso, and report anything that looks off"
cd "/Users/emirertorer/Documents/claude projects/ink-away.koplugin" && gh release create v1.5.0 dist/ink-away.koplugin-v1.5.0.zip --prerelease --title "Ink Away 1.5.0 (prerelease)" --notes "$(cat <<'EOF'
A big update built around a new notebook mode, plus a lasso tool and clearer file folders. This is a prerelease for testing on device.

New
- Notebook mode: open a fresh multi page notebook, or open any PDF as a notebook and write on every page. Paper styles: lined, grid, dotted, margin and Cornell, with adjustable line size and strength.
- Get around fast: turn pages, tap the page number to jump to any page, or open a thumbnail overview grid to move around at a glance. Duplicate, reorder and delete pages.
- Export a notebook to a real paged PDF (white or warm sandpaper paper). Choose all pages, only the pages you wrote on, or a range, and optionally number the pages. Exporting also keeps an editable copy so nothing is a dead end.
- Lasso select, on the canvas and on notebook pages: draw a loop around ink, shapes or fills, then drag the whole group, duplicate it, or delete it.
- Tidier saving: separate folders for drawing images, drawing projects, notebook PDFs and notebook projects. Existing projects are sorted into the new folders once, safely, with nothing deleted. Saving a drawing also keeps an editable copy of the same name.
- Ink Away now sits at the top of the Tools menu.

Please try the notebook flow and the lasso, and report anything that looks off.

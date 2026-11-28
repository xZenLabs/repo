# v3.1.0-beta.5 · 2026-11-28

### Beta Pre-Release: Safe TOC Chapter Lookup & Crash Fix

- **Fixed crash when exporting/indexing closed EPUBs with handwritten notes**: prevents KOReader's CReEngine (`libkoreader-cre.so`) from calling `getToc()` on an unrendered offscreen `CreDocument` during Index/Digest/batch exports.
- **In-memory TOC caching & XPointer lookup**: caches the live Table of Contents when closing a book so delayed auto-exports on close and subsequent exports resolve EPUB `DocFragment` chapters without re-opening documents, and opens closed fixed-layout PDFs at most once per session.
- **Includes all features from `v3.1.0-beta.4`**: direct TOC chapter lookup for InkAway & stylus notes (#52) and optional highlight color labels & custom aliases (#53, #54).

You can install or update directly in KOReader via **Tomedown > Settings > App & updates > Release channel > Beta > Check for beta updates**.

# v3.1.0-beta.4 · 2026-11-28

### Beta Pre-Release: Chapter Association for Handwritten Notes

- **Direct Table of Contents (TOC) chapter lookup for InkAway & stylus notes** (#52): handwritten notes on PDFs and EPUBs are now automatically grouped under their actual book chapters using KOReader's Table of Contents (live reader TOC, custom handmade TOC, or embedded document TOC when exporting closed books), even in chapters without any text highlights.
- **Reflowable EPUB & Book notes chapter alignment**: prioritizes XPointer document order (`DocFragment`) over shifted reflow page numbers and aligns InkAway `Book notes` chapter pages directly inside their matching chapter section.
- Includes all features from `v3.1.0-beta.3`: **InkAway handwritten notes support** (#52) and **optional highlight color labels & custom aliases** (#53, #54).

You can install or update directly in KOReader via **Tomedown > Settings > App & updates > Release channel > Beta > Check for beta updates**.

# v3.1.0-beta.3 · 2026-11-28

### Beta Pre-Release: Combined Build

This beta combines both community-requested features for testing:

- **InkAway handwritten notes support for PDF and EPUB** (#52): exports freehand strokes, shapes (lines, curves, rectangles, triangles, ellipses, polygons, arrows), RGB colors, highlighter opacity, text boxes, and linked `.inkaway` book/highlight notebooks into clean vector `.svg` files in `drawings/`.
- **Optional highlight color labels and custom aliases** (#53, #54): adds a **Highlight color** toggle (off by default) and **Color aliases** submenu under **Settings > Notes & highlights** (plus per-book override), appending the color name or custom alias to highlight metadata lines across book notes, `00 - Reading Digest.md`, and `.txt` exports.

You can install or update directly in KOReader via **Tomedown > Settings > App & updates > Release channel > Beta > Check for beta updates**.

# v3.1.0-beta.2 · 2026-11-27

### Beta Pre-Release: Optional Highlight Color Labels & Aliases (#53)

- **Highlight color toggle** (*Settings → Notes & highlights → Highlight color*, off by default): appends the highlight's color name (e.g. `- **p. 10** · 02/09/2026 · Yellow`) to each exported highlight's metadata line across book notes, `00 - Reading Digest.md`, and `.txt` exports.
- **Custom color aliases** (*Settings → Notes & highlights → Color aliases*): map any KOReader highlight color to a custom label (for example `Yellow → Key idea`, `Red → Disagree`).
- **Per-book override**: toggle highlight color labels per book under *Current book → Format & layout → Notes & highlights*.

You can install this beta directly in KOReader via **Tomedown → Settings → App & updates → Release channel → Beta → Check for beta updates**.

# v3.1.0-beta.1 · 2026-11-27

### Beta Pre-Release: InkAway Handwritten Notes Support

- **InkAway (`ink-away.koplugin`) support for PDF & EPUB**: exports freehand strokes, shapes (lines, curves, rectangles, triangles, ellipses, polygons, arrows), RGB colors, highlighter opacity, text boxes, and linked `.inkaway` book/highlight notebooks into clean vector `.svg` files in `drawings/`.
- **Automatic SVG updates**: tracks stroke changes per page so adding or editing drawings updates the exported SVG while keeping Obsidian `^hl-` block IDs stable.
- **Note**: Exports your actual drawn strokes as vector SVG images (no OCR on handwriting).

You can install this beta directly from KOReader via **Tomedown → Settings → App & updates → Release channel → Beta → Check for beta updates**.

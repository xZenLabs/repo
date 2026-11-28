# v3.1.0-beta.8 · 2026-11-28

### Beta Pre-Release: Highlight Separators (Global & Per-Book) (#55)

- **Configurable highlight separators** (*Settings → Notes & highlights → Highlight separator* and per-book under *Current book → Format & layout → Notes & highlights → Highlight separator*):
  - **None** *(default)*: blank line between highlights (`---` only between chapters).
  - **Line (`---`)**: horizontal rule `---` between highlights, automatically promoting `#` chapter headings to `##` to preserve visual hierarchy.
  - **Dots (`· · ·`)**: light typographic `· · ·` divider between highlights, keeping `---` for chapter breaks.
  - **Editorial + Dots (`· · ·`)**: folds page/date/color metadata directly inside the blockquote (`> — *p. 3 · 23 Nov 2026 | 22:17 · Yellow*`) with `· · ·` between highlights.
  - **Editorial + Line (`---`)**: combines inline quote attribution with `---` between highlights and `##` chapter headings.
- **100% cross-profile & merge compatibility**: works across **Obsidian**, **Standard (GitHub / HTML)**, and **CommonMark**, with full support for `Inline`, `Callout ([!note])`, and `Footnotes` personal notes as well as `Keep my notes` (`preserve`) merges.
- **Includes everything from `v3.1.0-beta.7`**: InkAway eraser fidelity, highlight-first sorting, unified multi-word EPUB/PDF annotations, stable anchor IDs, automatic orphan SVG cleanup, direct TOC chapter lookup, and highlight color labels & custom aliases (#53).

You can install or update directly in KOReader via **Tomedown > Settings > App & updates > Release channel > Beta > Check for beta updates**.

# v3.1.0-beta.7 · 2026-11-28

### Beta Pre-Release: Eraser Fidelity, Highlight-First Ordering & Per-Book Color Aliases (#55)

- **InkAway eraser fidelity inside handwritten notes**: `kind = "erase"` strokes inside `Book notes` (`.inkaway`) now remove/split prior erased strokes so erased letters never reappear in exported SVGs, while preserving strokes drawn afterwards.
- **Handwritten notes sorted under their linked highlight**: when a handwritten note shares the same page and timestamp as a text highlight, the text highlight always appears first with the handwritten note directly underneath it.
- **`Color aliases` in `Current book`**: added `Color aliases` directly under `Current book > Format & layout > Notes & highlights` alongside `Highlight color`.
- **Includes everything from `v3.1.0-beta.6`**: unified multi-word EPUB/PDF annotations, stable anchor IDs, automatic orphan SVG cleanup, direct TOC chapter lookup, and highlight color labels (#53).

You can install or update directly in KOReader via **Tomedown > Settings > App & updates > Release channel > Beta > Check for beta updates**.

# v3.1.0-beta.6 · 2026-11-28

### Beta Pre-Release: Unified InkAway Annotations & Complete Tool Fidelity (#55)

- **Natural unified EPUB & PDF annotations**: multi-word handwritten notes, arrows, shapes, dots, and margin marks drawn together on an EPUB or PDF page are now reconstructed in exact 2D layout and exported as a single cohesive SVG annotation instead of splitting word-by-word, while independent margin notes far apart vertically stay separate.
- **Stable drawing IDs & automatic orphan cleanup**: reflowable EPUB notes keep stable anchor-based filenames and Obsidian block IDs across font/window resizes, and stale drawing files are automatically pruned on re-export.
- **Complete InkAway tool support**: translucent highlighter/marker/watercolor opacity, eraser-split strokes (`breaks`), sticker & paint-bucket `fill_color` interiors + outlines, flood-fill runs, symmetry modes (`vert`/`horiz`/`quad`), rich-text bullets/checkboxes, and multi-page `Book notes` chapter continuations.
- **Includes all features from `v3.1.0-beta.5`**: direct TOC chapter lookup for PDFs & EPUBs, CReEngine offscreen safety, and optional highlight color labels & custom aliases (#53).

You can install or update directly in KOReader via **Tomedown > Settings > App & updates > Release channel > Beta > Check for beta updates**.

# v3.1.0-beta.5 · 2026-11-28

### Beta Pre-Release: Safe TOC Chapter Lookup & Crash Fix (#55)

- **Fixed crash when exporting/indexing closed EPUBs with handwritten notes**: prevents KOReader's CReEngine (`libkoreader-cre.so`) from calling `getToc()` on an unrendered offscreen `CreDocument` during Index/Digest/batch exports.
- **In-memory TOC caching & XPointer lookup**: caches the live Table of Contents when closing a book so delayed auto-exports on close and subsequent exports resolve EPUB `DocFragment` chapters without re-opening documents, and opens closed fixed-layout PDFs at most once per session.
- **Includes all features from `v3.1.0-beta.4`**: direct TOC chapter lookup for InkAway & stylus notes and optional highlight color labels & custom aliases (#53).

You can install or update directly in KOReader via **Tomedown > Settings > App & updates > Release channel > Beta > Check for beta updates**.

# v3.1.0-beta.4 · 2026-11-28

### Beta Pre-Release: Chapter Association for Handwritten Notes (#55)

- **Direct Table of Contents (TOC) chapter lookup for InkAway & stylus notes**: handwritten notes on PDFs and EPUBs are now automatically grouped under their actual book chapters using KOReader's Table of Contents (live reader TOC, custom handmade TOC, or embedded document TOC when exporting closed books), even in chapters without any text highlights.
- **Reflowable EPUB & Book notes chapter alignment**: prioritizes XPointer document order (`DocFragment`) over shifted reflow page numbers and aligns InkAway `Book notes` chapter pages directly inside their matching chapter section.
- **Includes all features from `v3.1.0-beta.3`**: InkAway handwritten notes support and optional highlight color labels & custom aliases (#53).

You can install or update directly in KOReader via **Tomedown > Settings > App & updates > Release channel > Beta > Check for beta updates**.

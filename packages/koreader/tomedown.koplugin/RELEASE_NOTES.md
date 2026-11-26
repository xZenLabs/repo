# v3.0.0 · 2026-11-26

# Tomedown v3.0.0

### Added

- **Dedicated 3-profile Markdown style selector (`tomedown_shared.lua`, `tomedown_render.lua`, `tomedown_cover.lua`)**:
  - `Markdown style`: available both globally (`Settings → Export → Markdown style`) and per book (`Current book → Format & layout → Markdown style`), independent of `Export format` (`.md`, `.txt`, or `Both`), with three profiles: `Obsidian`, `Standard (GitHub / HTML)`, and `CommonMark (no HTML)`.
  - **Standard (GitHub / HTML)**: renders book notes, `00 - Index.md`, and `00 - Reading Digest.md` with clean headings, lists, `<details>` synopses, sized `<img>` covers, and `[Title](file.md)` links, omitting Obsidian-only callouts (`[!book]`, `[!abstract]-`, `[!summary]`, `[!highlight]`), wikilinks, and `^hl-` block IDs.
  - **CommonMark (no HTML)**: omits all inline HTML tags (`<details>`, `<img>`, `<br>`) and `&nbsp;` entities for Zettlr, Pandoc, Logseq, and iA Writer, rendering `###` + `>` synopses, nested Markdown index lists, underscore emphasis, and compact `260×390 px` covers via pure `![Title](covers/...)` syntax (automatically re-extracting `800×1200 px` covers when switched back to `Obsidian` or `Standard`).
- **Nested vault asset folders (`tomedown_shared.lua`, `tomedown_cover.lua`, `tomedown_handwritten.lua`, `tomedown_upload.lua`)**:
  - `Covers folder` and `Drawings folder` under `Settings → Export → File names & folders` now accept nested vault-relative paths up to 3 levels (such as `assets/covers` and `assets/drawings` for Logseq, Obsidian, and Zettlr), automatically migrating existing files, pruning empty old directories, creating multi-level WebDAV folders (`MKCOL`), and resolving relative links across subfolder layouts.
- **Harmonized visual styles (`tomedown_render.lua`)**:
  - Unified 4 visual themes across book header modules, `00 - Index.md`, and `00 - Reading Digest.md`: `Minimal symbols (● / ◐)`, `Emoji (🟢 / 🟡)`, `Code badges (READING)`, and `Editorial (Reading)`.
  - **Independent catalog styling**: dedicated `Index style` and `Digest style` selectors with a `Follow book style` toggle enabled by default so one choice themes the entire vault, or configurable independently.
- **Full per-book configuration parity (`tomedown_menu.lua`)**:
  - **Unified per-book layout**: `Current book → Format & layout` mirrors all global visual and structural options onto a single 6-inch e-reader screen (`Export format`, `Markdown style`, `Notes & highlights`, `Book page`, `YAML frontmatter`, `Frontmatter fields`, and `Reset to global style settings`).
  - **Granular per-book overrides**: every option defaults to `Follow global setting` (`Global` / `Custom` status indicator), including `Book cover`, `Personal notes format`, `Special highlight style` (all 6 markers), `Link IDs on highlights`, `Every highlight is special`, and individual `Book page` modules.
- **In-reader dashboard cards and annotation browser (`tomedown_menu.lua`, `tomedown_upload.lua`)**:
  - **Book summary card**: `Current book → Book summary` opens a rounded e-ink card showing title, author, 3 interactive KPI counters (**Highlights**, **Special**, **Notes**), effective format and style, sync status, tags, and a direct `Export this book` button.
  - **Paginated annotation browser**: tapping any KPI counter opens a paginated card adapted to 6-inch Kindle and Kobo displays; short tap jumps directly to the passage (`GotoXPointer` / `GotoPage`), while long press toggles `Special` status or edits the note in place.
  - **Last export dashboard**: redesigned `Tomedown → Last export` into a 3-column KPI card (`Exported`, `Skipped`, `Errors` / `Backups`) with literary timestamp, active configuration, recent book titles, cloud status, and quick sync actions.
- **Personal note formats and highlight context (`tomedown_render.lua`, `tomedown_export.lua`)**:
  - **Callout note style**: added `Callout ([!note])` alongside `Inline` and `Footnotes` under `Personal notes format`, rendering reader commentary inside a dedicated `> [!note]` block below the citation while keeping `^hl-xxxxxxxx` block IDs anchored to the quote.
  - **Surrounding sentence context**: optional context extraction on reflowable documents (`Highlight context`) placing the surrounding passage directly beneath the highlight.

### Changed

- **Contextual e-ink menus (`tomedown_menu.lua`)**:
  - Dependent rows (such as `Digest style` under `Reading digest` and `Synopsis display` under `Book synopsis`) appear only while their parent toggle is active, Obsidian-only options disable in `Standard` / `CommonMark` / `.txt` modes, and foldable synopsis options adapt automatically in `CommonMark` mode.
- **Two-way vault merge and YAML serialization (`tomedown_merge.lua`, `tomedown_shared.lua`)**:
  - Improved quote canonicalization and note block preservation in `Keep my notes` so personal commentary and manual edits survive re-exports without duplication.
  - Native ISO date output (`YYYY-MM-DD`) and safe YAML quoting for colons, wikilinks, and commas inside custom frontmatter values for direct compatibility with Obsidian Bases and Dataview.
- **Localization**:
  - Updated and shortened single-line `TouchMenu` labels across Italian (`it`), French (`fr`), German (`de`), Spanish (`es`), and Brazilian Portuguese (`pt_BR`) to prevent truncation on 6-inch screens.
- **Website and online documentation**:
  - Redesigned homepage, About, Download, 404, and Documentation hub with an interactive live note specimen, `Obsidian` vs. `Standard` comparison slider, updated vault screenshots, `Current book` reference guide, and calm `100%` lightbox image inspection.

### Fixed

- **Cloud upload serialization on book close (`main.lua`, `tomedown_upload.lua`, `tomedown_export.lua`)**: coordinated pending-upload flushes across `ReaderUI` and `FileManager` plugin instances, serialized overlapping `uploadPaths` batches so transient covers and drawings are never deleted while still queued, and prevented pointless backoff retries when a local file is missing.
- **Strict per-book override isolation (`tomedown_shared.lua`, `tomedown_export.lua`, `tomedown_menu.lua`)**: preserved empty-set `fm_hidden` overrides when re-enabling globally hidden frontmatter fields on a single book, respected per-book `Book cover` disabling in `00 - Index.md`, and synchronized `digest_dirty` on per-book style changes without invalidating other books.
- **Per-book section style availability**: unlocked `Book style` under `Harmonize book styles` in `Current book → Format & layout → Book page → Section styles` even when optional header modules are disabled.
- **Custom e-ink card repainting**: added `onShow` and `onCloseWidget` dirty refresh regions (`movable.dimen`), `show_parent` button wiring, and `DocSettings` offline fallback across all rounded cards.
- **Kindle Lua 5.1 compatibility**: kept module upvalue counts below the 60-upvalue ceiling enforced by LuaJIT / Lua 5.1 on e-reader firmware.
- **Website showcase and navigation**: locked showcase stage geometry to eliminate height jumps, restored smooth automatic slide rotation, and resolved broken internal documentation anchors.

---

**Full Changelog**: https://github.com/imanubdesigner/tomedown.koplugin/compare/v2.1.0...v3.0.0

# v2.1.0 · 2026-11-17

# Tomedown v2.1.0 is Here

### Added

- **Handwritten notes and stylus drawings (`tomedown_handwritten.lua`)**:
  - Exports freehand stylus drawings and annotations from stylus-enabled KOReader devices as clean vector `.svg` files into the `drawings/` folder (configurable via `Settings → Style → Drawings folder`).
  - Automatically embeds vector illustrations directly into book notes and the reading digest.
  - Supports both KOReader freehand stylus vector strokes and `pencil.koplugin` bitmap/bookmark captures.
- **Modular book note header (`tomedown_render.lua`)**:
  - `Include book title in body`: adds an `H1` title and `H3` author/series header to the note body.
  - **Overview recap selector**: configurable recap layout (`Inline / Heading`, `Classic blockquote`, `Callout ([!summary])`, or `Table`).
  - **Reading dashboard**: embeds reading status, progress percentage, page count, star rating, literary dates, and a quick backlink to the book index (`00 - Index.md`).
  - **Collapsible EPUB synopsis**: extracts book blurbs into a collapsible callout (`[!abstract]- Book synopsis`).
  - **Body tags**: adds clickable `#tags` directly to the note body.
  - **Special highlights showcase**: collapsible `★ Special highlights` showcase callout before chapters.
- **Library index additions (`00 - Index.md`)**:
  - **Completed books**: dedicated showcase section for completed volumes above the main index.
  - **Library dashboard**: consolidated status overview (`[!summary] Library dashboard`) with direct navigation to the reading digest.
  - **Tag cloud**: aggregated tag cloud sorted by frequency.
  - **Index tag display selector**: choose between `Show all`, compact `First 3 (+N)` pill badge, or collapsible `<details>` wrapper to keep table columns readable.
- **Portable settings export and restore (`tomedown_settings_backup.lua`)**:
  - `Export settings to file` and `Restore settings from backup…` under `Settings → Files`.
  - Serializes all global and per-book configurations into `tomedown_settings_backup.lua` inside the local folder for straightforward device migration.
- **Reading digest quick export**:
  - Added `Export reading digest` directly to the primary Tomedown menu in KOReader.
- **Visual identity and topbar glyph**:
  - Updated visual identity, logo mark, and About dialog banner.
  - 1-bit monochrome topbar icon (`assets/appbar.tomedown.svg`), toggleable via `Settings → Style → Show Tomedown icon in the top bar`.

### Changed

- **Reading digest layout (`00 - Reading Digest.md`)**:
  - Literary date format (`16 Nov 2026`), timestamp labels (`09:41`), and horizontal dividers separating daily reading sessions.
- **Backup management interface (`tomedown_menu.lua`)**:
  - Explicit timestamp labels for existing note backups and snapshots (`Saved notes · <date>`, `Latest snapshot · <date>`).
  - Added global `Delete all backup copies…` bulk cleanup with a safety confirmation dialog.
- **Localization**:
  - Updated translations for Italian (`it`), French (`fr`), German (`de`), Spanish (`es`), and Brazilian Portuguese (`pt_BR`).
- **Documentation and online reference**:
  - Comprehensive documentation overhaul with interactive zoom inspection for Obsidian architecture diagrams and updated UI schematics.

### Fixed

- **Settings restore security**: sandboxed `load` / `setfenv` execution environment and null-byte validation in `restoreSettingsFromFile()` to ensure safe deserialization of backup files.
- **Frontmatter key ordering**: deterministic serialization order and preservation of user custom frontmatter fields during note re-exports.
- **Diagram rendering**: resolved right-bezel clipping and visual border artifacts in documentation SVG diagrams.

---

**Full Changelog**: https://github.com/imanubdesigner/tomedown.koplugin/compare/v2.0.1...v2.1.0

# v2.0.1 · 2026-11-12

If you have existing book notes, re-exporting the current book or running a library re-export is recommended to apply the new tag splitting rules and unbreakable badge formatting to your index and frontmatter.

Improvement

• Unbreakable tag badges across all index views: every tag pill in the index table is now rendered as a protected inline block (white-space: nowrap). Hyphenated subjects like #Horror-tales or #Psychological-fiction never break across lines mid-word, preserving clean spacing across Tags below title, Tags column, and Compact layouts.
• Intelligent tag and conjunction splitting: subjects containing conjunctions ("and", "AND", "&") or Calibre hierarchical facets ("--") are now automatically separated into distinct, individual tags with proper first-letter capitalization (e.g. Detective and mystery stories becomes #Detective and #Mystery-stories).
• Direct metadata keyword parsing: raw EPUB and Calibre subject metadata is passed directly to the tag normalization pipeline without preliminary space-to-hyphen replacement, preserving full compound phrases for intelligent splitting.
• Smooth format transitions: switching between Markdown (.md) and Plain Text (.txt) automatically manages note visibility, safely backing up inactive notes as .bak files and restoring them when switching back without cluttering the active vault.

Fix

• Clean frontmatter tag removal: disabling book metadata tags cleanly strips the tomedown_book_tags key from frontmatter instead of leaving orphaned keys.
• Test suite verification: all 2,012 automated assertions passing across 8 test suites on Lua 5.4, LuaJIT, and Kindle luac5.1 bytecode compiler.

Install it from Check for updates inside the plugin, or download the zip below.

Full Changelog: https://github.com/imanubdesigner/tomedown.koplugin/compare/v2.0.0...v2.0.1

# v2.0.0 · 2026-11-11

New

• Per-book style & frontmatter overrides: customize frontmatter visibility, export formats (.md / .txt / both), footnote styles, chapter headings, and highlight metadata for a single volume under Current book → Style & format.
• Modular YAML frontmatter: hide any optional standard key (e.g. progress, status, pages, special) to keep git diffs noise-free.
• Custom frontmatter fields: check [x] Custom fields to define arbitrary key-value pairs (e.g. genre, project, doi, rating). Custom keys automatically turn into individual toggleable checkboxes in both global and per-book menus.
• Book-only custom metadata: define custom fields isolated strictly to the volume you're reading without polluting other notes.
• Custom frontmatter key ordering: control the exact sequence of YAML keys with a comma-separated list (Frontmatter key order…).
• Multi-format export: export notes as rich Obsidian-ready Markdown (.md), clean minimalist Plain Text (.txt), or Both simultaneously.
• Native Top Bar icon: optional dedicated [M↓] tab in KOReader's top reading navigation bar for instant 1-tap access to Tomedown actions.
• 3-Slot rolling safety backups: merge engine rotates hand-edited backups through three timestamped slots (.bak.1 → .bak.2 → .bak.3) so earlier edits are never buried.
• Highlight context capture: optionally capture surrounding text before and after each highlight.

Improvement

• In-place menu disclosure: toggling Custom fields or adding keys updates menus dynamically without reloads.
• Instant cache flush: modifying style or metadata immediately invalidates the in-memory book cache for Export this book.
• Full localization: complete and updated translations for Italian, German, Spanish, French, and Brazilian Portuguese.

Fix

• Single-book export cache: resolved an issue where Export this book could reuse a cached book model after changing settings.
• Under-the-hood stability: verified with 2,130 automated assertions passing on Lua 5.4, LuaJIT, and Kindle's luac5.1 bytecode compiler.

Install it from Check for updates inside the plugin, or download the zip below.

# v1.4.1 · 2026-11-08

New

• Customizable covers folder name: choose any destination folder name for extracted book covers (e.g. `_covers`, `_assets`, or whatever you prefer) under **Settings → Style → Covers folder**. Perfect for Obsidian vaults where leading underscores hide asset directories from note listings. Thanks to @arcanaemia for the suggestion (#41)!
• Seamless automatic migration: changing the folder name automatically migrates existing covers to the new directory and cleans up the old folder. All frontmatter paths (`cover: "_covers/..."`) and Markdown image links are automatically updated on export.

Improvement

• Updated documentation across all settings guides.
• Full localization in Italian, German, French, Spanish, and Brazilian Portuguese.
• Verified with 1,954 automated assertions passing on Lua 5.4, LuaJIT, and Kindle's Lua 5.1 bytecode check.

Install it from **Check for updates** inside the plugin, or download the zip below.

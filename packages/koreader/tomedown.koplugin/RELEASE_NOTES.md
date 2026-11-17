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

# v1.4.0 · 2026-11-07

**New**

- Universal Markdown highlights: choose how special highlights are formatted when exported (Obsidian Callout [!highlight], GFM Alert [!IMPORTANT], Standard highlight ==highlight==, Highlight & bold, Star & bold, or Bold).
- Reading Digest: a consolidated chronological summary file (00 - Reading Digest.md) grouping highlights across your library by day, with an epigraph and a one-tap export shortcut.
- KOReader metadata import: import book ratings, reviews, reading status, reading dates, and collections from KOReader directly into note frontmatter.
- Reading now section: optional dedicated section at the top of the index table for books currently being read.
- Subfolder organization & filename templates: organize notes into folders by author, series, or status, and customize filename patterns (Author - Title, Title (Author)).
- Native Bookshelf integration: quick actions (Export this book, Tags..., Book visibility...) integrated into the bottom action bar of each book.
- Tag suggestions & manager: fast tag suggestion dialog based on library tags and a tool to clean up unused tags.

**Improvement**

- Polished index tables: cover images optimized to 90×120 for balanced rows, compact 5-block progress bars, and added vertical breathing room for multi-line tags.
- Calibre tag facet splitting: hierarchical category tags (e.g. Fiction.Mystery) are automatically split into clean individual #tag values.
- Reorganized settings: settings split into dedicated, uncluttered Index and Style submenus with dedicated icons.
- Book visibility: exclude specific volumes from the index or from export without deleting existing notes.

**Fix**

- Reading digest heading links: wikilink headings render with unescaped pipes so they display cleanly without raw bracket syntax in Markdown viewers.
- Under-the-hood stability: verified with 1,929 automated assertions passing on both Lua 5.4 and LuaJIT.

Install it from Check for updates, or the zip below.

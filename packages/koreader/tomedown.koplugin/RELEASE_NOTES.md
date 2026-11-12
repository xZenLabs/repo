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

# v1.2.0 · 2026-11-03

**New**

- Four new languages: German, French, Spanish and Brazilian Portuguese. Menus and exported notes follow KOReader's language wherever a translation exists.
- Tags for the book you are reading: under *Current book*, Tags: %1 adds tags to that book alone. They join its frontmatter at the next export, and tags made only of numbers (1500, 1984) are ignored, with a notice that names them; 1500s and anno-1500 stay valid.
- Tags in the index: books that carry their own tags get a Tags column, after Series and before Status, written as clickable #tag separated by a space. A book without tags shows a dash, and the column disappears when no book in the table has tags.
- Index order: under Settings → Files, My books can be ordered by author (default), title, last read or highlights. Last read and highlights run newest and most first; series books keep their own order at whatever the setting says.

**Fix**

- Smaller download: the repository banners and the manual are no longer packed into the zip by mistake.

**Improvement**

- The plugin code is now split into small modules (shared, menu, export, upload): nothing changes for readers, but every future release is easier to check.
- The workflows are linted in CI with actionlint, and the release zip is built by a script that checks its exact contents against an allowlist, so docs and banners cannot come back.

Install it from Check for updates, or the zip below.

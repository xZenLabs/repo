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

# v1.1.3 · 2026-11-01

- Updates unpack into a new folder first, check it, and only then replace the installed one. A failed download, unpack or check leaves your current version untouched.
- The check looks for main.lua and _meta.lua, compiles every Lua module, and compares the version inside with the release.
- The old folder stays as tomedown.koplugin.previous until the next update, and files that the new version no longer ships go away with it.
- An archive entry that points outside the plugin folder is refused, and the update stops before it can touch the installed copy.
- The curl fallbacks quote the address and accept only https addresses with safe characters.
- Release notes and the changelog are plain text from this version on, so the layout is the same on every device.
- The About window now shows the licence, GNU Affero General Public License v3.0.
- The test suite runs on LuaJIT, the interpreter KOReader ships, as well as on Lua 5.4.

Coming from 1.1.2 or earlier, this release is installed by the previous updater; the new install steps start with the next update.

# v1.1.2 · 2026-10-30

Tomedown 1.1.2.

- The row that rebuilds every file is now called *Repair all files*, which is what it does.
- The About window wears the new logo.
- The README has a front page and reference pages now: settings, file formats, keeping notes, and developing. Menu screenshots are refreshed there.

Install it from *Check for updates*, or the zip below.

Questions or feedback on the menu? [Join the discussion](https://github.com/imanubdesigner/tomedown.koplugin/discussions).

# v1.4.0 · 2026-11-07

# [Release] Tomedown v1.4.0 for KOReader: Universal highlights, reading digest, dedicated menus, and Bookshelf support

Tomedown is a KOReader plugin that turns every volume you read into its own Markdown note with frontmatter, cover art, and an automatic library index. Direct from your e-reader to your notes vault. No servers, no tracking, no locked gates.

### What's new in v1.4.0:

1. **Universal Markdown highlights**:
   Until now, special highlights relied heavily on Obsidian callout syntax. You can now choose how your special highlights are exported from KOReader:
   - Callout (`[!highlight]`)
   - Alert (`[!IMPORTANT]`)
   - Standard Markdown highlight (`==highlight==`)
   - Highlight + bold (`==**text**==`)
   - Star + bold (`⭐ **text**`)
   - Bold (`**text**`)
   Your notes will now look great whether you use Obsidian, MarkText, Typora, Logseq, iA Writer, or standard Markdown viewers.

2. **Reading Digest improvements**:
   - One-tap export: all main actions are now grouped right at the top of the menu, including a direct shortcut for `Export reading digest`.
   - Clean design: added an elegant title, an inspirational welcome quote, and fixed heading link formats so they render cleanly without raw bracket syntax in any Markdown editor.

3. **Reorganized Style and Index menus**:
   - The settings menu has been completely reorganized with dedicated icons for **Index** and **Style**.
   - The Files menu is now much cleaner and easier to navigate.

4. **Polished Index tables**:
   - Optimized table covers to 90×120 for compact, balanced rows.
   - Sleeker 5-block progress bars to save horizontal space and keep tables from overflowing.
   - Added vertical breathing room between tag pills.
   - Long Calibre category tags are now automatically split into clean, individual tags.

5. **Native Bookshelf integration**:
   If you use the Bookshelf plugin, you will now find Tomedown's quick actions (`Export this book`, `Tags...`, `Book visibility...`) built right into the bottom action bar of each book.

6. **General improvements**:
   - 1,929 automated assertions passing on both standard Lua and LuaJIT.
   - Under-the-hood stability improvements and bug fixes.

---

### Installation:
- If you use a KOReader plugin store ([Storefront](https://github.com/ultimatejimmy/storefront.koplugin) or [AppStore](https://github.com/omer-faruq/appstore.koplugin)), search `tomedown` under Tools and install it.
- Alternatively, download `tomedown.koplugin-v1.4.0.zip` below and unzip it to your e-reader's `koreader/plugins/` directory.

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

# v1.1.1 · 2026-10-27

Tomedown 1.1.1.

- The changelog inside KOReader no longer shows the address of an image or a link when the viewer cannot render Markdown. It keeps the image caption and the link text.
- The rename dialog is called *Notes heading*, like the row that opens it.

Install it from *Check for updates*, or the zip below.

Questions or feedback on the menu? [Join the discussion](https://github.com/imanubdesigner/tomedown.koplugin/discussions).

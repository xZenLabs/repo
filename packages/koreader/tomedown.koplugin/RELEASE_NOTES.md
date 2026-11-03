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

# v1.1.0 · 2026-10-27

**Tomedown 1.1.0, the per book edition.**

Three betas are behind this one, all of them tested on the device, offline included. 1.1 starts from a single question, whose notes are kept, and answers it one book at a time. Along the way the menu was regrouped and every row was given the name it does, so the release is also the one where *Preserve* becomes *Keep my notes*.

## Highlights

- **A switch for each book.** *Keep my notes in this book*, under *Current book*, decides for that book alone, with the global switch off. Turning it off asks first, saying what is about to happen; confirm and the file you had is kept as `.bak`, then the plain export takes its place. Turn it on again and those notes come back into the file. A book that stores its own choice keeps it through later flips of the global switch.
- **A heading for each book.** *Notes heading: %1*, also under *Current book*, names that book's zone and only that one, with any title you like, or no title at all if you leave it empty.
- **The index stopped tagging along.** *Keep my notes: index* and *Index notes heading: %1* live in *Settings → My notes*, so exporting one book can no longer rewrite your notes in `00 - Index.md`.
- **Two copies, one job each, plain names.** `.bak` is *Notes set aside*: the zoned file as it was when you turned Keep my notes off, and it comes back when you turn it on. `.bak.1` is the *Safety copy*: text of yours that a rewrite was about to replace and that would not come back by itself. A copy kept by an older version shows as *Older copy*. *Backup copies…* in *Current book* lists them one at a time with the day each was saved, and deletes one only after a box that says what it holds.
- **Block IDs on every highlight.** *Add link IDs to highlights* appends a stable `^hl-…` to each quote, taken from the highlight's own creation time, so a link from another note lands on that highlight and survives the next export. Off by default.
- **One menu, five groups, names that read what they do.** The main menu is nine rows with a book open and seven in the file browser, the same list in both, but for *Export this book* and *Current book*. Settings is *Files*, *Cloud*, *My notes*, *Highlights for Obsidian* and *Updates*, with *Beta versions* inside.

## Added

- *Keep my notes in this book*, per book, with its own *Notes heading: %1* row right below.
- *Keep my notes: index* and *Index notes heading: %1*, so the index has a choice of its own.
- *Backup copies…* under *Current book*, with the copies named for what they hold.
- *How special highlights look: Callout* or *Bold*: the marker for a single Special Highlight is now yours to pick. The row is grayed out while *Treat every highlight as special* is on, because then every quote is a callout.
- *Add link IDs to highlights*, for the ids that keep a link alive.
- *Beta versions* as a submenu of *Updates*, with *Receive beta versions*, *Check for beta updates* while it is ticked, *Go back to the stable version* and the installed version as a plain label.

## Changed

- *Preserve manual edits* is now *Keep my notes: all books*, *Personal notes* is *Notes heading: %1*, and *Book notes* is the per book heading. The word Preserve leaves the code, the strings, the README, the tutorial, the Obsidian guide, the roadmap and the guide sheets.
- *Merge edits made in the cloud* is now *Bring in edits made in Obsidian* and lives in *My notes*, where the notes are.
- *Export current book* is *Export this book*, *Export only what changed* is *Export new and changed books*, *Export every book's highlights* is *Export all books*, *Upload everything to the cloud* is *Upload all files again*, and *Status* is *Last export*.
- The rows that need an open book (*Export this book* and *Current book*) only exist while a book is open, so the file manager sees the same menu minus those two.
- The picked local folder is written to the settings file on the spot. Before, it only reached the disk at the next suspend or autosave, so KOReader closing in between sent the next export to the folder you had just left.
- New screenshots everywhere, including the menu inside an open book, and the guide sheets follow the new names.
- The stored setting keys (`preserve`, `preserve_books`, `preserve_index`, `notes_title`, `notes_titles`, `exports`) keep their names: an update finds every choice where you left it.

The new menus, one after the other:

![The new menus in Tomedown 1.1.0](https://raw.githubusercontent.com/imanubdesigner/tomedown.koplugin/main/assets/menu/tomedown-1.1.0-menus.gif)

Every screenshot is in the README: https://github.com/imanubdesigner/tomedown.koplugin

## Fixed

- **A backup can no longer be thrown away by one worth less.** All copies went to a single name, so the next one overwrote the last, and the one destroyed could be the one holding your notes. There are two slots now, `.bak` and `.bak.1`, the older one rotates back, and a file that is exactly what Tomedown wrote last is not copied at all.
- **A copy that fails stops the write.** If either slot cannot be written (a full card, a read-only folder), the export leaves the file exactly as it is and says so, and the next export tries again.
- **The notes the first beta hid come back.** A card that ran 1.1.0-beta.1 could hold the notes behind a newer copy without a zone, where the next beta did not look. The first export now swaps the two slots once, undoes a rename the filesystem refuses, and puts back a copy left in `.bak.swap` by an interrupted swap.
- **A cloud copy written elsewhere no longer takes the notes set aside.** If the cloud copy was replaced by another writer and this device still has notes in `.bak`, the two zones are joined: the cloud text keeps its place and its order, and the paragraphs that exist only in `.bak` follow it. What the rewrite replaces is kept as the safety copy first. If the join cannot be made, the export is held back and nothing is written.
- **A rename refused by the filesystem** (some mounts on the Kindle card) no longer fails the copy: the content is written in place, with a warning in the log.
- A note reworded in the cloud is recognized by its first line and is not copied twice.
- Two checks in the update menu read what they do: *Check for beta updates* inside *Beta versions*, and *Go back to the stable version* instead of *Reset to latest stable release*.

## Installing

**If you already use a KOReader plugin store**, [Storefront](https://github.com/ultimatejimmy/storefront.koplugin) or [AppStore](https://github.com/omer-faruq/appstore.koplugin), search `tomedown` under *Tools* and install it. They are community plugins, not part of KOReader itself; if you have neither, use the zip below.

**Manual**: download `tomedown.koplugin-v1.1.0.zip` from the **Assets** section at the bottom of this page (not the *Source code* archive), unzip it into `koreader/plugins/` and restart KOReader.

**Coming from 1.0.0**: *Check for updates* in the plugin menu now finds this release by itself, no zip needed. **Coming from a 1.1.0 beta**: the stable release is offered the same way, or use *Settings → Updates → Beta versions → Go back to the stable version*.

README, full tutorial, quickstart sheets and Obsidian guide sheets:
https://github.com/imanubdesigner/tomedown.koplugin

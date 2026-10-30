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

# v1.0.0 · 2026-10-21

**Tomedown 1.0.0, the first stable release of the two-way edition.**

Two betas are behind this one, both tested end to end, offline included. This is the version that stops throwing away what you write.

## Highlights

- **Your own notes survive the export.** *Preserve manual edits* is new in 1.0.0, off by default: switch it on and the new render folds into the file you already annotated instead of replacing it. Your words stay under their own heading, fenced by the invisible HTML comments the plugin uses as handles. In 0.8.0 there was no such thing: every export won, and anything you typed at your desk was gone on the next run.
- **The merge works both ways now.** Before folding the new highlights in, the export fetches your copy from the cloud and, if it changed since the last upload, uses that as the base instead of the local one. Your notes come along with the fresh highlights. The setting is *Merge edits made in the cloud*, it is on by default, and it lives in Settings → Cloud right under *Upload to cloud*.
- **Offline is a first-class case.** Export with no connection and the file is queued. When you are back online, the plugin fetches the cloud copy, compares it with the one it sent last, folds your notes in, and only then pushes. If the download fails for some transient reason the file is held back and retried at the next chance, so nothing gets lost in either direction.

## Added

- *Preserve manual edits* as a setting, together with *Personal notes*, the heading above your notes block. Rename it per your taste, or leave the field empty to export without a heading. The row only exists while preserve is on.
- The settings menu is flatter, and the rows appear and disappear in place as you flip the toggles. The *Cloud* group shows only when a server is set, upload is on and preserve is on, because that is the only case where it has something to do.
- The About popup shows both repository links.

## Changed

- *Reload everything to the cloud* is now *Upload everything to the cloud*, which is what it actually does. It runs the same reconciliation as the export before pushing, so notes written in Obsidian get folded in there too.
- Reading progress bars are drawn as plain rectangles instead of glyphs, so they render the same on every device font.
- The guide sheets, the quickstart sheets and the menu screenshots were all retouched: portable fonts, the Obsidian palette, the settings paths corrected, the cover captions reworded to match what the plugin really does.
- The release zip now carries only what KOReader loads at runtime: the Lua modules, `languages/` and the logo.

## Fixed

- The flush cannot start twice over the same files. `reconcilePending` costs one network request per queued file and the flag that guards the upload was raised only after it, so a reconnect or a resume landing in the middle of that window could queue a second flush on top of the first one. The flag now stays up for the whole reconciliation, lowered on every exit including the error path, where it is wrapped in `pcall` so a failure inside it cannot leave the flush switched off until restart.
- The open book is read from memory during the export instead of being reopened, which was both slower and able to fail on a book still in use.
- `00 - Index.md` reports a write failure instead of failing quietly.

## Upcoming

Things we would like to try next. No promises, no dates, and nothing here is decided yet:

- **Preserve per book.** Keep the global toggle as the default and let a single book override it, for the series you annotate by hand and the ones you do not.
- **Stable block IDs on the highlights.** Give every exported highlight an Obsidian block ID so you can link straight to it from another note and keep that link alive after the next export. Suggested by [Tewel](https://codeberg.org/Tewel), and the one idea from this round that is not in the release yet.
- **Spacing that matches the reader.** Let the merge respect the blank lines you leave under a heading instead of framing the zone the way the plugin prefers.
- **Index speed**, only if a large library ever feels slow. Nothing to do there today.

## Installing

**If you already use a KOReader plugin store** — [Storefront](https://github.com/ultimatejimmy/storefront.koplugin) or [AppStore](https://github.com/omer-faruq/appstore.koplugin), both under *Tools* search `tomedown` and install it. They are community plugins, not part of KOReader itself; if you have neither, use the zip below.

**Manual**: download `tomedown.koplugin-v1.0.0.zip` from the **Assets** section at the bottom of this page (not the *Source code* archive), unzip it into `koreader/plugins/` and restart KOReader.

**Coming from 0.8.0** > *Check for updates* in the plugin menu now finds this release by itself, no zip needed.

README, full tutorial, quickstart sheets and Obsidian guide sheets:
https://github.com/imanubdesigner/tomedown.koplugin

# v0.8.0 · 2026-10-03

> **The Vault release is here: book covers, callouts, a new index and an export layout that reads like a note vault instead of a dump of quotes.**


https://github.com/user-attachments/assets/d4eb3e01-4b22-4947-ab4f-ed8c080bb7d5



## Highlights

- **Book covers** — *Include book covers* (off by default): every export saves the book's cover as an 800×1200 JPEG in full colour (quality 50) under `covers/`, embeds it in the book note and in the index. The `covers/` folder is created on the server on the first upload (WebDAV, FTP, Dropbox); the file leaves the device once the upload has confirmed it, stays queued while offline and goes away on the next flush. Obsidian 1.8.1+ renders the plain `<img>` tags — no snippet to install.

- **Callouts** — *All highlights as Special Highlights* (off by default): every highlight becomes an `> [!highlight]` callout instead of a plain quote; when the toggle is off, only *Special Highlight* marks turn into callouts.

- **Special Highlight** — one tap on a fresh selection (right under *Highlight*) creates and flags a highlight; the compact edit menu of an existing highlight carries the same dynamic row, *Special Highlight* / *Remove Special Highlight*. The mark lives on the annotation, is part of the book hash, and is always exported as a callout.

- **Index v2** — the book index gains cover, book, author, series, status, highlight count and last export per row, wiki links, and a stats line above the table. Existing vaults are backfilled on the next export.

- **Clean export layout** — every file opens with a rule right after the frontmatter, the book cover is centered and framed by rules before the `# **HIGHLIGHTS**` heading, and the index leads with `*9 books · 53 highlights — click a title to open its note.*` (singular agrees too: `*1 book · 1 highlight …*`).

- **Menu renames** — *Generate the 00 - Index.md (for Obsidian)* and *All highlights as Special Highlights*: same behavior, clearer names.

- **Status popup** — widened to 90% of the screen, smallest font, one line per entry with the labels in bold.

- **Keywords are always valid Obsidian tags** — a whitelist sanitizer keeps only letters, numbers, `-`, `_`, `/` and every non-ASCII character (accents, emoji); whitespace becomes `-`, everything else is dropped (`Horror tales; American` → `Horror-tales-American`). Books whose keywords change re-export automatically.

- **Automatic rewrite** — the render format is part of the stored book hash, so the first export after updating rewrites every note once. No *Import all books from history* needed.

## Updating

Update and run one export: notes, covers and the index regenerate themselves. Running one of the betas? Update as usual and switch **Beta Releases** off again if you don't want prereleases any more.

New to Tomedown: download the zip below and install it as a KOReader plugin.

All 758 test assertions green.

*Remotely Save users: set **Abort Sync If Modification Above Percentage** to **100 (disable the protection)** — Tomedown re-exports notes in bulk, which trips the default 50% guard.*

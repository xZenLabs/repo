# v3.1.0-beta.1 · 2026-11-27

### Beta Pre-Release: InkAway Handwritten Notes Support

- **InkAway (`ink-away.koplugin`) support for PDF & EPUB**: exports freehand strokes, shapes (lines, curves, rectangles, triangles, ellipses, polygons, arrows), RGB colors, highlighter opacity, text boxes, and linked `.inkaway` book/highlight notebooks into clean vector `.svg` files in `drawings/`.
- **Automatic SVG updates**: tracks stroke changes per page so adding or editing drawings updates the exported SVG while keeping Obsidian `^hl-` block IDs stable.
- **Note**: Exports your actual drawn strokes as vector SVG images (no OCR on handwriting).

You can install this beta directly from KOReader via **Tomedown → Settings → App & updates → Release channel → Beta → Check for beta updates**.

# v1.1.0-beta.3 · 2026-10-26

**Tomedown 1.1.0-beta.3, the third beta of the per book edition.**

The second beta gave the two copies beside each file a fixed job. This one repairs the cards that ran the first beta, where those copies were still being rotated, and makes sure a cloud copy written elsewhere cannot take the parked notes with it. The everyday promise does not change: preserve on, off, on behaves like a file you keep editing and saving.

A beta, and it behaves like one: it replaces 1.0.0 in the plugin folder (going back means installing the 1.0.0 zip again). What it needs is a week of real reading, and a note from you the moment something feels off.

## Highlights

- **The notes the first beta hid come back.** The first beta rotated every copy into `.bak.1`, so a card that ran it can hold the notes behind a newer copy without a zone, where the second beta did not look. The first export now swaps the two slots once, undoes a rename the filesystem refuses, and puts back a copy left in `.bak.swap` by an interrupted swap. Nothing is overwritten on the way.
- **Preserve on, off, on works like a text file.** Turn preserve off and the zoned file, notes included, is parked as `<name>.md.bak` while the plain export takes its place. Turn it on and that copy becomes the base of the next export: your notes are back. Every note you added is there, one you deleted stays deleted. Ten times in a row, if you like.
- **A copy written elsewhere no longer takes the parked notes.** If the cloud copy was replaced by another writer (a second Tomedown, a sync app resolving a conflict) and this device still has notes parked in `.bak`, the two zones are joined instead of one replacing the other. The cloud text keeps its place and its order, and the paragraphs that exist only in `.bak` follow it. What the rewrite replaces is kept as the safety copy first.
- **The queued upload repairs the copies first.** When the connection comes back before an export runs, the flush was writing `.bak.1` straight away. Now it fixes the first beta's slots and folds the parked notes in before it writes.

## Changed

- A note reworded in the cloud is recognized by its first line and is not copied twice.
- If the join between the two zones cannot be made, the export is held back and nothing is written, the way a copy that cannot be written already works.
- The README and the roadmap describe the recovery, including its one price: a note deleted in Obsidian while this device still had it parked comes back, visible and easy to delete again.

## What to try first

On a book with notes, turn preserve off, look at `<book>.md.bak`, turn it on and export: the notes are back. Do it twice more. If you ran 1.1.0-beta.1, this first export is also the one that puts the two copies back in the right slots.

## Installing

Download `tomedown.koplugin-v1.1.0-beta.3.zip` from the **Assets** section at the bottom of this page (not the *Source code* archive), unzip it into `koreader/plugins/` and restart KOReader.

The beta is also opt-in inside KOReader: *Settings → Updates → Developer*, with *Beta Releases* ticked, will offer it. Without that tick nothing changes, the background check stays on stable releases and nobody gets nudged towards it.

README, full tutorial, quickstart sheets and Obsidian guide sheets: https://github.com/imanubdesigner/tomedown.koplugin

# v1.1.0-beta.2 · 2026-10-26

**Tomedown 1.1.0-beta.2, the second beta of the per book edition.**

The first beta asked a new question: should preserve be a choice for each book? This one repairs the weakest part of the answer, the backups. Two copies sat next to every file, and the rules deciding which held what could still lose the one with your notes inside. Now each copy has a single job, and the one that matters always comes back.

A beta, and it behaves like one: it replaces 1.0.0 in the plugin folder (going back means installing the 1.0.0 zip again). What it needs is a week of real reading, and a note from you the moment something feels off.

## Highlights

- **Turning preserve off parks your file.** The zoned file, notes included, is kept as `<name>.md.bak` while the plain export takes its place. Turn preserve on again and that copy becomes the base of the next export, so your notes are back in the file. It makes no difference whether the plain file on disk is one Tomedown wrote or one you left there: the parked copy is the one that counts. On, off, on, off, on: every note you kept returns each time, one you deleted stays deleted, one you added is kept.
- **The second copy is a safety net.** `<name>.md.bak.1` now holds only text that could not come back by itself: something typed into the plain file while preserve was off (that file is regenerated), a block edited inside its comments, a cloud copy that moved on. It has one slot and never takes the place of `.bak`.
- **A copy that fails stops the write.** If either slot cannot be written (a full card, a read-only folder), the export leaves the file exactly as it is and reports `the backup copy could not be written, file left as it is`. Nothing is traded for a rewrite, and the next export tries again.

## Changed

- A rename refused by the filesystem (some mounts on the Kindle card) no longer fails the copy: the content is written in place, with a warning in the log.
- A cloud copy that is still the very file Tomedown uploaded last is not kept as `.bak.1`, so an ordinary export does not fill the second slot with your own bytes.
- The README went through a full pass: shorter where it repeated itself, plainer where it explains the two copies, and a real mistake corrected (a block edited inside its comments goes to `.bak.1`, not `.bak`).

## What to try first

Turn preserve off on a book with notes, look at the `.bak`, turn it on and export: the notes are back. Then do it twice more. Type a line into the plain file while preserve is off, turn it on, and look in `.bak.1`: your line is there, the parked notes are in the file.

## Installing

Download `tomedown.koplugin-v1.1.0-beta.2.zip` from the **Assets** section at the bottom of this page (not the *Source code* archive), unzip it into `koreader/plugins/` and restart KOReader.

The beta is also opt-in inside KOReader: *Settings → Updates → Developer*, with *Beta Releases* ticked, will offer it. Without that tick nothing changes, the background check stays on stable releases and nobody gets nudged towards it.

README, full tutorial, quickstart sheets and Obsidian guide sheets: https://github.com/imanubdesigner/tomedown.koplugin

# v1.1.0-beta.1 · 2026-10-25

**Tomedown 1.1.0-beta.1, the first beta of the per book edition.**

1.1 is about one question: whose notes are kept. Preservation is now decided per book instead of for the whole library, the index has its own switch instead of following whichever book you exported last, and turning preserve off asks first and puts your notes back when you turn it on again. Block IDs arrived too, so a link to a highlight in Obsidian survives the next export.

A beta, and it behaves like one: it replaces 1.0.0 in the plugin folder (going back means installing the 1.0.0 zip again). What it needs is a week of real reading, and a note from you the moment something feels off.

## Highlights

- **A switch for each book.** *Preserve: this book*, in the book's menu under *Export current book*, decides for that book alone. *Preserve: global* stays the default: on, every file follows it and the per file rows are not even built; off, each book goes back to whatever it stored.
- **A heading for each book.** *Book notes: %1* names that book's zone, and only that book's. Any title you like ("The Witch theory", "Julian Carax Dixit", ...); leave it empty and the zone exports with nothing above it.
- **The index stopped tagging along.** *Preserve: index* and *Index notes: %1* sit in *Settings → Markdown files*, and exporting one book can no longer rewrite your notes in `00 - Index.md`. Off keeps the file as `00 - Index.md.bak`; on brings it back.
- **Turning it off asks first.** A box says what is about to happen, because with preserve off the render overwrites the file (no merge, no copy). Confirm and the file you had is kept as `.bak`, so turning preserve on again puts your notes back into the file, as long as the plain file is the one Tomedown wrote last: something you typed meanwhile is never replaced by an older snapshot.
- **Block IDs on every highlight.** A stable `^hl-…` at the end of each quote, so a link from another note lands on that highlight and survives the next export. Off by default, from *Block IDs for highlights*, with the id taken from the highlight's own creation time. *(Idea proposed by [Tewel](https://codeberg.org/imanubdesigner/tomedown.koplugin/issues/2) on Codeberg)*

## Added

- A *Highlights* group in Settings, with its own icon: *All highlights as Special Highlights*, *Special highlight marker: %1* (callout, or bold for a paragraph-wrapped quote) and *Block IDs for highlights*. The three moved out of *Markdown files*, which had grown too crowded.

## Changed

- Three rows finally read what they do: *Preserve: global* for *Preserve manual edits*, *Notes: %1* for *Personal notes: %1*, and *Export every book's highlights* for *Import all books from history*, which exports and never imports. The global one takes that name to sit next to the other two preserve rows.
- The rows that need a book (*Export current book*, *Preserve: this book*, *Book notes: %1*) only exist while a book is open: in the file manager they pointed at whatever had been read last, so that menu now starts at *Export only what changed*.
- New screenshots everywhere, including the menu inside an open book, and the guide sheets follow the new row names.

## Fixed

- **A picked folder no longer gets lost.** It is written to the settings file on the spot; before, it only reached the disk at the next suspend or autosave, so KOReader closing in between sent the next export to the folder you had just left.
- **A backup can no longer be thrown away by one worth less.** All backups went to a single name, so the next one overwrote the last, and the copy destroyed could be the one holding your notes (turning preserve back on found the plain file Tomedown itself had written and flagged it for backup anyway). There are two slots now, `.bak` and `.bak.1`, the older one rotates back, and a file that is exactly what Tomedown wrote last is not copied at all.

## Still open

On the roadmap after this beta. No promises, no dates, nothing decided:

- **Where the copies live, and how many.** Two slots per file is what this beta ships; one slot only, a `highlights_backup/` folder, or the two we have plus rows to clear them by hand is the question for the Discussion.
- **Managing the `.bak` copies.** A row to delete a book's own copy, a row that lists every copy in the folder, never a button that deletes them all at once: they may be the only copy of what you wrote by hand.
- **Spacing that matches the reader**, so the merge respects the blank lines you leave under a heading.
- **Index speed**, only if a large library ever feels slow.

## What to try first

Flip *Preserve: global* on and off with notes sitting in the books and in the index. Turn *Preserve: this book* off for one book and read the box. Export, type a line in the plain file by hand, switch preserve on again and check your line is still there. Rename *Book notes: %1* on two books and make sure each keeps its own.

## Installing

Download `tomedown.koplugin-v1.1.0-beta.1.zip` from the **Assets** section at the bottom of this page (not the *Source code* archive), unzip it into `koreader/plugins/` and restart KOReader.

The beta is also opt-in inside KOReader: *Settings → Updates → Developer*, with *Beta Releases* ticked, will offer it. Without that tick nothing changes, the background check stays on stable releases and nobody gets nudged towards it.

README, full tutorial, quickstart sheets and Obsidian guide sheets: https://github.com/imanubdesigner/tomedown.koplugin

# v0.8.0-beta.6 · 2026-10-03

> **Last beta before the Vault stable: an index grammar fix and a device check for the new menus.**

Sixth beta of the **Vault** release.

## Highlights

- **Stats line grammar**: a vault with a single book (or a single highlight) now reads `*1 book · 1 highlight — click a title to open its note.*` — no more `1 books · 1 highlights`
- Nothing else changed in the export: hashes stay valid, so there is nothing to re-export; the index line corrects itself on the next export that writes files
- README: the index sample shows the rendered status label, and the stale pre-format screenshot is gone

## Beta focus

1. On the Kindle: Settings → **Beta Releases** ON → *Check for updates* → update to beta.6 and restart.
2. On desktop: reinstall the plugin from the asset below, then restart KOReader.
3. **Device check this round**: open a highlight's menu on the Kindle screen — the entry *All highlights as Special Highlights* is longer than the old one. If it gets truncated on the e-ink menu, say so in the discussion.

All 758 test assertions green.

*Remotely Save users: set **Abort Sync If Modification Above Percentage** to **100 (disable the protection)** — Tomedown re-exports notes in bulk, which trips the default 50% guard.*

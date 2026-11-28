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

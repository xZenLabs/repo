# v0.3.0

First release of **JustDraw**, an **experimental** KOReader plugin for writing and drawing on an e-ink reader with a stylus. It began as a fork of [Finger Ink](https://github.com/SMUsamaShah/fingerink.koplugin).

The KOReader stylus features it builds on are still under development, and the plugin has only been tried on a couple of real devices. Pen handling, palm rejection and screen refresh differ a lot between readers, so your results may vary. Feedback and logs are very welcome.

## What it does

- **Notebooks**: standalone drawing books that belong to no document, with blank, ruled, squared or dotted paper.
- **Page notes**: a transparent layer over one page of a PDF, DjVu or comic. The ink stays in place under zoom and pan.
- **Drawing sheets**: a panel over an EPUB, anchored to a passage rather than a page number, so it stays with the text when the font or margins change.
- **Document notes**: one list of everything in the book, including your sheets and page notes plus KOReader's own highlights, bookmarks and typed notes. You can filter it, export from it and jump back to any entry.
- **Pens**: six styles (Ink pen, Graphite, Marker, Round ink, Highlighter, Textured graphite), each in three widths, plus an eraser that cuts strokes in two and undo.
- **Export**: PDF, PNG or JPEG output of a page, a sheet, a notebook or every note in the book.

## Requirements

- An e-ink reader whose stylus KOReader can see.
- A current KOReader **development** build. Stable releases are not supported.
- Stylus drawing, page notes and drawing sheets need **KOReader v2026.07 or newer**. On older development builds only the original mode works: drawing directly on the screen with a finger.

## Install

1. **Back up KOReader's settings first.** There is no sync: notebooks and notes stay on the device that made them.
2. Download `justdraw.koplugin.zip` below.
3. Unzip it into KOReader's `plugins` directory, so the final path is `koreader/plugins/justdraw.koplugin/main.lua`.
4. Restart KOReader.

While reading, the plugin is at **Tools → JustDraw**. In the file browser, it is at **Tools → Notebooks**.

## Reporting a problem

**JustDraw → Stylus diagnostics** records a short trace of the plugin's pen decisions into KOReader's log. Traces contain coordinates only, never document or notebook contents. Please attach the log to an issue along with a short description of what happened.

## License

AGPL-3.0, version 3 only.

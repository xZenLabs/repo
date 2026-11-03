# Capitulares — KOReader plugin

**v1.0** · Portuguese (Portugal) / English · Unofficial, independent KOReader plugin.

**Capitulares** adds ornamental drop caps to EPUB books opened in KOReader, with per-book configuration and a visual font picker. It does **not** modify the EPUB files.

## Features

- Automatic drop caps at eligible chapter and subchapter starts.
- Optional **per-book** additional drop caps by paragraph count or **reflowed screen count**, restarting at each chapter.
- Ornamental fonts, reader fonts, or the book's font; live visual font samples.
- Size, horizontal and vertical spacing, per-font tuning profiles, default drop cap and reset.
- Supports EPUB layouts using nested `div` containers and text within `span` elements.
- Screen-based extra drop caps avoid dialogue paragraphs beginning with `—`, `–` or `-` and prefer eligible narrative paragraphs.
- Optional drop-cap-only color palette when KOReader detects and enables color display; per-book setting and an **Original** option.
- Accented letters are preserved in the document; the decorative glyph can be normalized when a font lacks an accent.

**Limitation:** Reflow changes page boundaries, especially after inserting drop caps. Some screens do not start any eligible paragraph, so exact one-per-screen behavior cannot be guaranteed in every EPUB.

## Install — one universal ZIP

Download **`Capitulares-v1.0.zip`** from **Releases**. It contains a single top-level directory: `capitulares.koplugin/`.

1. Fully quit KOReader and connect your e-reader to a computer.
2. Extract the ZIP **inside your KOReader plugins folder**:

   | Device | KOReader plugins directory |
   | --- | --- |
   | Kobo | `.adds/koreader/plugins/` |
   | Kindle | `koreader/plugins/` |

3. Check that `plugins/capitulares.koplugin/main.lua` exists, with no duplicate nesting.
4. Safely eject the device, restart KOReader, open a **DRM-free EPUB**, then select **Tools → Capitulares**.

There is no separate Kindle edition and no need for command-line tools. The plugin works inside KOReader's EPUB reader, not in the Kindle native reader or KOReader's file browser.

## Configure

Enable for the current book, then open **Customize drop cap**. Choose a font, size and spacing. Under **Advanced**, configure optional extra drop caps by **paragraphs** or **screens** and choose the interval. Screen intervals restart at each chapter. Dialogue starters are skipped for screen-mode extra drop caps.

On supported color screens, **Advanced → Drop-cap color** offers **Original** and nine colors. Changing a real document style may trigger one legitimate KOReader repagination prompt; repeated prompts while reading are not expected.

## Fonts

Fonts are not bundled. See **[FONTS.en.md](FONTS.en.md)** for font links and licensing notes. On Kobo, optional TTF/OTF files can be installed in `.adds/koreader/fonts/Initials/`.

## Compatibility

- Kobo Libra 2: main workflow tested with KOReader v2026.07.2.
- Kindle Colorsoft: EPUB structure and dialogue handling informed by device testing; behavior may vary by EPUB and KOReader configuration. Color rendering still needs comprehensive device validation.
- Designed for EPUB. No blanket compatibility guarantee for other formats or DRM-protected books.

## Code licensing

The code is publicly visible but **no open-source license has been selected**. Default copyright restrictions apply; publication does not by itself grant broad rights to modify or redistribute the code. External fonts have their own licenses.

Community project, not affiliated with the official KOReader team.

**Português:** [README.md](README.md) · **Changelog:** [CHANGELOG.md](CHANGELOG.md)

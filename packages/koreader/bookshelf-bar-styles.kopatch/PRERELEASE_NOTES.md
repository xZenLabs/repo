# v1.0.0-beta.2 · 2026-11-09

Bug fixes for colours:

- **Default colours no longer turn styles grey.** If Bookshelf's progress bar colour was set to its default (#404040), styles like Leaves were drawn in grey on colour screens. That default is now ignored, so each style keeps its own colours.
- **Picked colours now apply to outlines and details too.** For example, Sakura no longer keeps a pink outline when you pick a blue colour. Same fix for Leaves, Ivy, Constellation, Moon phases and Ribbon.

Thanks to everyone who reported these on r/koreader!

### Install
Download `2-bookshelf-bar-styles.lua` below and replace the old file in `koreader/patches/`, then restart KOReader.

# v1.0.0-beta.1 · 2026-11-08

First public beta of **Bookshelf bar styles**: sixteen custom progress bar styles for the Bookshelf plugin of KOReader.

**Minimal:** Dots, Segments, Ruler, Ribbon
**Nature:** Leaves, Ivy, Tendril, Bee trail, Sakura, Mushrooms
**Stationery:** Pencil
**Sky:** Constellation, Moon phases
**Seasonal:** Snowflakes, Fairy lights
**Animals:** Cat & yarn

### Install
Download `2-bookshelf-bar-styles.lua` below, copy it to `koreader/patches/` (on Kobo: `/mnt/onboard/.adds/koreader/patches/`) and restart KOReader. Then pick a style with **Bar: …** in the editor of a line containing `%bar`, and raise the bar height to around 200%.

### Help test this beta
It has not been tested on many devices yet. Useful things to check:
- **Colour screens** (Kobo Libra Colour, Kindle Colorsoft…): do the colours look right?
- **Greyscale screens:** are all styles readable in shades of grey?
- **Night mode:** do the soft edges and colours invert cleanly?
- **Bar height:** how do styles look at default height, ~150% and ~200%? Where do they stop being readable?
- **Bar width:** hero card vs list rows, portrait vs landscape.
- **Progress:** 0%, a few %, mid-book and 100% (the "finished" drawings).
- **Speed:** does the home screen redraw noticeably slower with these styles?
- **Custom colours:** fill and track colours picked in Bookshelf's menu.
- **Ghosting:** any leftover marks after page turns or refreshes on e-ink.

Please open an issue with your device model, KOReader and Bookshelf versions, the style name and a photo.

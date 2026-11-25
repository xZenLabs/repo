# v9.0.0 · 2026-11-25

## Page Scrubber — Patch notes

## Summary

Version 9.0 adds a new notes editor with the KiKome keyboard, a compact menu when you tap a highlight, and draggable cursors to adjust selections and highlights. The split menu gets a filter button (order, bookmarks, highlights or notes, style and color). There is also a new Automatic text size; Small, Medium and Large will be removed in a future release. You can now also add your own buttons to the selection menu: any button other plugins put in the highlight dialog can become its own button, with the icon you pick.

## What's new

### Notes menu (new) — Reading Pop-Ups → Notes menu
- **Menu notes**: a new editor for writing notes, with a gray rounded field, **Cancel** / **Save** in the bottom corners and **Paste** for the selected text. Tap outside to cancel. Falls back to KOReader's dialog if it fails to load.
- **Menu on highlight tap** (a compact pill next to the highlight: Delete, Style, Note, Copy, More) moved here from *Selection menu*.
- Both are **off by default**, but turn on by themselves if the Scrubber Selection Menu is already enabled.
- **KiKome keyboard** (on by default): used in the note editor and the *Export as…* prompt. It has ñ and accents, slide on the space bar to move the caret, and hold delete to clear. Turn it off to go back to KOReader's keyboard.

### Selection menu and cursors
- Cursors at each end of a selection (and of a highlight): drag them to adjust it.
- **Auto (follows selection)** menu position: above the selection, or below if there is no room.
- **Add button**: turn any button other plugins add to the highlight dialog (under *More*) into its own button, and pick an SVG icon for it.
- Dictionary and Selection Menu visual resign.

### Split menu
- New **filter button**: order, show (All / Bookmarks / Highlights / Notes), highlight style and color. It turns black while a filter is on.

### Look and feel
- KiKome-style dialogs (list picker, bottom sheets, toasts, SVG picker) replace KOReader's pop-ups, and fall back to them if they fail to load.
- *Reading Pop-Ups* is now split into submenus: **Dictionary**, **Selection menu** and **Notes menu**.
- New **Automatic** text size, matched to KiKome.

> [!IMPORTANT]
> **Small / Medium / Large text sizes will be removed in a future release.** Try **Automatic** (Settings → Text size) and tell me if you don't like it before they go.

### Other
- Spanish strings for everything new.


## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

# v8.6.1 · 2026-11-21

## Bug Fixes

### Text size (Appearance) crash
- Changing **Text size** reopened the scrubber through `onClose()`, which left deferred tasks (page jump + full refresh) running while the new scrubber was being built. The old instance is now closed immediately without jumping, and the new one is created inside a protected call. A failure is logged instead of crashing KOReader.
- The reopened scrubber now keeps its view mode, tab, page and origin. Before, it read fields that don't exist and fell back to the defaults.

### Floating dictionary freeze (Kobo)
- If the floating popup failed to build, the error was silently swallowed and no popup appeared, leaving the lookup stuck with the word still highlighted. It now falls back to KOReader's native popup and logs the error.
- After 3 consecutive failures, the floating popup is skipped for the rest of the session.

## Notes
- Both fixes are hardening based on code review. I couldn't reproduce the crashes, so please report back if they persist.
- If they do, attach `crash.log` (in the KOReader folder) and the list of installed dictionaries.

## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

# v8.6.0 · 2026-11-21

# Patch Notes

## Summary

This update adds a **Swipe Up menu** to Reading Pop-Ups and unlocks every KOReader typography option in the Quick Menu, so replacing KOReader's own typography menu never leaves you without access to them. The **Aa tab** was redesigned for PDF/CBZ, gained a **More** button in EPUBs, and now lets you see the page behind it while you change settings.

---

## Swipe Up menu in Reading Pop-Ups

Choose what opens when you **swipe up from the bottom edge**, instead of KOReader's typography menu.

**Settings > Reading Pop-Ups > Swipe up to:** Off *(default)*, Grid, Simple Grid, Index, Index (Table of Content), Multi-Grid, Quick Menu.

Since this can replace KOReader's typography menu, the **Aa tab** now exposes all the format options KOReader has. If you cancel KOReader's own menu, you are never left without them.

---

## Aa tab

**Live preview:** opening the Aa tab now keeps the page visible in the background, so you can see your changes applied automatically.

### PDF / CBZ

A completely different tab, adapted to fixed documents: three submenus with icons and a summary of their current value, plus the view / rotate row.

| Entry | Options |
| --- | --- |
| **Page** | Rotation, Page crop, Margin, Auto straighten, Fit zoom to, Fit, Rows, Zoom factor, Direction |
| **Reflow** | Reflow on/off, Font size, Word gap, Line spacing, Alignment |
| **Visual** | Contrast, Saturation, White threshold, Dewatermark, Background cleanup, Dithering, Render quality *(Reflow on)* |

Order follows KOReader (Page first, Rotation first inside it). Options that don't apply to the current document are hidden.

### EPUB: new More (⋮) button

Placed at the right end of the bottom row, with every option that was missing:

- **Main list:** Rotation, Margin L/R, Margin T/B.
- **View options:** Render mode (how the layout engine renders the book), Zoom dpi (scales images and size-based CSS), Word spacing, Word expansion (how much words may stretch in justified text).
- **Style options:** Contrast, Font weight, Font hinting, Font kerning, Embedded style (publisher's styles), Embedded fonts (the book's own fonts), Image scaling (fast or best quality).

---

## Option picker

A new picker opens for each option in the Aa tab and its submenus:

- Shows a description of the option and of each value.
- Includes a star to set the option as your default.
- Toggles (Reflow, Background cleanup, Embedded style, Image scaling, ...) keep their switch in place; tapping the **name** opens the picker with the explanation.

---

## Quick Menu visual refresh

A more subtle and elegant design, with buttons on a soft gray background, and icons at the start of the submenu entries.

## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

# v8.5.0 · 2026-11-13

## What's new

### Quick menu redesign
- New **brightness bar** with percentage.
- **Aa** menu: for EPUBs, choose 1 or 2 columns; for PDFs, switch between paged and continuous view. New **rotate** button.

### New option: Rounded style
- New **Rounded style** submenu in Appearance, with one toggle per view: Grid, Simple Grid, Multi Grid and Split menu. Enabled by default.
- Turn a toggle off to get square page corners in that view.

### Split menu
- Redesigned split menu.
- Icons in the right-hand list now show the highlight color as a background when the style uses several colors.

### Compatibility
- The dictionary popup now shows buttons registered by plugins loaded before Page Scrubber, such as OfflineTranslate's "Learned" button. Thanks to: #9 

### Fixes
- Fixed the "!" placeholder that could appear on grid thumbnails after returning from the split menu. Thumbnails whose request got stuck are now retried in the background.

## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

# v8.4.0 · 2026-11-09

## 8.4 Search button in quick menu and more 

### **Quick Menu**
* Added a **Search** button to the bottom row (light · search · actions · settings) to immediately trigger KOReader's text search.

### Kikome and bookshelf compatibility
- Instant exit from the **Library** button when KiKome or Bookshelf is the "Start with" home: the book is parked instead of closed, so the library shows with no loading wait.
  - Start with = KiKome: needs *Instant exit from books* on and the book opened from KiKome.
  - Start with = Bookshelf: needs hot parking on and the book opened from the shelf.
- Any other "Start with" value, a missing or disabled plugin, an option turned off, or a book opened from elsewhere exits exactly as before.

**Table of Contents (Vertical & Horizontal)**
* The current chapter row (marked by the gray dot) now displays the time left to finish the chapter, mirroring KOReader's footer logic and chapter hierarchy.
* Adaptive label sizing: The time left indicator hides if reading stats are unavailable/zero, and falls back to a compact format (e.g., "12m" instead of "12m left") on cramped screens.
* Smart 2-line expansion: If the text still won't fit, the row expands to two lines to prevent harsh title truncation, placing the dot and time left at the end of the second line. "Page N" stays vertically centered.

**Right Split Panel (Vertical)**
*Small visual tweaks in formating. 



## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

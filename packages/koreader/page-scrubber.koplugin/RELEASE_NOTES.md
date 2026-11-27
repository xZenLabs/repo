# v9.0.1 · 2026-11-26

## Translations & dates

This update is all about language support. Thanks to @danieldcastro  for the Portuguese translations (#11 ) and the detailed i18n review that led to most of the fixes below!

### Added
- **Portuguese (pt / pt_BR) is now complete.** Every string in the plugin is translated.
- **Dates follow each language's own order.** The date format is now translatable, so Spanish shows "26 de mayo de 2026" and Portuguese shows "26 de maio de 2026". Other languages are unchanged.
- **"May" is translated correctly.** The full and abbreviated month now have separate translations ("mayo" / "may", "maio" / "mai").

### Improved
- **One shared translation loader.** Every module now reads the same files, so region files like `pt_BR.po` and `zh_CN.po` are used across the whole UI, not just in the main menu.
- **Grid and table of contents landscape views are now translated** (they were always shown in English before).
- **Quick menu, updater and dictionary use the plugin's own translations**, and fall back to KOReader's when a string is missing.
- **Spanish:** about 80 missing strings added, including the render option descriptions in the quick menu and all the update messages. Duplicate entries removed and a few wordings corrected ("Añadido el", "Menú de selección del Scrubber").
- **Portuguese:** 16 extra strings added (highlight colors, "Delete note", "Paste", "Searching…") on top of the contributed translations.

### Fixed
- A table of contents fallback title was written in Spanish in the code, so it showed "Capítulo" in every language. It's now translated properly.
- The back button that appears when you zoom into an image had a very thick outline on Kindle. It now has a thinner outline in both the normal and expanded panel.

## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

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

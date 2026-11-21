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

# v8.3.0 · 2026-10-26

## 8.3 New features: Breadcrumb pins on the progress bar. 

- **Breadcrumb pins on the progress bar.** New option *Breadcrumb pins in slider* under Settings → Layout → Progress bar (pin icon). When you jump from one page to another, the origin page is saved as a pin on the bar.
  - Up to 3 dots are shown: the **origin** in dark gray, always visible (tap it to return there), and the **2 most recent** history pins in black.
  - Works on the scrubber bar, the grids, and the TOC view.
  - Mutually exclusive with the bookmark dots: when the option is on, the bar shows only breadcrumbs.

### Details:
- Pins are stored per book, in the document's metadata.
- In EPUB, each pin also stores its position in the text (xpointer). If you change font, margins, or DPI, the pin still points to the same place.

## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

# v8.2.0 · 2026-10-21

## What's new

### New: Study Mode
- When enabled, a **Study** button appears in the split menu (it can also be opened with a gesture). It lets you study your annotations with the same spaced-repetition method used by apps like Anki: every annotation is a card, and you rate it **Again**, **Good** or **Easy** depending on how hard it was. The easier a card is, the longer it takes to come back in your next session.
- When you finish a session, **Review mode** unlocks: you can browse all your annotations, but without the rating buttons, so your progress is never modified.
- On every card you can **tap the page** to jump straight to that page in the book and read the context. You can also **undo** a card if you rated it wrong.
- **How it works:** it's off by default. You can enable it for all books or only for a specific folder, like School, University or Work.
- The study data of each book lives inside that book's `.sdr` folder.
- You can delete the Study progress of each book from **Settings > Study Mode > Reset Study Progress**.
- All the text in the Study / Review card follows **Settings > Appearance > Text size**.

### New: Custom icons
- Now in **Settings > Appearance > Custom icons**: add your own icons!
- Tap **+** on any SVG, browse your KOReader files to the folder where your icon is, and **long-press** the SVG you want to use.
- You can go back to the original SVG individually, or reset all of them at once.
- Prefer to do it manually? Drop your SVGs in `koreader/settings/page_scrubber/icons/` using exactly the same file names as the plugin's icons (they are case-sensitive), then reopen the scrubber. Your icons are kept when the plugin is updated.

### Settings improvements
- The **Favorite fonts**, **System font** and **Add scrubber action** menus were updated to match the new settings design.
- Settings (and Study mode) can now be used with physical buttons on **non-touch devices**. *Feedback is welcome to check it works as intended.*

### Quick Menu
- Small redesign so everything looks bigger and fits better.
- **New Status Row:** time, Wi-Fi and battery (and a Study mode notification if Study mode is enabled). Enable it in Settings > Quick Menu > Status Row 
- Fixed the frontlight toggle.

### Updated the page scrubber Updater: 
-Now it displays a nice window showing the full patch notes and other changes.

- Updated spanish and Portuguese. 
- **Help translate:** If you'd like to help update the translation into your language, contributions are welcome!

## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

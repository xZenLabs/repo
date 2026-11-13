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

# v8.1.0 · 2026-10-18

## Settings & Split Menu Redesign

### Visual updates
- **Settings menu redesign:** new header with back and close buttons, options grouped into sections, the current value shown on the right of each row, and a cleaner, lighter look.
- **Split menu refresh:** the selected row is now a rounded pill, the pinned row has a softer selected state, the color filter arrows are chevron icons, and page numbers are centered. Landscape got the same changes.
- The book title and chapter name now match the size of the "Library" label, and the selection menu has a thicker outline.

### New book title style: Bar
- Under **Settings > Appearance > Top bar > Book title style** there is a new **Bar** style. It draws the book title on a full-width white bar, vertically centered.
- Turn on **Top bar separator line** together with the **Bar** style and the result looks very similar to the Kindle's own top bar.

### Selection menu
- **New option: Size of selection menu** (Small / Medium / Large) under Settings > Reading Pop-Ups. It scales the icons, the buttons and the outline. Medium is the previous size.

### New: Advanced settings
A new **Advanced** submenu (Settings > Other > Advanced):
- **Settings**
  - **Back up settings:** saves all your PageScrubber options and your favorite images to `page_scrubber_backup.lua` in KOReader's `settings` folder.
  - **Restore settings from backup:** brings back the options and favorite images saved in that file. To restore on another device, copy the file to the same folder first.
  - **Reset all settings:** back to defaults. Asks for confirmation, and also clears your favorite fonts, quick actions and favorite images. Back up first if you want to keep them.
- **Cache**
  - **Clear image cache:** deletes the scan cache of the Images tab (the current size is shown next to it). Your favorite images are kept.
- **Updates**
  - **Check for updates:** looks for a newer release on GitHub, shows its notes and installs it from the reader. It keeps a backup and restores the previous version if the install fails. Restart KOReader when it finishes.

## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

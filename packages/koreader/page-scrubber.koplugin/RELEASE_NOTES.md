# v7.7.7 · 2026-10-09

## New Features

### Split Menu
* **Color filter:** Now, in the Highlights and Notes tab, if there are annotations with more than one color, a new triangle icon will appear allowing you to filter entries by color.
* **Individual color selector:** A new circular button was added to the highlight type editing row. This button allows you to directly change the color of a specific annotation (works for all styles except invert).

### Selection Menu
* **Quick color menu:** By long-pressing any highlight style (Highlight, Underline, or Strikethrough), the new color menu will now unfold to let you choose which color to paint the annotation with.

---

## Fixes & Improvements

### Interface & Behavior
* **DPI pagination fix:** Fixed a critical bug where changing the screen DPI caused selecting an annotation in the Split Menu to take you to the wrong page.
* **Optimized Split Menu loading:** The plugin now uses the same logic as KOReader's native listing. This fixes the excessive loading times when opening the menu after rotating the screen between portrait and landscape.
* **Native notes integration:** Tapping the button to add text notes will now directly invoke KOReader's native menu.
* **Visual refinement:** Slightly reduced the thickness of the buttons within the Split Menu and refined the SVG icons overall for a more polished look.

### Performance
* **Reduced lag when turning pages:** Rewrote the pagination logic to prevent bottlenecks and extreme slowdowns.
  * **Preload queue optimization:** Each new tap now cancels older preload tasks that were still in the queue. Additionally, the engine now prioritizes loading pages in the direction you are navigating.
  * **Concurrency control (Semaphore):** Implemented a semaphore system. If the current page hasn't finished rendering, page turns are blocked, preventing background processes from piling up and freezing the device.


## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

# v7.7.3 · 2026-10-06

# What's new!

##  Multi Grid: Now you can select 9 pages!
- New option under **Layout → Multi Grid: Show 9 pages**. Shows 9 pages (3x3) instead of 6, with the current page in the center. Works in both portrait and landscape.
- Small visual tweak to the index: added a dithering effect for a nicer look (based on `hatching.lua` from ZenOS).
- Added visual feedback when pressing the `<`, `>` and `X` buttons in Simple UI mode.

##  <-- Library button
The Library button now it redirects you to the path you have asigned as 'Start With' instead of simply going to the file browser. That means: Simple UI Homescreen, Bookshelf, or history... 

## Fixes:

- **Multi Grid and Simple Grid:** CBZ and PDF pages now respect their true size more accurately and no longer shrink or stretch awkwardly to fit the grid.
- The same fix was applied to the 3-page Grid in **Landscape** mode.

## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

# v7.7.2 · 2026-10-04

## Bug Fixes in dictionary 
- Fixed the Highlight button doing nothing in the dictionary pop-up.
- Fixed plugin buttons in the dictionary pop-up (text mode) not receiving the selected text.

## Installation
1. Download the zip named `page_scrubber.koplugin-<version>.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

# v7.7.1 · 2026-10-03

### Bug Fix
- Fixed a crash when tapping the AI button with AI Assistant v1.18 (thanks @DerailleurAgile, #7).

## Installation
1. Download `page_scrubber.koplugin-vX.Y.Z.zip` from the [latest release](../../releases/latest) (under Assets, not "Source code").
2. Unzip it and copy the `page_scrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, replace the folder. To uninstall, delete it (and `koreader/patches/2--page-scrubber-font.lua` if you used the system font).

# v7.7.0 · 2026-10-03

## What's new

### System font selector
Page Scrubber can now change KOReader's system (UI) font from **⚙ Configuration → Appearance → System Font**. The list shows each available family and flags the ones without a bold variant ("no bold"), that only ship bold ("bold only"), or that only ship italics ("italic only"). The change applies after a restart.

**How it works:** the first time you open the selector (or pick a font), the plugin copies a small file, `ui_font_patch.lua`, to `patches/2--page-scrubber-font.lua`. After a plugin update, the patch is refreshed the next time you open the selector, and the new version takes effect on the following restart.

**Why a patch:** KOReader's widgets fix their font when they load, and plugins load after the core interface. Applying the font from the plugin would only reach part of the UI. A patch runs before everything else, so the font covers the whole interface.

**Why the patch also works on its own:** it has its own **System font** entry in KOReader's native Settings menu (file manager and reader), where you can enable/disable the replacement and pick a font. If you ever remove the plugin, you can still manage or turn off the font from there. Both use the same settings.

**Compatibility**
- **SimpleUI:** if SimpleUI's custom font is active, Page Scrubber doesn't touch the font and discards its own choice. The option stays visible and tells you the font is managed by SimpleUI.
- **ZenOS:** the option is disabled when ZenOS is detected.

> To remove the font patch completely, delete `patches/2--page-scrubber-font.lua`.

### Menu tweaks
- Small polish to our entries in KOReader's native menus so they look more consistent with the rest of the system (⚙ icon and separators).

### Fixes
- Fixed Wiki and Search buttons doing nothing in the dictionary pop-up and selection menu (thanks @DerailleurAgile, #6).
- Fixed ghosting on the bottom bar of the index.

### Translations
- Spanish updated with the new strings and updated more languages.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/33009934/page_scrubber.koplugin.zip)

# v7.7.3 · 2026-10-06

# Update 7.7.3

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

# v7.6.0 · 2026-09-30

### What's New

#### Quick Menu Enhancements
* **Typography Tab**: Added a dedicated Typography tab to the Quick Menu. You can now select your favorite fonts, adjust font size, and fine-tune line spacing on the fly.
* **Gesture Support**: The Quick Menu can now be assigned to a gesture (via Dispatcher) to open it directly while reading.
* **Toggleable Quick Menu**: Added a new setting to enable or disable the Quick Menu entirely, keeping things clean for Page Scrubber purists who only want page scrubbing.
* **Default Starting Tab**: Added an option in settings to choose whether the Quick Menu opens by default on the standard actions tab or the new Typography tab.
* **Instant Style Switching**: Changing styles and typography options via the Quick Menu now updates almost instantaneously without loading screens.

#### Selection & Highlights Menu
* **Instant Highlight Style Changes**: Changing highlight styles in the selection/split menu is now seamless—no more loading screens, refreshing almost instantly.

#### Appearance & Settings Polish
* **Top Bar Separator Line**: Added a new toggle in the Appearance menu to draw an optional separator line beneath the top bar.
* **Visual Improvements**: Refreshed the settings menu layout and visual styling for a cleaner, more intuitive look.

#### Localization & Languages
* **New Languages**: Added full translations for Norwegian (`nb`) and Ukrainian (`uk`).
* **Translation Updates**: Updated all existing translation catalogs (German, Spanish, French, Hindi, Italian, Japanese, Dutch, Polish, Portuguese, Russian, Turkish, and Simplified Chinese) to cover the new menus and settings strings.

---

### Bug Fixes

* **TOC Page Count**: Fixed inaccurate page count calculations when opening the Table of Contents via the Dispatcher.
* **Dictionary Double Pop-Up**: Fixed a bug where long-pressing a word occasionally triggered the dictionary pop-up twice.
* **Dictionary Text Bounds**: Fixed font size calculation in the dictionary to ensure "shrink to fit" renders and paints text properly.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32851569/page_scrubber.koplugin.zip)

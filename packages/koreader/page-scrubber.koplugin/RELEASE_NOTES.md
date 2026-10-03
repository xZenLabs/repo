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

# v7.5.0 · 2026-09-28

### FastDict Engine
 * **Instant Dictionary** Lookups: Added an in-memory StarDict lookup engine for significantly faster word searches.
 * Reliable Fallback: Retained full compatibility with the native dictionary engine for missing or advanced queries.
Improvements on Dictionary Pop-Up
 * **Dynamic Window Sizing (Shrink-to-Fit)**: The popup automatically shrinks to fit short definitions, getting rid of awkward empty space.
 * **Reorderable Dictionary Buttons:** Custom order and visibility toggles for all bottom actions directly from settings.
 * X-Ray Integration: Integrated X-Ray directly into the dictionary action bar (set to the end by default and if not just move it with the chevron wherever you like).
 
### Improvements on Selection Menu
 * **Custom Action Ordering**: Added full sorting and toggle support for every tool in the text selection toolbar.
 * Smart "More" Button: Easily move the expansion button (...) to appear either first or last on the bar.
 * X-Ray in Selection: Enabled sorting and toggling for X-Ray alongside standard selection tools.

### Scrubber Actions & Settings UI
 * **Reorderable Quick Actions**: Easily rearrange custom launcher actions with up/down arrows or delete them using the trash icon.
 * Adaptive SVG Chevrons: Replaced plain text arrows with native chevron icons that dynamically hide when an item cannot move further.
 * Stability & Touch Fixes: Isolated modal menus to eliminate ghost touches and accidental window closures, keeping menus properly layered during transitions.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32747242/page_scrubber.koplugin.zip)

# v7.4.9 · 2026-09-27

### Stable pages should be more... stable

**Stable Pages (*Pagemap*)**
* **Pinpoint Accuracy (Zero Drift):** Eliminated the 1 to 5-page drift from earlier math estimations; stable pages now map with exact 1:1 precision against the physical print edition.
* **Correct Page Totals:** Synchronized page counts so Roman numeral front matter no longer inflates the total (e.g., displaying `879 / 879` instead of `879 / 905`).
* **Instant Mid-Screen Updates:** When a new physical page begins mid-screen, the label updates immediately rather than waiting for the next page turn.

**Six Grid Mode**
* **Fixed RTL Traversal:** Left and right buttons turn pages in the correct direction when reading right-to-left.
* **Boundary Auto-Hide:** Block jump buttons automatically disappear upon reaching the start or end of the book.
* **Simplified Return Button:** Removed extra arrows from the origin button in landscape, standardizing it to a clean `Page X` label matching portrait mode.

**Landscape & Views**
* **Auto-Hiding Chapter Controls:** Chapter jump buttons cleanly disappear when reaching the first or last chapter across all landscape layouts (Six Grid, Grid, Split, and Simple Grid).
* **UI Glitch Fix:** Anchored slider geometry to fixed margins, preventing the bottom bar from turning completely blank when chapter buttons hide.
* **No More Ghost Cards:** Eliminated empty white placeholder cards with loading dots beyond book boundaries in Landscape Grid.

**Table of Contents (ToC)**
* **Clean Scrubbing State:** The chapter page counter hides its number and displays only the icon while dragging the slider; the exact count appears instantly upon release over the active chapter.
* **Adaptive Landscape Pagination:** If chapter list pages overflow toward side buttons (✕ and shutter), pagination dots automatically convert into a compact numeric pill (`X / Y`) matching portrait mode.
* **Clean Navigation Controls:** Chapter list jump buttons (`<<`, `<`, `>`, `>>`) dynamically hide at list boundaries.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32694557/page_scrubber.koplugin.zip)

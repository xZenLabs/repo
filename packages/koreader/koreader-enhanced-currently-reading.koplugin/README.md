# SimpleUI Plus (v3.0.0)

<p align="center">
  <img src="_screenshots/1.png" alt="Screenshot 1" width="48%">
  <img src="_screenshots/2.png" alt="Screenshot 2" width="48%">
</p>
<p align="center">
  <img src="_screenshots/3.png" alt="Screenshot 3" width="48%">
  <img src="_screenshots/4.png" alt="Screenshot 4" width="48%">
</p>
<p align="center">
  <img src="_screenshots/5.png" alt="Screenshot 3" width="48%">
  <img src="_screenshots/6.png" alt="Screenshot 4" width="48%">
</p>
# 📖 SimpleUI Plus (`simpleui_plus.koplugin`)

**SimpleUI Plus** is the next-generation evolution of Enhanced Currently Reading — transformed from a standalone `module_currently_yanllsama.lua` file into a full, independent KOReader plugin (`simpleui_plus.koplugin`) for **SimpleUI**.

It integrates cleanly with SimpleUI at runtime via in-memory hooks without modifying any `simpleui.koplugin` files on disk, delivering a multi-book Cover Deck, 39 reading metrics, 45 progress visual variants, color screen (RGB32) theming, 2D live positioning, and a built-in profile manager.

---

##  Highlights (v3.0.0)

* **Standalone Plugin & Setup Wizard**: Works alongside `simpleui.koplugin` with zero core file edits and includes a first-run setup wizard (`wizard.lua`).
* **Cover Deck (1 / 3 / 5 / 7 Books)**: Stacked multi-book cover deck with vertical swipe and tap-to-switch between recent or TBR books.
* **39 Statistics Metrics (7 Groups)**: Chapter pages/time left, highlights & notes counts, today/week/month/year/all-time stats, reading streak, estimated finish date, and a compact live Stat Picker (`stats_editor.lua`).
* **45 Progress Visual Variants**: 15 Ring styles (`15%–150%`), 15 Vertical Bar styles, and 15 Horizontal Bar styles backed by daily, weekly, monthly, and yearly goals, plus a detailed **Book Stats** popup (`module_currently_books_stat.lua`).
* **Color Screen (RGB32), Borders & Headers**: Custom colors for text, backgrounds, borders, and visuals, `0–30 px` corner radius, `1–4` columns × `1–7` rows, and 10 category header styles.
* **2D Live Position Editor & Fluid Previews**: Single-window X/Y slider with `-`/`+` fine-tuning, selectable window sizes/positions, partial e-ink repaints, and landscape orientation support.
* **Profile System**: 12 built-in presets (`default_profiles.lua`), save/lock/export, bulk-purge unlocked presets, and Quick Profile Switch.

---

##  How to Install

1. **Remove the Old Module (If Installed):**
   If you previously placed `module_currently_yanllsama.lua` manually inside `simpleui.koplugin` (or `simpleui_ext.koplugin`), delete it to avoid conflicts.
2. **Copy the Plugin Folder:**
   Copy `simpleui_plus.koplugin` from this repository into KOReader's `plugins` directory:
   * **Kobo:** `.adds/koreader/plugins/simpleui_plus.koplugin`
   *(Requires **SimpleUI** to be installed and enabled under `plugins/simpleui.koplugin`.)*
3. **Restart KOReader:**
   On startup, the **SimpleUI Plus Setup Wizard** will guide you through enabling the module. You can also enable or customize it anytime from **SimpleUI → Homescreen Settings → Modules**.

---

##  Change Log

**v3.0.0 (Latest)**
* **Architecture & Setup**: Transformed from a single drop-in module (`module_currently_yanllsama.lua`) into a full KOReader plugin (`simpleui_plus.koplugin`) that integrates via in-memory hooks (`main.lua`) without modifying `simpleui.koplugin` files on disk; added a first-run Setup Wizard (`wizard.lua`).
* **Cover Deck & Layout**: Replaced the single cover with a 1 / 3 / 5 / 7 book Cover Deck (swipe vertically or tap stacked covers to switch recent/TBR books); added cover spacing, cover size, Stats/Visuals width ratio (`40%–85%`), and side padding controls.
* **Statistics & Grid**: Expanded from 10 to 39 metrics across 7 groups (chapter left, highlights/notes, today/week/month/year/all-time, streak, estimated finish); added a live docked Stat Picker (`stats_editor.lua`), `1–4` columns × `1–7` rows, and 10 header styles.
* **Progress Visuals & Goals**: Expanded from 6 bars to 45 visual variants (15 Rings `15%–150%`, 15 Vertical Bars, 15 Horizontal Bars) with daily/weekly/monthly/yearly page, time, and book goals, plus a detailed Book Stats window (`module_currently_books_stat.lua`).
* **Appearance, Positioning & Responsiveness**: Added RGB32 color theming, `0–30 px` rounded borders, a 2D X/Y Live Position Editor (`position_editor.lua`) with Small/Medium/Large sizes and Bottom/Center/Top placement, fluid partial e-ink repaints, and landscape orientation support.
* **Profiles**: Added a full profile manager with 12 built-in presets, save/lock/export, bulk-purge of unlocked presets, and Quick Profile Switch.

**v2.0.0**
* **Added**: Full CoverDeck integration with swipe up/down gesture support.
* **Added**: Vertical data bars tracking daily page goals and total book progress.
* **Added**: Complete UI overhaul with rounded frames and a boxed statistics layout.
* **Added**: Dedicated "Text and Font Settings" menu to fully customize typography (font face, size, and weight).
* **Improved**: Restructured the Settings Menu into logical sub-menus (Grid Settings, Bar Settings, etc.).
* **Renamed**: Official module name updated to `module_currently_yanllsama.lua` for use with `simpleui_ext.koplugin`.

**v1.0.0 (Original Release)**
* Initial release with dynamic grid system.
* Basic statistic visibility and sorting controls.
* Smart Info Screen for book summaries.

---

*Developed by Yanllsama for the KOReader and SimpleUI community. Licensed under the MIT License. Feedback and Pull Requests are always welcome!*

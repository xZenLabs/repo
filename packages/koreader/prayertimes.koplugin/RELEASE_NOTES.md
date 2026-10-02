# v1.2.0 · 2026-09-08

## Prayer Times v1.2.0

**Previous Version:** v1.1.0

---

### ✨ New Features

**1. Moroccan Calculation Method (19°/17°)**
- Added the Moroccan calculation profile (Fajr 19°, Isha 17°) for Morocco and Mauritania.
- Auto-selected when choosing any Moroccan or Mauritanian city.
- Marked as `pending_primary_source_validation` — exact agreement with official Moroccan timetables may require per-prayer corrections.

**2. IAC Standard Method**
- Added the International Astronomical Center standard profile.
- Latitude-aware Isha angle: 18° below latitude 45°, 17° at or above 45°.
- Based on the IAC Accurate Times documentation.

**3. Automatic Asr Madhhab Selection**
- The plugin now auto-selects the Asr jurisprudence based on country.
- Hanafi (double shadow) for Pakistan, India, Bangladesh, Afghanistan, and Turkey.
- Shafi (single shadow) for all other countries.
- Users can still override manually.

**4. Per-Prayer Manual Corrections**
- New submenu: **Calculation Settings → Per-Prayer Corrections**.
- Adjust each prayer independently by ±30 minutes.
- Useful for matching local mosque timetables that include administrative offsets.

**5. City Search**
- Tap **🔍 Search for a city...** at the top of the location list.
- Type in Arabic or English to instantly filter 200+ cities.
- Results show city name with country label.
- Original nested country menu preserved for browsing.

**6. Arabic-Indic Digits**
- When the interface language is Arabic, all numbers display as ١٢٣٤٥٦٧٨٩٠.
- Applies to clock, Gregorian date, Hijri date, prayer times, countdown, and status bar.

**7. High-Latitude Support**
- Five configurable estimation rules for polar regions:
  - Real times only (shows --:-- if unavailable)
  - One-seventh of the night
  - Middle of the night
  - Angle-based portion of night
  - Fixed minutes from sunrise/sunset
- Auto-enables "one-seventh" for cities above 48° latitude.
- Includes an **ℹ️ What is this?** explanation button.

**8. Ramadan Mode (Umm al-Qura)**
- New submenu: **Hijri and Fasting → Ramadan Mode**.
- Three options: Automatic (tabular Hijri), Force Ramadan (120 min), Force Normal (90 min).
- Controls the Isha interval for the Umm al-Qura method.

**9. DST Clock Toggle**
- New option: **Set Location → Daylight Saving Time → Apply DST to plugin clock**.
- When enabled: plugin clock = Kindle clock + DST offset.
- When disabled: plugin clock = Kindle clock exactly.
- DST always affects prayer calculations regardless of this setting.

**10. Location Coordinate Guide**
- Integrated step-by-step guide using timesprayer.com.
- Shown automatically when tapping **Add new location**.
- Available in both Arabic and English.

---

### 🐛 Bug Fixes

**1. Screen Brightness Lock (Critical)**
- Fixed: screen brightness remained stuck at the plugin's custom level after closing the widget.
- Brightness is now properly restored via `onCloseWidget()` and `destroy()` lifecycle methods.

**2. Background Timer Memory Leak (Critical)**
- Fixed: refresh and alert timers continued running after widget closure.
- All timers are now unscheduled on close.

**3. Fasting Reminder Wrong-Day Bug (High)**
- Fixed: timezone double-shift caused fasting reminders to appear on incorrect days.
- Now uses UTC-based time parsing (`os.date("!*t")`) to avoid system timezone conflicts.

**4. Custom Locations Lost on Update (High)**
- Fixed: user-added locations were saved inside the plugin directory and wiped on update.
- Custom locations now stored in KOReader's persistent settings directory (`prayertimes_custom_locations.lua`).

**5. Missing Device Import (Medium)**
- Fixed: `Device` module was not imported in `widget.lua`, causing brightness functions to silently fail.

**6. Namespace Collision Prevention (Medium)**
- All internal modules renamed with `prayertimes_` prefix to prevent conflicts with KOReader core files.
- Eliminates `attempt to index upvalue (a boolean value)` crashes.

**7. Calculation Engine Improvements**
- Solar position now calculated iteratively for each prayer event (better accuracy).
- Equation of time properly normalized to [-12, 12) range.
- Input validation for coordinates, timezone, and calendar dates.
- Returns `nil, error` for invalid inputs instead of producing wrong results.

---

### ⚡ Performance Improvements

**E-Ink Display Optimization**
- Live clock mode now uses lightweight `"ui"` refresh instead of `"flashpartial"`.
- Eliminates visible screen flicker on e-ink displays during minute-by-minute updates.
- Initial launch still uses `"full"` refresh for a clean first render.

---

### 📁 Files Changed

| File | Change |
|------|--------|
| `main.lua` | New menus, search, corrections, DST toggle, location guide, error handling |
| `prayertimes_widget.lua` | Arabic digits, lifecycle teardown, e-ink refresh, DST clock |
| `prayertimes_calculation.lua` | Iterative solar position, 9 methods, input validation, metadata |
| `prayertimes_defaults.lua` | New settings, region_madhhabs, high-latitude defaults |
| `prayertimes_translations.lua` | All new translation keys in EN/AR |
| `prayertimes_fasting.lua` | UTC time parsing fix |
| `prayertimes_utils.lua` | Renamed for namespace isolation |
| `prayertimes_statusutils.lua` | Renamed for namespace isolation |

---

### 🔄 Migration Notes

- **No action required.** All existing settings are preserved automatically.
- Old settings files (`prayertimes_config.lua`) are fully compatible.
- If you previously selected a Moroccan city, the method will auto-switch to Moroccan on next launch.
- Custom locations are migrated to persistent storage on first launch.
- The `apply_dst_to_clock` setting defaults to `false` (plugin clock matches Kindle).

---

### 📥 Installation

1. Download `prayertimes.koplugin-v1.2.0.zip`
2. Extract to your KOReader `plugins/` directory
3. Restart KOReader completely
4. Access via **Tools → Prayer Times**

---

### 🙏 Acknowledgments

- Astronomical basis: Mohammad Shawkat Odeh / International Astronomical Center (IAC)
- Thanks to all users who reported bugs and requested features
- Special thanks to the KOReader community

**Full Changelog**: https://github.com/Mahmoudgomaa001/prayertimes.koplugin/compare/v1.1.0...v1.2.0

# v1.1.1 · 2026-09-07

## Release Notes – Prayer Times v1.1.1
**What's New**
Simplified Clock Display
The clock now always shows your device's system time. No more confusion with DST adjustments—what you see on the prayer times screen matches your device clock exactly.

**Full Changelog**: https://github.com/Mahmoudgomaa001/prayertimes.koplugin/compare/v1.1.0...v1.1.1

# v1.1.0 · 2026-09-07

## Release Notes – Prayer Times v1.1.0

### What’s New

- **Direct Font Preview**  
  Tapping any font in the font list now opens a full‑screen preview immediately—no extra submenu. The preview shows the actual Prayer Times screen with the selected font.

- **Overlay Controls**  
  The preview opens with a floating overlay at the bottom that lets you:
  - Switch to previous/next font (◀ ▶)
  - Adjust font size (– / +)
  - See the current font name
  - Apply the font + size without leaving the preview (saves and continues)
  - Cancel to close and return

- **Per‑Language Font Sizes**  
  Each font can have a separate recommended size for Arabic and English. The plugin remembers the size you set for each font in each language, so it renders correctly in both.

- **Removed Standalone Font Size Menu**  
  The old “Font size adjustment” item has been removed because it’s now handled inside the preview overlay—simpler and faster.

- **Swipe Down to Close**  
  In preview, swiping down closes the preview without needing the overlay.

- **Stability Improvements**  
  Fixed screen refresh after closing preview, resolved crashes from overlay interactions, and ensured the preview always renders correctly.

- **Battery‑friendly Reminder**  
  The plugin still only shows when opened or when the device wakes (if enabled). It does not run in the background.

### Upgrade Instructions

If you’re updating from v1.0.x:

1. Delete the old `prayertimes.koplugin` folder from `koreader/plugins/`.
2. Copy the new `prayertimes.koplugin` folder into the same location.
3. Restart KOReader completely.

**Note:** The settings file is automatically migrated. Existing font preferences will still work, but the new per‑language sizes will apply once you save a new size in the preview.

### Download

**prayertimes-koplugin-v1.1.0.zip**

---

**Full Changelog:** [v1.0.1...v1.1.0](https://github.com/Mahmoudgomaa001/koreader.prayertimes/compare/v1.0.1...v1.1.0)

# v1.0.1 · 2026-09-06

## Release Notes – Prayer Times v1.0.1

### Initial Release

The first stable release of the Prayer Times plugin for KOReader.

### Features

- ✅ Accurate prayer time calculation (7 methods: MWL, Egyptian, Umm al-Qura, Karachi, ISNA, Jafari, Tehran)
- ✅ Asr jurisprudence selection (Shafi/Hanafi)
- ✅ Hijri calendar with manual adjustment
- ✅ Fasting day reminders (Mondays/Thursdays, White Days, Ashura, Arafah, Six Shawwal)
- ✅ Custom fonts support
- ✅ Bilingual Arabic/English interface with RTL
- ✅ Battery-friendly design (no background running)
- ✅ Location database with auto method suggestion
- ✅ Add custom locations manually
- ✅ Alert options (flash, message, frontlight pulse)

### Installation

1. Download the ZIP file below.
2. Extract it.
3. Copy the `prayertimes.koplugin` folder into `koreader/plugins/`.
4. Restart KOReader completely.

### Documentation

- [README](https://github.com/Mahmoudgomaa001/prayertimes.koplugin)
- [Full English Guide](https://github.com/Mahmoudgomaa001/prayertimes.koplugin/blob/main/docs/README.en.md)
- [الدليل الكامل بالعربية](https://github.com/Mahmoudgomaa001/prayertimes.koplugin/blob/main/docs/README.ar.md)

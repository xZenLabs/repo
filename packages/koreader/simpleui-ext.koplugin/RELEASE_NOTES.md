# v1.17.0 · 2026-11-07

# SimpleUI Extra Modules v1.17.0

Requires SimpleUI 3.0 or newer for the new **Text** menus; everything else works on older SimpleUI builds as before.

## New

### Per-element fonts (SimpleUI 3.0+)
A new **Text** menu lets you pick font, style and size for each element of a module, using SimpleUI 3.0's text styles. Elements you don't touch keep their built-in face. On older SimpleUI builds the menu is hidden and the modules render as before.

- **Recent Book Stats** — headers, values and labels
- **Hero Currently Reading** — title, author, description, progress and statistics
- **Currently Reading (with Pace)** — title, author, percentage and statistics
- **Reading Streaks** — headers and values

### Recent Book Stats: Sections
A new **Sections** toggle lets you hide either the **This Book** or the **Pace** panel. The remaining panel takes the full width. One panel always stays visible.

### Stable page numbers
Books with KOReader's **"Use stable page numbers"** enabled now show the reader's page labels in **Recent Book Stats**, **Hero Currently Reading** and **Yanllsama**. Page counts derived from the Statistics database (pages read, pages/min, pages left, last session) are converted to stable pages. Time and day estimates stay in screen pages, matching the Statistics plugin. Books without the flag are unchanged.

## Fixes

- **Recent Book Stats:** unchecking one section no longer makes the other panel disappear. SimpleUI 3.0 hides rows whose enable condition is false, so the last remaining section now refuses to be unchecked instead.
- **Text styles:** fall back to the older `makeTextStyleMenu` / `makeTextStyleItem` and `getTextStyle` APIs on early 3.x builds, and log the reason when the Text menu is unavailable.

# v1.16.0 · 2026-10-24

- adapt to simpleui 3.0

# v1.15.0 · 2026-08-26

 - adapt to simpleui 2.6

# v1.14.0 · 2026-08-20

- Adapt to SimpleUI 2.5

# v1.13.4 · 2026-08-16

- fix: some display issues, pr  from @GOSENGWONG :

    The author line in module_hero_currently and the Cover Deck description
    strip both overflowed their box. Both now let TextBoxWidget do the clipping
    via height + height_overflow_show_ellipsis instead of hand-rolled measurement.

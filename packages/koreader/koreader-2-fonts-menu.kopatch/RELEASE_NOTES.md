# koreader-user-patch · 2026-09-24

LAST UPDATE: 2‑fonts‑menu‑profile  
Added quick profile selection.

A user pointed out that when changing fonts, you often need to adjust weight, spacing, or contrast, since each font has its own characteristics. For convenience, some users create profiles with different settings for each font.
Now you can switch profiles directly from the character‑settings screen — allowing you to change a single font or apply a full profile instantly for more refined setups.

Note: The profile tab shows existing profiles. If you create a new one, you’ll need to restart KOReader for it to appear in the quick‑selection list.

Patch for KOReader. “Fonts panel” in the bottom panel, under the font‑size section.
The patch adds a clickable text (a link) called “"FONT: font name”, which opens the menu for selecting the fonts installed in your KOReader.

Merged the previous patches with user‑selectable options.
To choose your preferred mode, simply long‑press on “FONT: font name”. A window will appear where you can set your preference, which will remain saved until you change it again.

By default, it starts with the fixed bottom panel mode.

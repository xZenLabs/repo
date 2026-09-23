# v1.3.2

**Added**
- New Margin settings under Advanced Settings.

# v1.3.1

**New**
- Spanish translation #3 (Thanks: @sergiomarquezdev )

**Fixed**
- Text positions when wallpaper has set and text background is not transparent

# v1.3.0

### Added
- **Image export for Android wallpaper**: since KOReader's built-in sleep
  screen never shows on Android (the OS lock screen takes over instead),
  Book Card can now export the card as a PNG on a timer and on suspend.
  New menu: *Advanced Settings → Image export (for Android wallpaper)*,
  with a refresh interval, an optional extra "copy to shared folder"
  destination (so a gallery/wallpaper app can pick it up), and a manual
  "Save image now" action. The image always lands at
  `koreader/screensaver/bookcard_png/bookcard_wallpaper.png`.
- **Grouped text background** option: when using a wallpaper background
  with text backdrop opacity, you can now choose "Grouped" instead of
  "Individually" so the stats column and the title/author/series block
  each get a single combined backdrop panel instead of one panel per line.

### Notes
- Image export is opt-in and off by default; when disabled it has no
  effect on existing behavior (sleep screen, rendering, etc.).

# v1.2.0

**New**
- Wallpaper backgrounds (based on Bookshelf's code) — pick a background picture for the card from settings/bookcard/wallpapers/ (Background > Wallpaper), with a translucent panel drawn behind each text element so it stays legible over the picture.
Text background opacity setting (Off / Low / Moderate / High / Solid) controlling the strength of that translucent panel (Background > Text background opacity).
- Daily Avg (pages) — optional second "Daily Avg" row showing pages/day instead of time (Card elements > Statistics), off by default.
- Advanced Settings menu (Tools > Book Card > Advanced Settings):
  - Orientation: Default / Force portrait / Force landscape. Forcing an orientation rotates the screen just before the sleep screen is drawn and restores it automatically on wake. The Preview popup is unaffected — it always renders at whatever orientation the screen is currently in.
  - Clear cached data (moved here, see below).

**Fixed**
- Night mode SVG icons (flame / moon / sun / sunrise / sunset) no longer show a black box behind them — they're now composited with a proper coverage mask so only the icon's own pixels get inverted.

# v1.1.1

## Fixed ##

When exiting from a book and the sleep, it now shows the up to date data.

# v1.4.0

**New**

- Statistics modules can be re-arranged now
- Random quote from the current book can be displayed under the author/series
- Ukraine translation added #4 (Thanks: @advokatb)

**Fixed**
- Grouped text boxes adjusted the cover + shadow (if it's enabled)

# v1.3.3

**Changed**

Changed Book Card to Book card to match the Koreader default plugin names.

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

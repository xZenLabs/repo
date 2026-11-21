# v1.0.2 · 2026-11-21

Marginalia v1.0.2 — Stability & Performance
This update focuses on smoother reading, more reliable margin handling, and easier access to Marginalia.
What's new
- Fixed repeated “Reloading”: resolved the loop that reopened books and reapplied margins over and over.
- Improved performance: faster drawing of prepared ornaments, fewer redundant screen updates, and less unnecessary work when opening the gallery.
- Better activation flow: when Marginalia is disabled, its shortcut now opens a Capitulares-style popup to enable it or close the popup.
- New menu symbol: added ❈ Marginalia to the KOReader menu.
- Preserved your setup: existing profiles, per-book compositions, and all 249 bundled ornaments remain unchanged.
Installation: Use the full ZIP for a new installation or No Images to update while keeping your ornament library.

Important: Disable Marginalia from the Tools menu before uninstalling it, so the original book margins are restored.

# V1.0.1 · 2026-11-20

Marginalia v1.0.1 — Performance Hotfix

Superseded — known repeated “Reloading” bug. Marginalia v1.0.1 can repeatedly reload books with decorative margins. Please update to v1.0.2 (see Releases), which fixes the issue and includes performance/UI improvements. Keep a backup of book .sdr settings and disable Marginalia via its Tools menu before manually uninstalling it, to restore original margins.

A maintenance release focused on improving reading performance, preventing unwanted margin persistence, and ensuring proper cleanup when disabling or uninstalling the plugin.

Fixed

- Page-turn performance: Removed automatic margin recovery during page changes to prevent unnecessary repagination.
- Margin persistence: Temporary ornament margins no longer overwrite the book's original margin preferences when settings are saved.
- Plugin cleanup: Improved removal of graphical overlays, cached image resources, and gesture handlers when disabling or uninstalling Marginalia.
- Margin restoration: Improved restoration of original margins, including recovery from previous v1.0 settings when the original values are available.
- Stability: Prevented pending redraw operations from restoring visual elements after the plugin has stopped.

Unchanged

- All 249 included ornaments are preserved.
- Existing profiles, compositions, and personal libraries remain compatible.
- No changes to the main interface or ornament positioning.
- Original ebook files remain untouched.

Installation

Close KOReader, replace the existing plugin files, and restart. Use the No Images package to preserve your existing collection.

# v1.0 · 2026-11-18

# Marginalia for KOReader

Add decorative borders, corners, dividers, strips, and figures to your reading pages. Marginalia works inside KOReader and does not change your ebook files.

## Screenshots

### Black & White

![Marginalia 1](https://raw.githubusercontent.com/rmmr111/Marginalia.Koplugin/main/Screenshots/Marginalia1.png)
## Features

- Choose ornaments from the Gallery and add them to a book.
- Change their size and position, or hide and remove them.
- Save your favorite combinations as profiles and use them in other books.
- Add your own SVG, PNG, and JPG images.
- Change SVG colors on supported color E Ink readers.
- Figures appear in front of borders when used together.
- English and Portuguese menus.

## Download

- **`Marginalia_v1.0.zip`** — complete plugin with **249 ornaments**.
- **`Marginalia_v1.0_No_Images.zip`** — complete plugin without images, for people who already have a collection.

## Installation

1. Close KOReader.
2. Extract the ZIP into your KOReader `plugins` folder. The result should be `plugins/marginalia.koplugin/`.
3. Restart KOReader and open **Marginalia** while reading a book.

On Kobo, the plugin folder is usually inside `.adds/koreader/plugins/`.



## Add your own images

Keep personal collections outside the plugin so they are not lost during updates. For example:

```text
koreader/marginalia/My Collection/Frames/my-border.svg
koreader/marginalia/My Collection/Figures/my-figure.png
```

Other supported folders include `Corners`, `Stripes`, and `Separators`. Reopen Marginalia after adding images to refresh the Gallery.

**When updating:** back up your files first. Keep your personal `koreader/marginalia/` folder.

## Image credits

The included artwork comes from [Rapier](https://rapier.website/gallery#borders), [Hellmouth](https://hell-mouth.neocities.org/marginalia), [Rawpixel](https://www.rawpixel.com/public-domain), and other public collections. **Not all images are public domain.** See [IMAGE_SOURCES.md](IMAGE_SOURCES.md) and [IMAGE_MANIFEST.csv](IMAGE_MANIFEST.csv) for source links and license details.

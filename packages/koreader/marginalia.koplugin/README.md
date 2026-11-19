# Marginalia for KOReader

**Decorative borders, corners, dividers, strips, and figures for your reading pages.**

Marginalia is a KOReader plugin for adding decorative artwork to ebooks without modifying the original book files. Combine ornaments, adjust their placement and size, and save the result as a reusable composition profile. It is designed for E Ink readers, including monochrome and color devices.

## Screenshots

### Black & White
![Marginalia 1](https://raw.githubusercontent.com/rmmr111/Marginalia.Koplugin/main/Screenshots/Marginalia1.png)


### Color E-Ink
![Marginalia Color - Gallery](https://raw.githubusercontent.com/rmmr111/Marginalia.Koplugin/main/Screenshots/marginalia%20color1.png)

## Features

- **Ornament gallery:** browse borders, half-page borders, corners, strips, dividers, and decorative figures.
- **Book-specific layouts:** add multiple elements to a book, show or hide them, and adjust their size and placement.
- **Composition profiles:** save, rename, update, delete, and reuse your preferred combinations of ornaments and margins.
- **Direct profile selection:** tapping a profile applies it to the current book and returns to the main panel, without an extra editor or confirmation step.
- **Figures in front:** figures are painted above frames and other structural ornaments, regardless of the order in which you added them.
- **Personal libraries:** browse ornament collections stored outside the plugin so they can survive reinstallations and upgrades.
- **SVG colors:** recolor supported SVG decorations on compatible color E Ink screens; PNG and JPG files are not recolored.
- **Language support:** English and European Portuguese.

## Downloads

Two versions of the **same complete plugin** are available in the GitHub release:

| File | Includes | Recommended for |
| --- | --- | --- |
| `Marginalia_v1.0.zip` | Full plugin and **249 bundled ornaments** | New installations |
| `Marginalia_v1.0_No_Images.zip` | Full plugin code, **no bundled ornaments** | Users with their own ornament libraries |

The *No Images* version is **not** a patch or a changes-only package. Both versions have the same code and features.

## Installation

1. Close KOReader.
2. Extract the chosen ZIP into your KOReader `plugins` directory.
3. Check that the resulting folder is `plugins/marginalia.koplugin/` (not a nested or renamed folder).
4. Restart KOReader and open **Marginalia** from the KOReader menus.

On Kobo, the usual location is `.adds/koreader/plugins/marginalia.koplugin/`. Other devices use their own KOReader installation directory.

**Updating an existing installation:** back up your files first. When replacing a bundled library, replace the plugin's `images/` directory rather than merging files, so older assets are not left behind.

Never delete your separate personal library under `koreader/marginalia/` when replacing the plugin. If using the *No Images* version, keep your existing personal ornament collections; the ZIP does not supply any new ornament image files.

## Getting started

1. Open a book and launch Marginalia.
2. Select **Gallery**, browse a collection and category, then add an ornament to the book.
3. Return to **This book** to resize, reposition, hide, remove, or save changes to individual elements.
4. Use **Advanced margins** if you need to adapt the page layout around your decorations.
5. Save the composition as a **profile** to reuse it with other books.
6. To use an existing composition, choose a profile. It is applied immediately to the current book.

When figures and frames overlap, figures always appear in the foreground. This changes only the visual drawing order; saved coordinates and other profile settings are preserved.

## Add your own ornament collections

The safest place for custom images is **outside** the installed plugin, under `koreader/marginalia/`. For example:

```text
koreader/
├── plugins/
│   └── marginalia.koplugin/
│       └── images/                # Bundled library (if installed)
└── marginalia/                    # Personal data and collections
    ├── custom/
    │   └── Figures/
    │       └── my-figure.svg
    └── My Collection/
        ├── Frames/
        │   └── my-border.svg
        ├── Corners/
        │   └── my-corner.png
        └── Separators/
            └── my-divider.svg
```

The gallery reads ornament images from the bundled `images/` folder, `koreader/marginalia/custom/`, and named collections directly beneath `koreader/marginalia/`.

- Use recognized category names such as **Frames**, **Half Frames**, **Corners**, **Stripes**, **Separators**, and **Figures**.
- Extra category folders, such as `Stripes/Horizontal/`, are supported.
- Supported ornament image formats are **SVG, PNG, and JPG**.
- Close and reopen the Marginalia panel after copying files to refresh the gallery.
- A collection without a recognized ornament category may not appear in the gallery.

Your personal collections and saved profiles are stored separately from the installed plugin. They should remain available after plugin updates, provided you do not delete `koreader/marginalia/` itself.

## Troubleshooting

**My custom collection does not appear.** Check its location, category folder name, and file extension, then close and reopen the Marginalia panel. Make sure you are running the current version of the plugin.

**I installed the No Images ZIP and the bundled gallery is empty.** This package does not include the 249-image library. Add your own collection or install the full package.

**A figure overlaps a border.** Figures are deliberately drawn in front of borders so that their artwork remains visible. Adjust the figure's position or size if you want less overlap.

## Image sources, licenses, and acknowledgements

The public image bundle contains **249 ornaments**. Not all images are dedicated to the public domain: some are shared with permission, and others carry attribution and share-alike requirements. The images and the plugin's code do **not** automatically have the same license.

The principal sources are [Rapier](https://rapier.website/gallery#borders), [Hellmouth](https://hell-mouth.neocities.org/marginalia), [Rawpixel's public-domain collection](https://www.rawpixel.com/public-domain), and individual works from Wikimedia Commons and Openclipart. Thanks to the creators and archivists who made these resources accessible.

- [`IMAGE_SOURCES.md`](IMAGE_SOURCES.md) — source summaries, licensing notes and required attribution.
- [`IMAGE_MANIFEST.csv`](IMAGE_MANIFEST.csv) — image-by-image source URLs, rights notes and SHA-256 values.

Credits and license details are provided to help users understand the terms of each artwork source. If you redistribute or modify an ornament, check its individual license and attribution requirements first.

## Project notes

- Marginalia runs inside KOReader; it does not alter the EPUB or other source ebook file.
- Rendering and visual behavior can vary by device, E Ink screen, and KOReader version.
- Please report issues with your reader model, KOReader version, steps to reproduce, and relevant logs or screenshots.

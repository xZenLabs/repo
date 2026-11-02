# v1.7.3 · 2026-11-02

## New features

- **ZenPM support**: Meguru can now be installed and updated from [ZenPM](https://github.com/xZenLabs/zen-pm). Search for `meguru`. (#10)

## Bug fixes

- **Derainbow works on Android again**: the native libraries are now copied into the app's private files directory, since shared storage is mounted `noexec`. Refs #9.
- **Compatible with KOReader's new OPDS dialog**: the *Meguru this series* row now appears in both the old `showDownloads` and the new `getDownloadButtons` dialog. Refs koreader/koreader#16311.


## New Contributors
* @KristanLaimon made their first contribution in https://github.com/Craftwork2720/meguru/pull/10

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.7.1...v1.7.3

# v1.7.1 · 2026-10-30

## Bug fixes

- Fixed turned panels appearing upside down on a landscape screen.
- Fixed **Meguru this series** missing on KOReader nightly builds ([koreader/koreader@dad1ad4](https://github.com/koreader/koreader/commit/dad1ad44335fafb1070d524c9ffd2fa2ce2da81d)).
- Fixed books opened from a just-added OPDS catalog not creating their series folder.

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.7.0...v1.7.1

# v1.7.0 · 2026-10-25

## Meguru v1.7.0

Two new optional integrations.

### [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) (OPDS catalog browser)

- **▶ Meguru this series** row in Bookshelf's OPDS catalog window opens a series directly in Meguru.
- **`.meguru` files also open from folder shelves** with bookshelf.koplugin 5.5.0+.

### [Panels+](https://github.com/KristanLaimon/PanelsPlus)

- **Panels+ added as an option for the long-press.** *Panel view* puts `panels+` first, followed by `off` and all three Meguru views: `panel cut`, `pan & zoom`, and `free view`.
- **Panels+ OCR text selection now works in Meguru**, in the Panels+ view only.

### Thanks

- [AcidWeb](https://github.com/AcidWeb) for [bookshelf.koplugin PR #496](https://github.com/AndyHazz/bookshelf.koplugin/pull/496), which made the Bookshelf integration possible

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.6.0...v1.7.0

# v1.6.0 · 2026-10-16

## New features

- **Settings are shared across a series** — a menu row you change applies to every book in it. Turn off *Remember settings for this series* to stop the sharing.
- **Panel rotation has three states**: No rotate / Rotate / Autorotate, remembered across books.
- **Hardware Dithering row** on devices whose screen controller can dither. It replaces the software row there, and starts from the device's own setting.
- **Full refresh on every page turn**, for Meguru only.
- **Crop recognises more margins**: paper, drawn frames, and bars down a side.
- **The letterbox is painted in the margin that was trimmed**.
- **Book info names the OPDS catalog** when it differs from the server.

## Improvements

- **Decode budget raised to 10 Mpx.**
- **Resuming a book no longer decodes page 1.**
- **The panel view warms the next page's crop, panels and first tile.**
- **Panel detection no longer copies the page.**
- **The pair offset gesture action is named *Meguru: …* and is offered only while a Meguru book is open.**
- **Menu regrouped**: server rows are now under **OPDS**.

## Bug fixes

- Fixed the margin colour around the first page of a book.
- Fixed a catalog that changed server being remembered as the old one.
- Fixed an error when a local `.cbz` is opened for the first time.

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.5.4...v1.6.0

# v1.5.4 · 2026-10-11

## Bug fixes

- **Kavita: chapters are no longer skipped.** ([#5](https://github.com/Craftwork2720/meguru/issues/5)).
- **Komga: series covers now use the full-size image**.

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.5.3...v1.5.4

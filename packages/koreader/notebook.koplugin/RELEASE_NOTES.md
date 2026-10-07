# v1.7.2 · 2026-10-07

## [1.7.2](https://github.com/pierspad/notebook.koplugin/compare/v1.7.1...v1.7.2) (2026-10-07)

### Bug Fixes

* reject persistent palm contacts and erase arrows without object menus ([43b58e7](https://github.com/pierspad/notebook.koplugin/commit/43b58e70ed6fa887aecbe071417977eebbff99f0))

- Palm contacts remain blocked during pen proximity and until finger release; pen takeover clears stale zoom-pan origins.
- Lines and arrows now erase in whole-stroke or area mode without opening object menus. Undo restores the original shape.
- Text stacking controls are omitted for selected lines and arrows.

Validated with the full test bench, package checks and native rendering checks in all shipped languages.

The intermittent Scribe issue where library titles reappear around handwriting has not been reproduced and is not claimed as fixed in this release.

# v1.7.1 · 2026-10-05

## [1.7.1](https://github.com/pierspad/notebook.koplugin/compare/v1.7.0...v1.7.1) (2026-10-05)

### Bug Fixes

* preserve marker opacity and finish mouse drawing gestures ([5b05e67](https://github.com/pierspad/notebook.koplugin/commit/5b05e67c71eec636afa45eead2483a5797c9e57e))

# v1.7.0 · 2026-10-05

## [1.7.0](https://github.com/pierspad/notebook.koplugin/compare/v1.6.3...v1.7.0) (2026-10-05)

### Features

* add autosaved notebook workflows, embedded images and paper controls ([8e3a274](https://github.com/pierspad/notebook.koplugin/commit/8e3a2742384d1881f55fee8ab3fdf8d07cc0b16e))

### Bug Fixes

* polish notebook menus, previews and translations ([3258b82](https://github.com/pierspad/notebook.koplugin/commit/3258b828322da01cc85818898934c55d2da16e79))

# v1.6.3 · 2026-10-01

## [1.6.3](https://github.com/pierspad/notebook.koplugin/compare/v1.6.2...v1.6.3) (2026-10-01)

### Bug Fixes

* prevent eraser bridges and overlapping marker geometry growth ([d48e26e](https://github.com/pierspad/notebook.koplugin/commit/d48e26e3d09574939905a959cd974732e91c5746))

# v1.6.2 · 2026-10-01

## [1.6.2](https://github.com/pierspad/notebook.koplugin/compare/v1.6.1...v1.6.2) (2026-10-01)

### Bug Fixes

* render update notes with native Markdown and document source installation ([d097c4e](https://github.com/pierspad/notebook.koplugin/commit/d097c4e3a3144fe503a3f7515e7e08a3fb6d7256))

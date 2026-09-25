# v1.2.0

## [1.2.0](https://github.com/pierspad/notebook.koplugin/compare/v1.1.0...v1.2.0) (2026-09-24)

### Features

* add cancellable PDF export progress ([bf1b4c0](https://github.com/pierspad/notebook.koplugin/commit/bf1b4c05d384af4f4c26fead10976a417a48f057))
* add editable text, PDF backgrounds and XOPP export ([bd10ca0](https://github.com/pierspad/notebook.koplugin/commit/bd10ca06ab1b526149e7570601fc0efac29a0285))
* add live styled text editing ([9e311a9](https://github.com/pierspad/notebook.koplugin/commit/9e311a9529f47e679f07df8e6a8a44b284ed641b))
* improve stylus tools, editable shapes and drawing responsiveness ([002ae5b](https://github.com/pierspad/notebook.koplugin/commit/002ae5b45f6297f57937513b3bfed48254653f19))
* smooth low-latency highlighter ink ([389dd9f](https://github.com/pierspad/notebook.koplugin/commit/389dd9fed61530438a005cca35d5b0919b3c7b49))

### Bug Fixes

* keep live ink and text state visible ([89d2335](https://github.com/pierspad/notebook.koplugin/commit/89d233532f704572e2fd51bf3e2095c0016f83d6))
* pre-release ([2709775](https://github.com/pierspad/notebook.koplugin/commit/27097753faea6a8b4fd489eedadcc2241987faa8))
* preserve PDF geometry in XOPP sharing ([f129d36](https://github.com/pierspad/notebook.koplugin/commit/f129d36885ec77b57a9df9e859586ef97e89afed))
* remove pen-up stalls and surface XOPP exports ([0296b52](https://github.com/pierspad/notebook.koplugin/commit/0296b52ef725c6e1c0ae20067f08d4aa8ded90fb))
* restore fast highlighting and compact text input ([16bb062](https://github.com/pierspad/notebook.koplugin/commit/16bb0627407f8682470a47e72e5b95aa74f80308))

# v1.1.0

## [1.1.0](https://github.com/pierspad/notebook.koplugin/compare/v1.0.0...v1.1.0) (2026-09-14)

### Features

* distinguish pen options and place clock beside settings ([97624ca](https://github.com/pierspad/notebook.koplugin/commit/97624ca95feb37443707c3c92285654db624f744))
* every lasso edit is one entry in the history ([44711f0](https://github.com/pierspad/notebook.koplugin/commit/44711f0a0985c99b90e6cb8191c6182cfd462e18))
* streamline PDF export and drag selection in gallery ([a83a9b8](https://github.com/pierspad/notebook.koplugin/commit/a83a9b8c56552376747c262db6b8b7217b288c43))
* the numbers that decide how the pen feels, as values ([42bdd7a](https://github.com/pierspad/notebook.koplugin/commit/42bdd7a9ef3dec1490747af081c8fa19ccc3e496))
* the tuning panel, built from the tab declaration ([9bc84c2](https://github.com/pierspad/notebook.koplugin/commit/9bc84c216a77ba616f47e4128ac87c539fff5d5a))

### Bug Fixes

* isolate plugin modules and protect pen selections from palm touches ([1eefbfb](https://github.com/pierspad/notebook.koplugin/commit/1eefbfbdd781fa967118a1e36b0516d285592afa))
* keep a selection's repaints, and its clipboard, to itself ([0ba1187](https://github.com/pierspad/notebook.koplugin/commit/0ba11875a4bd677dd4db6ae8c819f8a963c16f98))
* use compatible conventional changelog preset ([af75d82](https://github.com/pierspad/notebook.koplugin/commit/af75d82f22ba88a95e30e2aa1b6bfc9933738664))
* what v1.0.0 got wrong about the device it runs on ([ed4ee13](https://github.com/pierspad/notebook.koplugin/commit/ed4ee13491b5e3b50c1b83ee72d9665906fad654))

### Performance Improvements

* fix notebook input backlog and clipped rendering ([4f2484f](https://github.com/pierspad/notebook.koplugin/commit/4f2484f4ff88cec9bae55b678c325070af1c2db0))

# v1.0.0

# Changelog

## v1.0.0

First release.

### Writing

- Pen, highlighter and eraser, with the eraser working either by area or by
  whole strokes.
- Hold still at the end of a stroke to snap it to a line, rectangle, circle or
  triangle.
- Lasso a part of the page to move, cut, copy, paste or delete it.
- Undo and redo, and as many pages as you like, each able to take its own
  background: blank, lined, narrow lined, grid, dot grid or checklist.
- A hand resting on the glass does not draw. The pen is tracked in its own input
  slot and touches are ignored while it is down, for a moment longer than the
  stroke itself, because a hand usually leaves the glass after the nib does.

### The gallery

- Notebooks as thumbnails rather than file names, in folders.
- Rename, duplicate, move, delete and export, on one notebook or on a selection.
- Sorting by last edited, least recently edited, or name in either direction,
  remembered between sessions.
- Export to PDF, one or many, rendered a notebook per tick so the screen keeps
  answering.
- Sidecar directories KOReader writes beside an opened PDF are hidden, and the
  one belonging to a PDF you delete goes with it.

### Sending

- With [localsend.koplugin](https://github.com/kaikozlov/localsend.koplugin)
  installed, a Send action appears and hands a notebook — or a whole selection,
  rendered to PDF on the way out — to a phone over Wi-Fi.
- Entirely optional and not a dependency: nothing is required, the running
  plugin is looked up on the UI, and if it is not there the button is never
  built.

### Not falling over

- Every way the event loop can enter this plugin is behind a pcall and a
  watchdog. A fault closes the notebook, writes `notebook-error.log` and leaves
  KOReader running.
- The watchdog turns the JIT off for the duration of a protected call, because a
  count hook is not checked inside a compiled trace — which is to say that
  without it an infinite loop in a handler is a dead device, silently.
- 203 tests across ten suites, run before every push and before every deploy.

### Installing

Extract `notebook.koplugin-v1.0.0.zip` into your KOReader plugins directory and
restart. On a Kindle that is `/mnt/us/koreader/plugins/`.

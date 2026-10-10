# v1.2.0 · 2026-02-24

### What's New
- **Scanned PDF freeze fix** — Long-pressing on scanned PDF pages no longer freezes the device. Cozy Home intercepts the gesture before KOReader's Leptonica OCR engine fires, and shows a helpful message instead.
- **[PDF] tags** — PDF books now show a [PDF] tag in Learning Space book lists and the book picker.
- **One-time PDF tip** — First time opening a PDF from a Learning Space, a brief note explains highlight limitations on scanned documents.

### Install
Extract `cozyhome.koplugin` to `koreader/plugins/` on your device.

# v1.1.1 · 2026-02-23

### What's New

**Standalone scheduling preset picker** — Cozyhome's flashcard hub now
has a ⚙ Scheduling button on the Stacks tab, so you can switch between
Relaxed, Standard, Intensive, and Daily presets without needing the
Cozy Flashcards plugin installed.

### Details

- Added "Scheduling" button next to "+ New Deck" on the Stacks tab
- Shows all 4 presets with learning step details (e.g. 10m → 1d → 3d → 4d)
- Current selection marked with ● indicator
- Setting stays in sync if you also have Cozy Flashcards installed

### Install

Extract the zip into your KOReader `plugins/` folder so you have:
`koreader/plugins/cozyhome.koplugin/`

# v1.1.0 · 2026-02-23

Updates made to change "notecard" to "flashcards".
Fixed import and export functionality on flashcards.
**Full Changelog**: https://github.com/thekimberleyann/cozyhome.koplugin/compare/v1.0.0...v1.1.0

# v1.0.0 · 2026-02-19

## Cozy Home v1.0.0

A clean, customizable welcome screen that replaces KOReader's default file browser. Big tappable tiles, minimal clutter, and quick access to your books, highlights, flashcards, and study tools.

## Features

- **Welcome Dashboard** — Continue Reading card, 3×2 nav grid, reading stats
- **Highlights Browser** — Browse, search, and filter highlights across all books; create flashcards from highlights
- **Learning Spaces** — Organize books into classes/topics with linked notecards and highlights
- **Notecards Hub** — Built-in spaced repetition review engine (SM-2 algorithm), deck management, Anki import/export
- **Focus Mode** — Pomodoro timer with XP and streak tracking
- **Settings Hub** — Customize tile layout, behavior, and spaced repetition tuning

## Installation

1. Download **`cozyhome.koplugin-v1.0.0.zip`** below
2. Extract and copy the `cozyhome.koplugin` folder to:
   ```
   [Kobo drive]:\.adds\koreader\plugins\cozyhome.koplugin\
   ```
3. Restart KOReader
4. Open from **Tools → Cozy Home**

## Requirements

- KOReader (recent version with LuaJIT / Lua 5.1)
- Tested on: Kobo Clara 2E, Kobo Libra Colour

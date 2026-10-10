# v1.0.2 · 2026-10-10

### Fixed
- **Broken board when other chess plugins are installed.** Kochess used to copy its piece icons into the shared `icons/chess` folder, and skipped the copy if that folder already existed. Other plugins, such as [Board Games](https://github.com/KitanaCode/boardgames.koplugin), write their own pieces to that folder. If one of them was started first, Kochess showed that plugin's pieces, and empty squares showed KOReader's "icon not found" placeholder.

### Changed
- Piece icons now go into a folder that only Kochess uses: `koreader/icons/kochess`.
- Icons are checked on every start. A missing or changed file is copied again, so icon changes in future versions reach your device.
- Kochess no longer touches the old `icons/chess` folder, so plugins that rely on it keep working.

### Upgrading
Replace the `chess.koplugin` folder and restart KOReader. You don't need to copy icons by hand. You can delete the old `icons/chess` folder if no other plugin uses it.

Thanks to @dmaglio for the fix (#4).

# v1.0.1 · 2025-11-30

- stockfish binary is included in the repo ( tested on Kobo Forma and Kindle Touch only)
- submodule files are now part of the repo

# v0.17.1 · 2026-11-22

- Fixed: with the split screen, a PDF or DjVu in KOReader's reflow mode is now reflowed for the book's half, with the text as big as on the whole screen. Before, it was reflowed for the whole screen, so dragging the divider changed nothing and, with the book on the left or right, the page was cut.
- Fixed: with the split screen, dragging the divider keeps the place down a long page (a reflowed one) instead of going back to its top.

Install: copy the `chessboard.koplugin` folder to `koreader/plugins/` and restart KOReader, or update it from Storefront or AppStore.

If you enjoy the project, a star on GitHub is much appreciated. Please report bugs at https://github.com/FelipeMarelli/chessboard.koplugin/issues

# v0.17.0 · 2026-11-22

- **Split screen**: the book on one half of the screen and the board on the other (above or on the left, swappable). Drag the line between them to give either more room. Beside the board, every button at once and several lines of moves. A PDF or DjVu page is shown whole in its half.
- **Dark mode**: the moon button draws the window in dark grays; the sun brings it back light.
- **Analyze on lichess**: the QR code button shows the game full screen as a QR code; scan it to open the whole line on the lichess analysis board.
- **Remembered across books**: split or floating, the divider, the size of the window, and dark or light are kept, also after KOReader restarts.
- **Three dots**: the buttons used less often (size, start over, split, QR code, dark mode) are under a "more" button, so the floating window stays narrow.
- **Move button feedback**: while the finger is on the move button the window frame thickens; a short hint explains how to drag it.
- New look: buttons as cards on a light gray ground, a white frame around the board, rounded held buttons.
- Fixed: with the split screen, KOReader no longer reopens the book by itself after a few idle seconds.

Install: copy the `chessboard.koplugin` folder to `koreader/plugins/` and restart KOReader, or update it from Storefront or AppStore.

If you enjoy the project, a star on GitHub is much appreciated. Please report bugs at https://github.com/FelipeMarelli/chessboard.koplugin/issues

# v0.10.1 · 2026-11-18

- The board now opens from Tools › "Chess board" in the reader menu, instead of Tools › More tools.

Install: copy the `chessboard.koplugin` folder to `koreader/plugins/` and restart KOReader, or update it from Storefront or AppStore.

# v0.10.0 · 2026-11-18

First release of Chess Board, a KOReader plugin for reading chess books: an interactive board that floats over the page of the book.

- Floating board over the book; taps outside it still turn pages and follow links.
- Legal moves only, with castling, en passant, promotion, check, mate and stalemate.
- A strip with the line of moves in book notation; step back and forward, or jump to the start and end.
- Try variations: go back and play another move.
- Position editor, with the side to move and castling deduced from the pieces.
- Move and resize the window; hold the eye to peek at the text under it.
- Made for e-ink; portrait and landscape; English and Spanish.

Install: copy the `chessboard.koplugin` folder to `koreader/plugins/` and restart KOReader, or install it from Storefront or AppStore. Developed and tested on KOReader v2026.07.1 on a Kindle Paperwhite.

Still in development: please report bugs at https://github.com/FelipeMarelli/chessboard.koplugin/issues

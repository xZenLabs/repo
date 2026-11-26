# Chess Board (`chessboard.koplugin`)

A KOReader plugin for reading chess books: an interactive board that floats **over the page of the book**, so you can follow the games and try variations without leaving the reading.

> **Early version.** It is ready for reading chess books, and more features are on the way. Found a bug or want a feature? Open an issue at https://github.com/FelipeMarelli/chessboard.koplugin/issues — every report helps.

<img src="screenshots/game.png" width="300" alt="A big board over the page, with the moves played below it"/> <img src="screenshots/reading.png" width="300" alt="A small board in a corner, beside the text being read"/>

## Features

- **Floating board over the book**: it does not cover the reader; taps outside the window turn pages and follow links as always.
- **Legal moves only**: tap a piece and its targets are marked; castling, en passant, promotion, check, mate and stalemate.
- **The line of moves**: a strip under the board shows the moves played in book notation, with figurines and the current move in bold. Step back and forward, or jump to the start and the end.
- **Try variations**: go back and play another move; the rest of the line is replaced.
- **Position editor**: set up any position from the book, with the side to move; castling rights are deduced from the pieces.
- **Move and resize**: drag the window anywhere and make it as small or big as you like.
- **Peek behind the board**: hold the eye to read the text under the window; lift the finger and the board is back.
- **Analyze on lichess**: a QR code opens the game on the lichess analysis board, on your phone, at the position on the board.
- **Split screen**: the book on one half of the screen and a big board on the other, with big buttons beside it. The text reflows into its half, in EPUB, PDF and every format KOReader reads; drag the line between them to give the text more or less room.
- **Dark mode**: the window drawn in dark grays, for a book read in night mode or just for taste; one tap brings it back light.
- **Made for e-ink**: plain gray squares, sharp Merida pieces at any size, marks that differ by shape and not only by tone, and minimal screen refreshes.
- **Portrait and landscape.**
- **English and Spanish.**

<img src="screenshots/play.png" width="300" alt="A selected pawn and its targets"/> <img src="screenshots/editor.png" width="300" alt="The position editor"/>

<img src="screenshots/split.png" width="300" alt="The screen split: the book above, the board and its moves below"/> <img src="screenshots/dark.png" width="300" alt="The split screen drawn dark"/>

## Install

From Storefront or AppStore, searching for "Chess Board". Or by hand: copy the `chessboard.koplugin` folder to `koreader/plugins/` on the reader and restart KOReader.

Developed and tested on KOReader v2026.07.1, on a Kindle Paperwhite.

## Use

With a book open, the board opens and closes from the reader menu, under Tools › "Chess board".

- **Play**: tap a piece, then the target square.
- **Walk the line**: the arrows go back and forward one move; held down, they go to the start and the end.
- **More buttons**: the three dots show the buttons used less often: size, start over, split screen, QR code and dark mode. Back shows the main row again.
- **Move and resize**: drag the move button, the cross of arrows, to take the window somewhere else; while the finger is on it, the window frame thickens. The size button, under the three dots, makes it smaller or bigger.
- **Flip**: the arrows button turns the board around.
- **Peek**: hold the eye, first in the row, to hide the window and read what is under it; it comes back when you lift the finger.
- **Analyze on lichess**: the QR code button, under the three dots, shows the game full screen as a QR code; scan it with your phone to open the whole line on the lichess analysis board, at the position on the board. Tap to close it. Very long games do not fit in a QR code.
- **Set up a position**: the pencil opens the editor, with the pieces, the side to move, an eraser and a trash can that puts the start position or empties the board. Back starts the game from the new position.
- **Start over**: the trash can, under the three dots, goes back to the start position.
- **Dark mode**: the moon, under the three dots, draws the window in dark grays; the sun draws it light again.
- **Split the screen**: the split button, under the three dots, puts the book on one half of the screen and the board on the other: the book above in portrait, on the left in landscape. Drag the line between them to move it. In the split screen every button shows at once; the swap button puts the book and the board the other way round, and the window button takes the board back over the page. Beside the board, the moves of the line take every row that fits above the buttons: at least three in portrait and two in landscape, the buttons getting smaller for them, never the board. A PDF or DjVu page is shown whole in its half, and with its own zoom again when the board floats.
- **Remembered**: split or floating, where the line between book and board is, the size of the window, and dark or light are kept for every book, also after KOReader restarts. Each book still opens with the board closed.

## Like it?

If you enjoy the project, leave it a star on [GitHub](https://github.com/FelipeMarelli/chessboard.koplugin): it is much appreciated.

## License

Copyright (C) 2026 Felipe Marelli.

This program is free software: you can redistribute it and/or modify it under the terms of the GNU Affero General Public License, version 3, the same as KOReader. It comes with no warranty. See `LICENSE`, also included in the plugin folder.

The files listed below keep the license of their origin.

### Third-party code and graphics

| What | Origin | License |
|---|---|---|
| `chessboard.koplugin/chess/rules.lua` | `ink_knight/chess.lua` from [Ink Knight](https://github.com/beater-studios/ink_knight.koplugin), commit `601acd2`, © 2026 Beater Studios. Modified: names, strict FEN reading, move number, notation with the piece letter apart, position validation; what was specific to Ink Knight games was removed. | GPL-3.0, version 3 only (`chess/LICENSE-GPL-3.0`). Combinable with AGPL-3.0 under section 13 of both. The names "Ink Knight" and "Beater Studios" are not licensed (section 7(e)). |
| `spec/inkknight_rules_spec.lua`, `spec/perft_spec.lua` | `tests/chess_spec.lua` and `tests/perft_spec.lua` from Ink Knight, same commit, adapted. Not in the package. | GPL-3.0, version 3 only. |
| `chessboard.koplugin/assets/pieces/merida/*.svg` | Merida pieces by Armando Hernandez Marroquin, taken unchanged from [lichess](https://github.com/lichess-org/lila), commit `8f16c30`, folder `public/piece/merida`. | GPL-2.0 or later according to lichess's `COPYING.md`; used under GPL-3.0, combinable with AGPL-3.0. |
| `chessboard.koplugin/assets/icons/*.svg` | [Lucide](https://lucide.dev), package `lucide-static` v0.460.0: `arrow-down-up`, `minimize-2`, `move`, `x`, `trash-2`, `arrow-left`, `chevron-left`, `chevron-right`, `minus`, `plus`, `eraser`, `eye`, `square-split-vertical`, `flip-vertical-2`, `flip-horizontal-2`, `picture-in-picture-2`, `qr-code`, `ellipsis`, `moon` and `sun`. Modified: `stroke="currentColor"` becomes black. | ISC (`assets/icons/LICENSE-lucide`); parts from Feather, MIT. Compatible with AGPL-3.0. |
| `screenshots/*.png` | Taken in the KOReader emulator over *Chess Fundamentals* by José Raúl Capablanca (1921), from [Project Gutenberg](https://www.gutenberg.org/ebooks/33870). | The book is in the public domain. |
| `spec/perft/*.perft` | [scalachess](https://github.com/lichess-org/scalachess), commit `fbb8f2c`, via Ink Knight. Collected from chessprogramming.org and the Ethereal engine. | MIT (`spec/perft/LICENSE-scalachess`). |

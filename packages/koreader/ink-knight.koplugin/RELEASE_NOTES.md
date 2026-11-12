# v0.4.0 · 2026-11-12


- The list of moves starts with the name of the opening, from the list Lichess publishes, kept in the plugin so it works without internet: in the game against the engine, between two people and in the review. In a Lichess game it shows once the game is over, since Lichess does not show it to the players while they play.
- Correspondence games without internet: the games you have on Lichess stay on the device each time the list of games comes, and the offline menu shows them, your turn first. On your turn you can make a move with the Wi-Fi off, and take it back until it is sent. It goes to Lichess the next time you play online, or at once if the online part is open, only if the game is still in the position where you made it; if not, you are told it was not sent.
- 5000 puzzles come with the plugin, from the open Lichess puzzle database, for playing with no account and no internet: in the offline menu, at five levels of difficulty and with the color to play, going on from where you stopped. Their results do not go to Lichess. The release also has packages with 20000 and 50000 puzzles.
- A position editor, in the offline menu: put and take away pieces from a palette, choose the side to move and the castling, start from the usual position or an empty board, or paste a FEN. Done checks that the position can be played, says why when it cannot, and offers to play from it against the engine or between two people, with or without a clock, or to ask Lichess about it when the online part is open. The position is kept for the next time, and a game from it is continued later like any other.
- Learn chess, in the offline menu: the 18 stages of the official Lichess app for beginners, from how each piece moves to castling, en passant, stalemate and piece value, 110 levels with stars to collect, the opponent's moves and the same scores and stars as the site, with the texts of the app in the three languages and the progress kept.
- An optional clock in the game between two people, from 3+2 to 30+20: it starts with black's time after white's first move, adds the increment after each move, can be paused, keeps its time when the game is continued later and ends the game on time, a draw if the other side cannot give mate.
- A chess clock for a game on a real board, in the offline menu: the screen in two halves, the top one turned round for the player across, the side to move shown inverted, with the moves counted, pause and restart. It keeps the device awake while it runs and pauses when the device sleeps.
- Coordinate training, in the offline menu: tap the square named, or name the square marked, in 30 seconds or with no limit, from either side, with your best score kept. The board has no coordinates while training, and the clock waits while the device sleeps.
- Puzzles have a difficulty, from easiest to hardest compared with your puzzle rating, and a color to play, both in the puzzles menu. The puzzles kept for offline stay until a new batch chosen that way arrives, so a change made without internet still leaves puzzles to solve.

# v0.3.0 · 2026-11-10


- In a game without internet: choose your color, undo your last move and ask for a hint, which marks the best move found and plays it with a tap.
- A list of the moves of the game, two to a row, in the offline game, in the online game and in the review, where a tap on a move goes to it.
- The challenges you sent and nobody answered yet, rematches included, beside the ones you received, and each one can be canceled.
- A player who is not signed in on Lichess is called anonymous instead of a question mark.
- A game between two people on the same device, taking turns, with undo, the list of moves and a button to turn the board.
- Review mistakes: the puzzles you missed in the last 30 days, on the plugin or on the site, kept to solve without internet too.
- Challenges answered while the device slept no longer stay in the list after it wakes up.
- On the bar of a game, a white player without a name no longer shows the name of black.
- The Ink Knight cover on the sleep screen while the plugin is open.
- The token page in Portuguese no longer names the Kindle, like the other languages, since the plugin runs on other e-readers too.
- The screen with the QR code for the token says the address can also be typed in any browser, and the buttons no longer assume a phone: **Paste from another device** and **Done: paste the token**.
- During a game with a clock, the power button puts the device to sleep again. Before, it did nothing until the game screen closed, and a crash in the middle of a game could leave the device unable to sleep.
- Nothing is drawn over the sleep screen: the clocks, notices, the network and the engine wait until the device wakes up.
- Every screen opens in portrait and ignores rotation, including the online part, the rating chart and the token screens, and the previous rotation comes back on closing, also when a screen fails to open.
- After a few changes without one, the pages flash once to clear what e-ink leaves behind, and the board and the plugin itself open with a flash.
- The Back key, on devices with keys, goes back one step, and in a game with a clock it asks first, as the back button does.
- The token page opens its port only for private networks, and a crash with the page open no longer leaves the port open. If the device sleeps, the page stops and says so.
- Requests to Lichess use TLS 1.2 or newer.
- An option, a game or a puzzle saved by an earlier version that no longer makes sense is left out instead of stopping the plugin from opening.
- A page or the board that cannot be drawn shows a short message, and the way back still works.
- Following a player whose profile came incomplete no longer closes KOReader.
- In Spanish, the rating range option fits on larger screens.

# v0.2.0 · 2026-11-07


- Board styles: plain, newspaper (hatched dark squares like printed diagrams), crosshatch, dotted and contrast.
- Piece sets: classic, Cburnett and Merida.
- Optional coordinates on the edges of the board.
- These are in the settings and in the offline menu, and each choice shows a sample before its name.

# v0.1.1 · 2026-11-07


- When Lichess refuses the token, the online part is blocked except for one row that goes to connecting an account, and tapping it removes the token.

# v0.1.0 · 2026-11-07


First version.

- A first page where you choose to play online, play offline or exit. Lichess is only contacted after you choose to play online.
- The time and the battery at the bottom of every screen.
- Play on Lichess: find an opponent in rapid and classical, by correspondence, challenge friends and play the Lichess computer, with or without a time limit, picking your color in a challenge, and with an optional rating range when searching.
- A list of your games, with the ones waiting for you on top, refreshed at the interval you choose.
- Draw offers and draws by repetition, takebacks, giving time, resigning, canceling, claiming when the opponent leaves and playing again, with the game resuming by itself after a dropped connection.
- Puzzles, saved to solve without internet, with results sent when the Wi-Fi comes back, plus puzzles by theme, your results and the daily puzzle.
- Your past games and favorites move by move, with what Lichess knows about each position.
- Players: search, who is online, profiles, a rating chart with statistics, and your record against someone.
- Chess against a small engine with no internet, saved after each move.
- Connect your account by pasting the token from your phone, in English, Portuguese or Spanish.

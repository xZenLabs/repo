# v0.6.0 · 2026-11-14


- The plugin checks once, the first time it needs Stockfish, that it runs on the device (about half a second on a Kindle), and keeps the small engine where it does not, as on e-readers where the binary cannot run. An engine that stops in the middle of an analysis is noticed at once.
- Review at the end of a Lichess game: a game that ends with its board open shows a card with the result and Review the game first, and the bar of a finished game has Review. A game the site analyzed opens on its summary; one it did not offers the plugin's engine, with how long it takes, and an option to always analyze at the end of the game, which goes off again from More of the review. The analysis shows its progress as a bar, and every move it judged carries the tag "plugin's engine".
- The review tells about each move in a panel under the board: the move with the sign of Lichess (??, ?, ?!) and its judgment, the better move with an arrow on the board, and the evaluation in words ("white mates in 2", "black +1.5"). Games analyzed by Lichess get the arrow too.
- Moves are written with the pieces as symbols, the same in every language: in the review, the list of moves, the most played moves and under every board.
- The board of a review always shows the coordinates, since its moves and the better ones name squares.
- After the analysis of an offline game by Stockfish, its summary opens first, as at the end of a Lichess game, with your side marked.
- A change of the whole board (a game arriving right after its board opened, the card at the end, the board turned) now refreshes with a flash. Without it, on the Kindle the bar of buttons could stay blank until the next flash.
- The summary of an analysis has a chart of the evaluation, a tap away from each move, says whose analysis it is, marks your side, and has My first mistake, which goes to your first mistake or blunder. The accuracy of each phase moved to the rows of the phases.
- Stockfish on the device: the plugin carries Stockfish 11 built for the Kindle, at the lowest priority so the screen keeps answering. The analysis of a game played without internet uses it, judging every move as Lichess does (inaccuracies, mistakes and blunders, average loss and accuracy, in a summary under More); and a Lichess game the site did not analyze can be analyzed by it from More, the review saying it is the plugin's analysis, not Lichess's.
- The summary of an offline game analyzed by the small engine no longer offers a summary page it did not have, which closed the review with an error.
- Studies, in the online part: your studies (private ones too with the optional permission `study:read`, which the link for creating a token now marks, since it only reads), another player's, also from their profile, or one by its address or code. A study is kept on the device, downloaded in the background, to read without internet: a chapter as a commented game, with its comments and arrows, and an interactive chapter as a guided one, with the author's comments on wrong moves. Navigating the variations comes later.

# v0.5.0 · 2026-11-13


- Broadcasts, in the online part: the over-the-board tournaments Lichess relays, live, coming and finished, with search; each tournament with its rounds and standings; a round with its games, kept up to date; and a game with the clocks of both players that follows the moves while it is played. A tournament can be kept on the device, downloaded in the background, to see with no network; a download cut short resumes with what is missing.
- Every request to Lichess names the plugin and the address of its repository in its User-Agent.
- The plugin presents itself as chess on e-ink, offline and on Lichess, instead of a Lichess client: in its description, the line under its name on the first screen, the About page, the README, the banner, the social preview and the sleep screen cover, which now show the first screen beside a game.
- Analysis of a game played without internet, against the engine or between two people: once it is over, Analyze goes through the moves with the engine of the plugin, showing its progress and with a way to cancel, and opens the review with the clear mistakes and blunders marked, the better move named and the evaluation of each move, as in the review of a Lichess game. Against the engine only your moves are looked at. The engine is small, so only clear mistakes are marked.
- Puzzles by opening, in the puzzles menu: the openings Lichess has puzzles of, most puzzles first, each family with its variations, and the last ones you opened on top. Like a theme, each keeps its puzzles on the device to solve without internet.
- Chess960: without internet, in the offline menu, from a position drawn or typed by its number, against the engine or between two people; and on Lichess, with Play Chess960 beside the rated option, for finding an opponent, challenges and the computer, accepting challenges, correspondence games kept offline and reviewing past games, with its rating in the profile. Castling is tapped on the rook.
- Four more piece sets, chosen for e-ink: Chessnut, MPChess, Kiwen Suwi and Shapes.
- Always promote to a queen, an option beside the look of the board, for games; lessons, practice and puzzles still ask.
- Bring preferences from Lichess, in Settings: promoting to a queen, coordinates, confirming moves and the piece set, copied from the site with the optional permission `preference:read`, which the link for creating a token now marks, since it only reads.
- Block a player from their profile, after a confirmation, and unblock them there too.
- Profiles have the recent activity by day, your private notes about the player (read and written on the device), the FIDE player when the account is linked to one, and the Puzzle Storm records. The players menu has the rankings: the top 10 of each rating.
- The analysis of a position, in the review and in the editor, also offers the most played moves in games of masters and in your own games, with the color you played.
- In the review of a game the site analyzed, More has a summary: the accuracy of each player, their inaccuracies, mistakes and blunders and the average centipawn loss, with the moves where the middlegame and the endgame begin, which the review and the list of moves also mark.
- Puzzle history, in the puzzles menu: the puzzles you tried, the last first, with their rating, when and whether you solved them, and earlier ones a tap away. Any of them opens to be solved again.
- Practice, in the offline menu: the practice lessons of Lichess, 308 of the 316 chapters in all 32 studies of checkmates, tactics and pawn and rook endgames. 165 are played against the engine until you mate, mate in so many moves or promote; 103 ask for an advantage or an equal position in so many moves, judged as the Lichess app judges them, with moves worked out with Stockfish beforehand, so no internet and no strong engine are needed; 3 ask you to hold the draw in king and pawn against king, judged exactly; 36 are guided, with the author's moves to find, comments, hints and the solution; and one is a commented game. The texts are in the three languages, translated from the English of Lichess, and the progress is kept.

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

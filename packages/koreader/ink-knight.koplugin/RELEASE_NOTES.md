# v0.8.0 · 2026-11-25


- Boards in color on color e-ink screens: Wood, Green and Blue, with colors made lighter and of a stronger hue than on Lichess, since color e-ink washes them out. On a color screen, Wood is the board of whoever never chose a style; a style you chose stays, gray or not. On a black and white screen they show in the list in gray, as they would only repeat Plain there. If color is turned off in KOReader, a colored board is drawn plain until it is turned on again.

# v0.7.2 · 2026-11-18


- The analysis by the plugin's Stockfish marks far fewer good moves as mistakes. Each move is now judged against the best move of its own position, since the engine on the e-reader favors the side to move, and comparing the position before a move with the one after it made almost every move look like a loss, opening moves included. On 6 games compared with the analysis of Lichess, the moves marked by mistake went from 66 to 15.
- The same game always gets the same marks: every position is searched to the same depth, in place of a fixed time for each.
- Analysis depth: Quick, Normal or Deep, each with about how long a game takes, chosen in the settings, in the offline menu and where the analysis is offered at the end of a game. A deeper analysis makes fewer mistakes and takes longer.
- Beside each player, the pieces that side has more than the other and "+n" for the side ahead, as on Lichess: in games on Lichess, correspondence, offline games, the review and broadcasts. With the same material nothing shows.
- Computer's time, in the offline menu: Normal, Long (5 s) or Very long (15 s) for each move of the strongest level, which plays better with more time. While it thinks for long, its plate says so and the buttons that do nothing meanwhile are drawn in gray. A move with no other choice is played at once.

# v0.7.1 · 2026-11-17


- Position analysis: when Lichess has no evaluation of the position, a button analyzes it with the plugin's Stockfish for a few seconds, and shows the evaluation and the best line marked as the plugin's engine. In the offline part, the editor has the analysis too, with only the plugin's engine, where it runs.

# v0.7.0 · 2026-11-17


- New look for every screen: black bands for the titles, white cards on a light gray ground, buttons in pills, Yes/No switches, a piece in a circle on the rows, and icons on the buttons of the board. The settings show the board style and the piece set chosen.
- The board sits in a black frame with the coordinates, always shown in the review, practice, studies and the editor. The players are plates with the side's piece, their clock in a pill and what is going on: the opponent's last move, a draw offered, the opponent gone, reconnecting, check, a hint. The line of text under the board is gone, so the board is larger.
- While playing, only the piece picked is marked, with the same dot on every square it can go to; the last move is marked only where a game is read (the review, commented chapters, broadcasts), with corners where it came from and a frame where it went. Arrows and circles have a white edge.
- Questions are cards over the screen, the choice of the promotion rises from the foot, and short notices are a black pill. A question of the game, such as confirming a move or a draw offered, takes the bar as two pills.
- The bar of a game on Lichess stays the same while you play: Back, Draw (Abort before the second move), Resign and More.
- The review shows the players and the result in a band, a bar of the evaluation beside the board, and a card for each move: which move it is and who analyzed it, the move with its judgment, the better move and the evaluation. In a broadcast the card has the clocks.
- Cards over the board when a game ends (with the king of the winner and, in a rated game, how much the rating moved), when a puzzle is solved (with the puzzles solved at the first try in a row) and when a chapter is solved.
- The texts of practice and studies have a heading with the study and the chapter, and a tap reads them whole, in place of the Read button. Commented games have Previous, Next, Comment and Chapter.
- The profile opens under a band with the player, the ratings in cards with their recent progress, Challenge and Follow side by side. The rating chart has periods: 1 month, 3 months, 1 year and all.
- The chess clock is two cards, black for the side to move, with pill buttons. The editor has its palette of pieces under the board.
- Studies has Search studies, with the keyboard of KOReader, and Popular studies: each lists studies with their author and likes, More studies brings the next ones, and any of them opens and can be kept like the others. Names lose the emoji the e-reader cannot draw.
- While the plugin is open, the sleep screen shows the game on the screen, or the one waiting for your turn, under a band that says the e-reader is resting.
- A game on Lichess no longer stops getting the opponent's moves when the connection dies without a word, as when the Wi-Fi of the e-reader dozes: Lichess keeps a game alive with an empty line every 7 seconds, and after 20 seconds of nothing the plugin connects again, showing Reconnecting. Before, the moves only came back after leaving the game and opening it again. The list of games and challenges does the same.
- After a full refresh, the next update waits for it to end, so a tap right after a flash no longer leaves part of the screen white on a Kindle.
- The chess clock marks the time control used last with "Last used" instead of a check mark.
- The offline menu opens at once the first time: the check that Stockfish runs on the device starts in the background when the plugin opens.
- In an offline game the bar of buttons stays the same while you play, so a move does not redraw it; a hint while the computer thinks, or undo with nothing to take back, does nothing.
- The offline opponent is Stockfish, with 8 levels like the computer of Lichess, from a beginner to the full engine. Where it does not run, the small engine plays with its 4 levels as before, and if Stockfish stops in the middle of a game the small engine goes on at the closest level, saying so. A game in progress keeps the engine it started with.
- Hints come from Stockfish too, in the offline game and in practice, much stronger than the small engine's.
- Practice has its last 8 chapters, long endgames of rook or queen to hold the draw or equalize for 7 to 30 moves, judged move by move by Stockfish on the device as the Lichess app judges them. They show only where Stockfish runs.

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

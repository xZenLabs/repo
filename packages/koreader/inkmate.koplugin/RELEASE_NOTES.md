# V1.0.7

v1.0.7: Fix checkmate, Kindle timeouts, offline puzzles, and UI crash
- Fix bug where game-ending moves (like checkmate) were not sent to Lichess server
- Add User-Agent, --http1.1, and -4 to Lichess API curl requests to fix Kindle network timeouts (Errors 28 & 52)
- Fix piece disappearance bug when playing offline puzzles as Black
- Fix crash when closing Lichess game actions menu (redundant UIManager:close calls)
- Change 'Cancel' to 'Decline' for draw/takeback offers for clarity
- Rename 'Solve Puzzles' to 'Offline Puzzles' and 'Daily Puzzle' to 'Online Puzzles'

# v1.0.6


- Fixed a major timer increment bug that granted time incorrectly during stops
- Fixed double-negation issue in the visual evaluation bar, which caused it to display incorrectly
- Resolved Lichess gameState double-processing
- Made Stockfish properly respect game clock times (wtime/btime) rather than hardcoded movetime
- Corrected engine ELO display to reflect accurate Stockfish configuration
- Cleaned up duplicate module requires and fixed PGN update history syntax
- Prevented undo/redo actions from incorrectly restarting the timer in finished games

# V1.0.5

Fixed:

Corrected player labels and clock alignment in the status bar: Fixed a confusing UI bug where the "(Human)" and "(Lichess/Stockfish)" text labels were hardcoded to always display White as the human on the left and Black as the opponent on the right. This caused players playing as Black to accidentally look at their opponent's time, thinking it was their own. The labels now correctly identify who is playing dynamically, ensuring that the "(Human)" tag always matches the correct side of the timer for both online and offline play.

# v1.0.1

**Bug Fixes:**

- Fixed KOReader Crash on Game Actions: Resolved a critical crash that occurred when selecting "Offer draw", "Propose takeback", or "Resign" from the in-game actions menu. This was caused by an immediate widget replacement during a teardown sequence. Callbacks have been properly safely wrapped so the menu closes correctly before the confirmation dialog opens.

- Fixed Lichess Takeback Offers: Resolved an issue where incoming takeback offers from your opponent were being silently ignored. This was due to a strict camelCase formatting requirement in the Lichess streaming API (wTakeback/bTakeback instead of lowercase properties). You will now be correctly prompted when an opponent proposes a takeback.

# v1.0.0

### **Inkmate v1.0.0**

Welcome to the first official release of Inkmate! Based on Casualchess, Inkmate has been completely overhauled to turn your e-reader into the ultimate standalone chess and board game companion.

Whether you want to analyze lines against Stockfish on a plane, play against friends online, or solve your Lichess daily puzzles during your morning coffee, Inkmate is built to deliver a beautiful, e-ink-optimized experience.

 **Key Features**

- Lichess Integration: Log in with your Lichess token to play live online games directly from your e-reader.
- Daily Puzzles: Fetch and solve the official Lichess Daily Puzzle. Puzzle metadata (rating, themes, origin game) are displayed seamlessly below the board.
- **Offline Puzzles:** Load your own puzzles via a local puzzles.csv file for offline practice.
- **Play offline against the Stockfish** engine with adjustable difficulty levels to match your skill.
- More than just Chess: Take a break from chess with fully playable built-in variants and mini-games including Checkers, Reversi (Othello), and Fox and Hounds.
- **Smart Save State:** Close your book or turn off your device at any time. Inkmate automatically saves your current game, timer, and puzzle state so you can resume exactly where you left off.
- E-Ink Optimized UI: A clean, distraction-free interface built specifically for KOReader, featuring touch-friendly buttons, clear piece contrast, and smooth interactions.

🛠️ Installation

1. Download the inkmate.koplugin folder from the source code below.
2. Place the folder into the plugins/ directory of your KOReader installation on your e-reader.
3. Restart KOReader. You will find Inkmate in your plugins menu!

**(Optional) To enable Lichess online features, insert your personal Lichess API token in the plugin's settings menu.**

**Feel free to tweak any wording or add a section if you want to include specific installation instructions or credits! Let me know if you need any adjustments.**

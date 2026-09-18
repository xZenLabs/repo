# V1.0.8

Bug Fixes

1. **Fixed a crash when starting an offline game against the computer.**

- Root Cause: A module name collision within the KOReader ecosystem. Our plugin had a generic file named utils.lua. If a user had other plugins installed that also used the same file name (such as Audiobook, AnnotationSync, or others), KOReader would mistakenly load the other plugin's file instead of ours. This caused InkMate to crash because it couldn't find the specific functions it needed to launch the Stockfish chess engine.

2. **Exit button closes KOReader instead of returning to KOReader.**

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

# v1.1.2

New in this pre-release:

- Two-player "flip board each turn": an option so the board turns to face whoever is on move, instead of one player reading it upside down. Off by default; turn it on in Board & colours.
- Post-game review: after a game, tap Review to see where each side lost the most ground against the neural net, in standard notation.
- Lifetime statistics: games played, current and best win streak, and a won/played record for each difficulty. Reached from the start menu.
- Turkish interface: the whole UI can be set to Türkçe (or left on Auto to follow the device). Change it in Board & colours.

Fixes:
- The Roll button on the board spine is now a compact button instead of an oversized white box.
- In Board & colours, Left and Right are no longer swapped.

# v1.1.1

Refinements:

- A closed-out player (on the bar with every entry point shut) is now skipped automatically, with a note up top, instead of rolling only to press Continue.
- The Roll button now sits on the board spine, where the dice land, so it is within reach of both players in a two-player game.
- New "Board & colours" screen on the start menu: choose whether player 1 plays White or Black and which bottom corner they bear off to. The board layout, colours and labels follow the choice, which is saved for next time.

# v1.0.4

Fixes for long games against the neural-net levels:

- Lower memory use during play, so long matches stay smooth instead of slowing down.
- Shorter pauses between Level 5's moves, since it already takes a moment to think.

# v1.0.3

New in this pre-release:

- **Level 4 "Expert"** and **Level 5 "Master"** — computer opponents powered by GNU Backgammon's neural network, far stronger than the earlier levels.
- Level 5 now correctly evaluates every opponent reply a full roll ahead, so it plays as the strongest level (an earlier build under-filtered its lookahead).
- Difficulty picker now fits all five levels on screen.

Now licensed under GPL-3.0-or-later, since the top levels include GNU Backgammon's trained network (see LICENSE and NOTICE.md).

# v1.0.2

New in this pre-release:

- Level 3 "Skilled" — the computer now looks a full roll ahead (2-ply). Clearly stronger than Level 2.
- Menu button (top-right of the board) — return to the opponent picker at any time, including mid-game and while the computer is thinking. Abandoning a game cleans up fully.

Includes the earlier v1.0.1 fixes (slower, followable computer moves; dead rolls show "Computer can't move" and pass automatically).

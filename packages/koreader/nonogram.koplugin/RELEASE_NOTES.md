# v1.1.0 · 2026-11-10

### Fix ambiguous puzzles and add picture puzzles

Random puzzles could have several valid solutions, and a board was only
accepted if it matched the one stored picture, so a correct solution
could be marked as wrong.

- Generate only puzzles that are solvable by logic alone, which
  guarantees a single solution.
- Treat a board as solved when it satisfies all clues; row/column
  highlighting follows the clues too.
- For games saved by older versions, adopt whichever valid solution
  fits the player's marks so Check, Hint and Show solution agree.
- Add 158 hand-drawn picture puzzles, played in order with the name
  revealed on completion; New game now offers picture or random.

# v1.0.0 · 2025-11-27

-initial release

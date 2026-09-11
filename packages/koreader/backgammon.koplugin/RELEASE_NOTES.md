# v1.1.0

First stable release with computer opponents.

Since 1.0.0:
- Play the computer at five difficulty levels, from a loose beginner to a neural-net master. Levels 4 and 5 use GNU Backgammon's network.
- A setup screen to pick two players or the computer, and a Menu button to switch back mid-game.
- The computer's moves are paced so they're easy to follow, with a clear message when it has no legal move.

Now licensed under GPL-3.0-or-later (see LICENSE and NOTICE.md).

# v1.0.0

Two-player backgammon (tavla) for KOReader - both players share one device and take turns on the same screen.

- Full standard rules: hitting, the bar, bearing off, forced moves, doubles
- Tap a checker to see its legal moves, tap a highlighted point to move - no dragging
- 1 / 2 / 3 point scoring (mars and backgammon) with a session scoreboard
- Portrait and landscape, switchable from an in-game button
- Built for e-ink; pure Lua, no dependencies, nothing written to disk

**Install:** copy the `backgammon.koplugin` folder into KOReader's `plugins` folder and restart. It appears under Tools → Backgammon. See the README for details.

No AI opponent or doubling cube - every game is two humans.

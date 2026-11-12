# Murdoku for KOReader

An **unofficial** [KOReader](https://koreader.rocks) plugin for playing the free
[Murdoku](https://murdoku.com) logic-mystery cases on an e-reader, designed for
touch so **no stylus or pen is needed**. Built and tested for the Kindle Paperwhite
(12th gen), and it works on any KOReader device with a touchscreen, in portrait or landscape.

> **Not affiliated with Murdoku.** This is a fan project. It is not affiliated with,
> endorsed by, or connected to Murdoku, Manuel Garand, or Digivoid Studios Inc.
> Murdoku is created by Manuel Garand. Play online and buy the books at
> **https://murdoku.com**. Murdoku™ is a trademark of Digivoid Studios Inc.
>
> **No murdoku.com puzzles are included in this repository.** The plugin downloads
> the free cases from murdoku.com straight onto your own device, the same files the
> website's player loads. All murdoku.com puzzles, names and clues are © their creators.
> The "Originals" pack and "Random" cases are made by this project's own generator
> (`tools/generator/`); they are not murdoku.com cases and are not derived from them.

<p align="center">
  <img src="docs/img/game.png" width="30%" alt="A case in progress in portrait">
  <img src="docs/img/case-list.png" width="30%" alt="The case list">
  <img src="docs/img/suspect.png" width="30%" alt="Holding a suspect shows their card">
</p>
<p align="center">
  <img src="docs/img/landscape.png" width="62%" alt="An 8x8 case in landscape with the suspect cards beside the board">
</p>

## Features

- Every free case on murdoku.com, including each new release (the newest is starred ★).
- **Originals** (◆): a pack of 30 cases made for this plugin (6 very easy, 9 easy, 9 medium,
  6 hard; 5×5 to 9×9; lighthouses, manors, museums, ski lodges…). They ship with the plugin,
  so they work offline with no download.
- **New random case** (⚄, in the case list's ☰ menu): pick a difficulty (very easy, easy,
  medium, or hard up to 6×6) and a size (5×5 to 9×9) and the plugin makes a fresh case on your device. Every
  case has exactly one solution, reachable by logic alone, with step-by-step hints. Random
  cases stay in the list until you delete them (hold the case). Bigger hard cases are too
  slow to make on an e-reader, so they're only in the Originals pack.
- General clues (rules that apply to everyone) are shown in the clue box and in All clues.
- **Download all cases** for offline play. Retired cases you've downloaded stay playable.
- Filter by source (murdoku.com / Originals / Random), difficulty (Very easy → Expert) and
  solved/unsolved; sort by newest, oldest,
  difficulty, name or grid size. The list header shows how many cases you've solved.
- **Suspect cards** under the board (beside it in landscape): a face, the name with its
  initial as a badge, and the clue with its key words in **bold**. Hold a card for the full
  clue.
- **Clue highlighting**: select a suspect and the squares their clue allows are outlined on
  the board ("in the Library, but not beside a shelf", "in the top row", "north of Freya"
  once Freya is placed…). Turn it off in the menu if you prefer to work it out yourself.
- **Icons** for every object, white on dark for obstacles and black on light for things you
  can stand on, sit on or lie on.
- Finger-friendly controls built for e-ink, matching murdoku.com:
  - Tap a suspect to select them. Then **tap** a square to pencil in a note, or **hold** a
    square to place them. Placing someone crosses out the rest of their row and column
    with real X marks (undoable), and clears the selection. Taking them off again removes
    those automatic X marks but keeps the ones you made.
  - With nobody selected, tap a square to X it out, or **swipe** across a row or column to
    X out a whole line.
  - Icon toolbar: X (mark mode), eraser, undo, hint, check, menu.
  - **Hold** a square to see what's there ("You can stand here." / "You can't stand here.").
    Hold a suspect to read their clue.
  - Unlimited undo, saved with the case so it still works after closing and reopening.
  - Check (flags misplaced suspects with **!**), step-by-step hints, reveal solution.
  - A live timer in the title bar. It stops while the device sleeps, and a long pause
    without a tap only counts a few minutes.
- Rows and columns are labelled R1… and C1…. Squares nobody can stand on are dark; everything
  you can stand on (floor, carpets, chairs, beds, boats…) is light.
- Portrait and landscape layouts, including grids that aren't square (e.g. 11×9), up to 16×16.
- Progress is saved after every move: leave a case half-solved and pick it up later (marked … in the list).

## Install

**With [Storefront](https://github.com/ultimatejimmy/storefront.koplugin)** (easiest):
open Storefront on your e-reader, search for **Murdoku**, and tap Install. Storefront
also tells you when there's an update.

**By hand:**

1. Download `murdoku.koplugin.zip` from the [latest release](../../releases/latest)
   (or clone this repo).
2. Connect your Kindle over USB and copy the `murdoku.koplugin` folder into
   `koreader/plugins/` so you end up with `koreader/plugins/murdoku.koplugin/main.lua`.
3. Restart KOReader.
4. Open the top menu → **Tools** (🛠) → **Murdoku**. Turn on Wi-Fi the first time so the case list can download.

Tip: Use the ☰ menu on the case list to **Download all cases for offline play**.
You can also assign "Murdoku" to a gesture under *Settings → Taps and gestures*.

## What's new in 1.3.0

- A new look: suspect cards with faces, object icons, dark squares for obstacles, R1/C1
  labels, an icon toolbar and clue highlighting.
- murdoku.com-style controls: tap for a note, hold to place, an eraser, automatic X marks.
- A brand-new Originals pack of 30 cases, each built around a satisfying "aha" step, with
  one-idea-at-a-time hints.
- A rewritten How to play with examples for every kind of clue.
- The timer no longer counts while the device is asleep.

## How to play

Place every character on the crime scene so that:

- there is exactly one person in each row and each column;
- nobody stands on an obstacle;
- every suspect's clue is true ("beside" = directly left/right/above/below **and in the same area").

The murderer is the one person who was **alone with the victim** in the same area.
The game checks automatically once everyone is placed. The full rules, with examples,
are in the game's menu under **How to play**.

## Development

```
murdoku.koplugin/
  main.lua             menu entry, case list, downloads, random-case dialog
  murdoku_game.lua     game screen, controls, portrait/landscape layout
  murdoku_board.lua    grid & suspect-bar drawing
  murdoku_puzzle.lua   puzzle JSON parser (no KOReader deps)
  murdoku_store.lua    HTTP, caching, saved progress
  murdoku_objects.lua  object table (which items can be stood on)
  murdoku_solver.lua   clue atoms, solution counter, logical solver/grader (no KOReader deps)
  murdoku_clues.lua    clue sentences for a known solution (no KOReader deps)
  murdoku_gen.lua      on-device generator: layout, clues, hints, export (no KOReader deps)
  murdoku_steps.lua    step solver naming each technique; "designed aha" accept filter/score
  murdoku_themes.lua   themed rooms/names/titles, generated from tools/generator/mgen/themes.py
  cases/               the bundled Originals (site v2 JSON) and index.json
tests/test_puzzles.lua    parser check (built-in checks + any folders of puzzle JSON files)
tests/test_generator.lua  on-device generator check: fixed seeds, uniqueness, timings
tools/generator/          offline generator (Python): --pack, --check, --bench
```

The offline generator writes cases in the site's v2 JSON format, so the normal parser
loads them unchanged. By default it makes "designed aha" cases (`mgen/aha.py`): a step
solver names the technique of every deduction, and the clue set is hill-climbed until the
solve has a mid-solve aha (cross-block, line-clash, subset, "who can be the person in the
car?", or a quick what-if) followed by a cascade of easy placements, with the victim placed
last or second to last (`--classic` uses the older pipeline). `--check` re-parses each case's clue **text** and confirms it has
exactly one solution, equal to the stored one:

```sh
python3 tools/generator/murdoku_gen.py --size 7 --difficulty medium --seed 42 --out /tmp/case.json
python3 tools/generator/murdoku_gen.py --check murdoku.koplugin/cases/orig-*.json
python3 tools/generator/murdoku_gen.py --pack --out-dir murdoku.koplugin/cases --playtest-dir /tmp/playtest
python3 tools/generator/export_lua_themes.py   # after editing mgen/themes.py
```

Run the parser test with KOReader's bundled LuaJIT against puzzles you've downloaded:

```sh
KO=/path/to/koreader
LUA_PATH="$KO/common/?.lua;;" LUA_CPATH="$KO/common/?.so;;" $KO/luajit tests/test_puzzles.lua murdoku.koplugin/cases /path/to/puzzle/jsons
LUA_PATH="$KO/common/?.lua;;" LUA_CPATH="$KO/common/?.so;;" $KO/luajit tests/test_generator.lua 20
```

Downloaded cases are stored in `koreader/murdoku/` on the device (random cases in `koreader/murdoku/random/`).

## Support the plugin

If you enjoy the cases, please buy the books:
[Murdoku Volume 1 on Amazon](https://link.amazon/B04hUyE9T). This is an **affiliate link**:
buying through it supports this plugin at no extra cost to you. The rest of the series is
on the same Amazon page.

## Credits

Object icons made by Delapouite, Lorc, Skoll, Caro Asercion, John Redman, Pierre Leducq,
Faithtoken and HeavenlyDog, from https://game-icons.net, licensed under CC BY 3.0
(https://creativecommons.org/licenses/by/3.0/). Changes: recoloured to black and white
and converted to standalone SVG. Also Fluent Emoji High Contrast © Microsoft Corporation (MIT),
Material Design Icons © Pictogrammers (Apache 2.0), Temaki by Bryan Housel (CC0), and
toolbar icons from Lucide (ISC). Suspect portraits are built from Open Peeps by Pablo
Stanley (CC0). See `murdoku.koplugin/ATTRIBUTION.md` for the full list and licence texts.

## License

The plugin code and the Originals pack are MIT licensed (see `LICENSE`). That license
covers only what is in this repository, not murdoku.com puzzles or Murdoku trademarks.

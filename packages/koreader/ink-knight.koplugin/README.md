<p align="center">
  <img src="docs/brand/banner.png" alt="Ink Knight: a Lichess client for KOReader">
</p>

<p align="center">
  <strong>A Lichess client for KOReader. Play live and by correspondence, solve puzzles and review your games on e-ink.</strong>
</p>

<p align="center">
  <a href="https://github.com/beater-studios/ink_knight.koplugin/releases/latest"><img src="https://img.shields.io/github/v/release/beater-studios/ink_knight.koplugin?style=flat-square&color=111111&label=release" alt="Latest release"></a>
  <a href="https://github.com/beater-studios/ink_knight.koplugin/actions/workflows/ci.yml"><img src="https://img.shields.io/github/actions/workflow/status/beater-studios/ink_knight.koplugin/ci.yml?branch=main&style=flat-square&label=tests" alt="Tests"></a>
  <a href="https://koreader.rocks"><img src="https://img.shields.io/badge/KOReader-2026.07-111111?style=flat-square" alt="Built for KOReader 2026.07"></a>
  <img src="https://img.shields.io/badge/languages-EN%20%C2%B7%20PT%20%C2%B7%20ES-111111?style=flat-square" alt="English, Portuguese and Spanish">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-GPL--3.0-111111?style=flat-square" alt="License: GPL-3.0"></a>
</p>

<p align="center">
  <a href="#what-it-does">What it does</a> ·
  <a href="#installation">Installation</a> ·
  <a href="#connect-your-account">Connect your account</a> ·
  <a href="#what-stays-out">What stays out</a> ·
  <a href="#development">Development</a> ·
  <a href="README_pt.md">Leia em português</a>
</p>

> [!NOTE]
> Ink Knight is not an official Lichess product and has no ties to Lichess.

## What it does

<table>
  <tr>
    <td width="25%" align="center"><img src="docs/screenshots/start.png" alt="First page, with play online and play offline"><br><sub><b>First page</b></sub></td>
    <td width="25%" align="center"><img src="docs/screenshots/games.png" alt="Your games, with the challenges received and sent above them"><br><sub><b>Your games</b></sub></td>
    <td width="25%" align="center"><img src="docs/screenshots/game.png" alt="A game in progress on the newspaper board, with Merida pieces, coordinates and clocks"><br><sub><b>Playing</b></sub></td>
    <td width="25%" align="center"><img src="docs/screenshots/puzzle.png" alt="A puzzle waiting for the best move"><br><sub><b>Puzzles</b></sub></td>
  </tr>
  <tr>
    <td width="25%" align="center"><img src="docs/screenshots/styles.png" alt="Choosing a board style, with a sample of each one"><br><sub><b>Board styles</b></sub></td>
    <td width="25%" align="center"><img src="docs/screenshots/moves.png" alt="The moves of a game, two to a row, with the one shown marked"><br><sub><b>List of moves</b></sub></td>
    <td width="25%" align="center"><img src="docs/screenshots/hint.png" alt="A game against the offline engine, with a suggested move marked"><br><sub><b>Hint, offline</b></sub></td>
    <td width="25%" align="center"><img src="docs/screenshots/two_players.png" alt="A game between two people on the same device"><br><sub><b>Two players</b></sub></td>
  </tr>
</table>

- **Your choice on opening:** the first page asks whether to play online or offline, and Lichess is only contacted if you choose online. The time and the battery stay at the bottom of every screen.
- **Play:** find an opponent in rapid and classical, by correspondence, challenge a friend (blitz or no time limit too) or play the Lichess computer. In a challenge, you can pick your color. The challenges you sent wait beside the ones you received, and you can cancel them.
- **Several games at once:** the list shows whose turn it is, with the games waiting for you on top. It refreshes at the interval you choose.
- **During a game:** clocks, promotion, draw offers and draws by repetition, asking for a takeback, giving time, resigning and canceling. The list of moves is one tap away, here and in the other modes, and starts with the name of the opening, even without internet (in a Lichess game, once it is over). When the game ends, play again. A dropped connection comes back by itself.
- **Puzzles:** a pile stays on the device to solve without internet, and results go to Lichess when the Wi-Fi returns. Also puzzles by theme and by opening, the history of the ones you tried, your results and the daily puzzle, and you can choose the difficulty, compared with your puzzle rating, and the color you play. You can also review the puzzles you missed in the last 30 days, including the ones missed on the site.
- **Review:** your past games and favorites, move by move, with what Lichess knows about each position: its evaluation, the most played moves (on Lichess, by masters and in your own games) and, near the end, the perfect result, and for a game analyzed on the site, the accuracy of each player.
- **Players:** search by name, see who you follow is online, profiles with the recent activity, your private notes, the FIDE rating and the Puzzle Storm records, a rating chart with statistics, your record against someone, and the top 10 of each rating.
- **Without internet:** play a small engine that never freezes the screen, with your choice of color, undo and hints, and continue the game later. Or play against someone else on the same device, with a clock if you like, or solve the 5000 puzzles that come with the plugin, no account needed, at the difficulty you choose. After a game, the engine can point out your clear mistakes. Set up any position in the editor and play from it. For beginners, Learn chess has the 18 stages of the Lichess app, from how each piece moves to checkmate, with stars to collect, and Practice has the practice lessons of Lichess: checkmates, tactics and endgames played against the engine, or guided move by move. There is also coordinate training: find the square named, or name the square marked, against the clock. And a chess clock for a game on a real board, with the device lying between the players. Your correspondence games stay on the device too: you can look at them and make your move with the Wi-Fi off, and it goes to Lichess the next time you play online, if the game is still where you left it.
- **Your board:** five board styles, including the hatched squares of printed diagrams, three piece sets and coordinates on the edges.
- **Sleep screen:** if the device sleeps with Ink Knight open, it shows the Ink Knight cover instead of the book cover. This applies when the KOReader sleep screen is set to show the book cover.

## Installation

1. Download `ink_knight.koplugin.zip` from the [latest release](https://github.com/beater-studios/ink_knight.koplugin/releases/latest).
2. Extract it into `koreader/plugins/`, so that `koreader/plugins/ink_knight.koplugin/main.lua` exists.
3. Restart KOReader. The plugin is in the Tools menu, as **Ink Knight**.

The release has two more packages with the same plugin and more puzzles to solve offline: `ink_knight-20000-puzzles.koplugin.zip` (about 1.2 MB) and `ink_knight-50000-puzzles.koplugin.zip` (about 2.5 MB), against 5000 puzzles in the usual one. To change, extract another over the installed folder; your progress is kept.

The language follows KOReader's: English, Portuguese or Spanish. In any other language, it uses English.

Your options, the games without internet and the saved puzzles are in `koreader/settings/ink_knight.lua`, and the token in `koreader/settings/ink_knight_token` or, on a Kindle, in `/var/local/ink_knight`. To uninstall, remove the plugin folder and these files, and revoke the token on Lichess.

## Connect your account

Ink Knight uses a personal token, which only you can create and revoke.

1. In Ink Knight, tap **Connect account** and **Create a token on Lichess**. A QR code opens [the page that creates a token](https://lichess.org/account/oauth/token/create) on your phone with the permissions marked. With no camera, turn on only these there:
   - External play: `board:play`, the only one needed to play online
   - Interactions: `follow:read` and `follow:write`, for who you follow and who you block
   - Puzzles: `puzzle:read`, for batches, themes, openings and your puzzle history, and `puzzle:write`, to send your results
   - Play games: `challenge:write`, only to give time to an opponent
   - Optional, only to add or remove favorites: `preference:write`. It comes unmarked, because it also allows changing your account preferences, which Ink Knight never does.
   - Optional, only for your private notes about players: `note:write`, which Lichess asks for even to read them. It comes unmarked.
   - Optional, only to bring your preferences from the site (always promote to a queen, coordinates, confirming moves and the piece set): `preference:read`. It only reads, so it comes marked.
2. Create the token, copy it and tap **Done: paste the token**.
3. On the same Wi-Fi network, point your phone at the QR code or type the address shown below it in any browser, tap **Allow** on the e-reader and paste the token.

Without a permission, the rest keeps working, and what depends on it says what is missing when you tap it, optional ones included. **Settings > Token permissions** shows what your token allows. Lichess does not change an existing token, so adding a permission means creating another.

> [!WARNING]
> On a Kindle, the token stays in the system partition, out of reach over USB, where Ink Knight keeps it private. The Kindle's own services can reach it after a reboot, until you open Ink Knight. On other devices, Ink Knight checks whether the file can really be protected, and warns you when it cannot, since shared storage ignores file permissions. Anything running as root can still read it, including other plugins, so if you lose the device or suspect a leak, revoke the token on Lichess. Never publish it.

<details>
<summary><b>What protects your token</b></summary>

<br>

- **Sent only to Lichess**, over HTTPS with the certificate checked, and kept in memory while in use.
- **The page on your network** only exists while that screen is open, needs a random code in the address and your tap on the e-reader, serves a single device, only works on private networks, and refuses other sites. Since a local server has no certificate, use it on a network you trust.
- **Only what is needed.** The permissions above cannot send private messages, change your account or read your email.

The full list is in [docs/design.md](docs/design.md).

</details>

## What stays out

- **Bullet and tournaments:** e-ink is too slow for them. Lichess only allows blitz through a direct challenge.
- **Engine help in a Lichess game:** it is cheating and can get your account banned. The offline engine never touches a game on Lichess.
- **Bots:** that API needs turning your account into a bot account.

## Compatibility

- Made for KOReader 2026.07 and for touchscreens, always in portrait. It was developed for a 10th generation basic Kindle (firmware 5.18.1).
- Uses only what comes with KOReader, with nothing else to install.
- The clock keeps running in a live game if you leave its screen, so Ink Knight asks first. During a game with a clock, the device stays awake, which costs battery. The power button still puts it to sleep.

## Development

With [LuaJIT](https://luajit.org) and `zip` installed, from the repository root, this runs the tests, checks the texts of the three languages and builds the package:

```sh
sh tools/check.sh
```

The design, the tools and the release process are described in [docs/design.md](docs/design.md). Contributions are accepted under the project's license.

## License

[GPL-3.0](LICENSE), version 3 only. You may use, study, modify and redistribute it, keeping it open under the same license.

Lichess is a trademark of its owners, and this license grants no rights to it or to the names "Ink Knight" and "Beater Studios". See [NOTICE](NOTICE). The classic pieces are drawn from the FreeSerif font that comes with KOReader, and the Cburnett and Merida pieces are by Colin M.L. Burnett and Armando Hernandez Marroquin, under GPLv2 or later. The names of the openings and the included puzzles come from the open Lichess data, in the public domain (CC0), the lessons of Learn chess and their texts and the practice lessons from the official Lichess app, under GPL-3.0, the practice ones written for lichess.org by their authors and translated into Portuguese and Spanish here.

---

<p align="center">
  <sub>Made by <a href="https://beaterstudios.com/">Beater Studios</a></sub>
</p>

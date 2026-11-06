<p align="center">
  <img src="docs/cover.png" alt="Kindle × Orca: Claude Code sessions on a Kindle">
</p>

<h1 align="center">Kindle × Orca</h1>

<p align="center">
  Use a jailbroken Kindle as an e-ink remote for your <a href="https://github.com/stablyai/orca">Orca</a> sessions
  (Claude Code, Codex…).<br>
  Read a book, get a ping when Claude needs a decision, answer with one tap, go back to reading.
</p>

<p align="center">
  <a href="#getting-started">Getting started</a> ·
  <a href="#what-you-can-do">What you can do</a> ·
  <a href="#how-it-works">How it works</a> ·
  <a href="#development">Development</a>
</p>

---

- **A dashboard that answers "does anything need me?"**: the waiting question with
  its answer buttons, your sessions, pull requests with their checks, Claude's
  usage limits, and your week.
- **Drive sessions from e-ink**: a terminal view sized to the Kindle, buttons for
  what agents ask most, free typing, and live updates.
- **Git and pull requests**: changes, commit with a drafted message, push, open
  a pull request, read its checks, re-run them, merge, or ask Claude to fix them.
- **Notified while you read**: a popup over your book with the question and
  its buttons, and a sleep screen that shows what needs you.
- **Reading and coding side by side**: your book's progress and reading heatmap
  next to your GitHub contributions.
- **Books both ways**: send plans, reviews and diffs to the Kindle as EPUBs; send
  a highlighted passage to Claude.

## Screenshots

All taken on a Kindle Basic (10th gen, 600×800). The projects, sessions and
pull requests are demo data ([how](tools/screenshots/README.md)).

<table>
  <tr>
    <td align="center"><img src="docs/screenshots/home.png" width="250"><br><sub><b>Home</b>: what needs you first</sub></td>
    <td align="center"><img src="docs/screenshots/session.png" width="250"><br><sub><b>A session</b>, answered from the Kindle</sub></td>
    <td align="center"><img src="docs/screenshots/sleep.png" width="250"><br><sub><b>Sleep screen</b>: still useful asleep</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="docs/screenshots/home-prs.png" width="250"><br><sub><b>Pull requests</b> and Claude's limits</sub></td>
    <td align="center"><img src="docs/screenshots/home-week.png" width="250"><br><sub><b>This week</b> and your book</sub></td>
    <td align="center"><img src="docs/screenshots/home-reading.png" width="250"><br><sub><b>Reading</b> next to GitHub</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="docs/screenshots/notify.png" width="250"><br><sub><b>A popup</b> over your book</sub></td>
    <td align="center"><img src="docs/screenshots/git.png" width="250"><br><sub><b>Git</b> and the branch's pull request</sub></td>
    <td align="center"><img src="docs/screenshots/chats.png" width="250"><br><sub><b>Conversations</b> across projects</sub></td>
  </tr>
</table>

## Getting started

You need a jailbroken Kindle with [KOReader](https://github.com/koreader/koreader),
Tailscale on both the Kindle and the PC, and Orca running on the PC.

1. **Install KOReader** via KPM: `;kpm install koreader`.
2. **Copy both plugins** into `koreader/plugins/` on the Kindle:
   `tailscale.koplugin/` and `orca.koplugin/`. Each
   [release](https://github.com/ManzoliW/orca.koplugin/releases) has a zip of
   each plugin (and `SHA256SUMS`); unzip them into `koreader/plugins/`.
3. **Start Tailscale on the Kindle**: KOReader → Network → Tailscale → Setup
   (auth key, binaries), then tick **Connected**. That menu is only for
   setup: it starts by itself with KOReader after that, and Orca's status
   line shows it and turns it on or off.
4. **Pair with Orca**: on the PC, Orca → Settings → Mobile. Save the pairing
   link to `/mnt/us/orca-pairing.txt` on the Kindle, then open KOReader →
   Tools → **Orca**, tap **⚙** in its title bar → Pairing → **Import**. The
   file is deleted after import.
5. **Test it**: tap the status line at the top of Orca → **Test connection**. It reports
   either the number of workspaces found or the step that failed.
6. **Kindle firmware 5.16 or later**: copy the two files in
   [`koreader-patches/`](koreader-patches) (also `koreader-patches.zip` in
   each release) to `koreader/patches/`. Newer firmware draws its status bar
   with a process KOReader doesn't know about, and it repaints over
   KOReader's top corners every minute; the patches pause it while KOReader
   runs.

Then open it with Tools → **Orca**, or bind **Open Orca** to a gesture
(KOReader → Settings → Taps and gestures) to open it with one tap from a
book. Every Orca screen has the clock, Tailscale, the PC link and the battery
at the top: tap that line to turn Tailscale on or off or test the
connection. **⚙** next to ‹ / ✕ holds the settings:

<p>
  <img src="docs/screenshots/connection.png" width="250" alt="The connection card the status line opens">
  <img src="docs/screenshots/menu.png" width="250" alt="Orca settings (⚙)">
</p>

> [!WARNING]
> The pairing link is a device credential. Keep it out of chats, screenshots
> and repositories. Revoke it in Orca → Settings → Mobile if it leaks.

## What you can do

### Home

Orca starts on a dashboard, most urgent first:

| Card | What it shows |
| --- | --- |
| **The question waiting for you** | The agent's question as a black card, with its choices as buttons (**1 Yes**, **2 …**, **Esc**) and **Open session**. |
| **Sessions** | Workspaces with an agent at work: ● Needs you, ◐ Working, ○ Done. |
| **Your pull requests** | The open ones you authored, across Orca's projects, with their checks (✓ ✕ …). Tap one for its checks, **Merge…**, **Re-run** or **Ask Claude to fix…**. |
| **Claude usage** | The 5-hour and weekly limits as bars, with when they reset. |
| **Activity** | Chats today, agents started, pull requests merged this week, agent time. |
| **This week** | Reading time against the week before, pull requests merged and GitHub contributions, agent time. |
| **Continue reading** | The book you opened last, with its cover, progress and time read today. |
| **Reading** | Minutes read per day, from KOReader's statistics, as a heatmap with your streak. |
| **GitHub** | Your public contribution calendar, drawn the same way. |
| **From Claude** | Documents Claude sent to the Kindle, **New** until you open them. |

Tabs at the bottom lead to **Workspaces** and **Chats**; tap the usage bars
for your accounts. A workspace with a single session opens that session
straight from Home. The last dashboard shows at once while the new one loads,
and the Kindle's own cards (reading, GitHub, documents) work without the PC.
When the PC can't be reached because Tailscale is off, the card says so with
**Start Tailscale**.

<img src="docs/screenshots/cards.png" width="220" align="right">

**Home cards…** (**⚙**) lets you hide each card on Home or on the sleep
screen, and change their order: the sleep picture leaves out what doesn't
fit, so this is also how you choose what it keeps.

<br clear="right">

<details>
<summary>Where the numbers come from</summary>

- Usage and totals are reused for 5 minutes, conversations for 15 (listing
  them makes the desktop scan transcripts); **↻** fetches everything again.
- Pull requests come through Orca, with your desktop's GitHub login, and are
  reused for 15 minutes.
- The contribution calendar is GitHub's public page (no token): the Kindle
  fetches it itself, at most twice a day, and keeps it for offline use. Your
  GitHub user is the author of your pull requests, or set it in **⚙** →
  **GitHub user**.
- Orca only reports lifetime totals, so for **This week** the Kindle keeps
  one snapshot a day and subtracts the one from a week ago. During the first
  week agent numbers count from the first snapshot.

</details>

### Sessions

<img src="docs/screenshots/workspaces.png" width="220" align="right">

- **Drive a session**: the terminal is resized to the Kindle's width while you
  look at it (and restored after). Buttons cover what agents ask most: `1 2 3`,
  `Esc`, `Ctrl-C`, arrows, `Tab`/`S-Tab`, `Enter`, and **Type…** for free text.
  Swipe down to read what scrolled off; **Rotate** for landscape.
- **Browse**: the **Workspaces** tab lists every workspace, needs-you first,
  and each session with its agent's state.
- **Start something new** (**+**): a workspace with Claude already working on
  your prompt, one linked to a GitHub issue or PR, a clone from GitHub, or a
  new empty project.
- **Conversations** (the **Chats** tab): your latest agent conversations across
  projects. Read one as a book, or **Continue on desktop** to resume it.

<br clear="right">

### Workspaces, git and pull requests

<img src="docs/screenshots/pr.png" width="220" align="right">

Inside a workspace:

- **Git**: branch and ahead/behind, changed files with their diffs,
  **Commit…** (the desktop's agent drafts the message), **Commit and push**,
  **Push**, **Pull**, **Create pull request…** (or a draft), and **Read all
  changes as a book**.
- **Pull request**: its checks (✓ ✕ …); tap one for the failing steps and
  annotations. **Re-run the failed checks**, **Ask Claude to fix…** (a session
  with the failing checks' names), or **Merge…** (squash, merge or rebase).
- **Files**: browse and read the checkout. **Open as book**, or **Ask
  Claude…** about a file.
- **Sleep or remove…** the workspace (the branch is kept).

<br clear="right">

### While you read

<img src="docs/screenshots/sleep.png" width="220" align="right">

- **Notifications** (**Notify me while I read**): a popup appears over your
  book the moment a session asks something or finishes, with the question and
  **1 2 3 Esc**, so you can answer without leaving the page. When the Kindle
  wakes, it catches up on what happened while it slept.
- **The sleep screen** (**Claude status on the sleep screen**): the sleeping
  Kindle shows a picture of Home's cards: the waiting question, usage, sessions,
  your book and heatmaps, and on Mondays your week. Waking it on a question
  opens Orca on that question.
- **Send a passage to Claude**: select text and pick **Send to Claude** in the
  highlight menu. Choose **Explain**, **Context** or **Save note**, or ask your
  own question; it goes to your last session with the book, author and chapter.

<br clear="right">

<details>
<summary>How the sleep screen works, and what notifications cost</summary>

- A Kindle draws its sleep screen before plugins hear about the suspend, so
  the plugin redraws the picture every 5 minutes while the Kindle is awake
  and points KOReader's sleep screen at it (a random image from a folder that
  holds only this picture). KOReader's sleep message is kept up to date too,
  and shows if the picture can't be drawn. Turning the option off restores
  your previous sleep screen.
- Waking on a question doesn't open Orca over its own screens or over a popup
  that already asks it (**⚙** → **Open the question when I wake the
  Kindle** turns it off).
- Battery: the notification stream costs about 5 mA while the Kindle is
  awake (52 mA vs 48 mA on a Kindle Basic, Wi-Fi on), roughly 10% less
  reading time. Asleep, Wi-Fi is off and it costs nothing.

</details>

<p>
  <img src="docs/screenshots/highlight-menu.png" width="220">
  &nbsp;
  <img src="docs/screenshots/ask-dialog.png" width="220">
</p>

### Documents both ways

`tools/send_to_kindle.py` turns Markdown (plans, reviews, reports, diffs) into
an EPUB that reads well on e-ink and copies it to `documents/Claude/`, over
Tailscale or USB. In Claude Code, the `/send-to-kindle` skill does it for you.
`tools/pull_notes.py` brings your KOReader highlights and notes back as
Markdown.

```sh
python tools/send_to_kindle.py plan.md --title "Refactor plan"
git diff main | python tools/send_to_kindle.py - --title "Review: my-branch"
python tools/pull_notes.py --since 2026-10-01 --out notes.md
```

### Usage and accounts

Tapping the usage bars on Home shows the 5-hour and weekly limits and Orca's
totals, and with more than one Claude account in Orca, lets you pick the one
new sessions use.

### Languages

The plugin follows KOReader's language. It ships in English, Brazilian
Portuguese and Spanish; a new language is one file in
[`orca.koplugin/orca/l10n/`](orca.koplugin/orca/l10n), and the tests list any
string it misses.

## How it works

```
Kindle (KOReader)                                   PC
┌──────────────────────┐                        ┌──────────────────┐
│ orca.koplugin        │  WebSocket, NaCl box   │ Orca             │
│  └ orcaclient/       │ ─────────────────────▶ │  mobile RPC      │
│ tailscaled           │   SOCKS5 :1055 →       │  :6768           │
│  (userspace mode)    │   tailnet              │                  │
└──────────────────────┘                        └──────────────────┘
```

- **Protocol**: the plugin speaks Orca's mobile protocol directly: a WebSocket
  on port 6768 with an end-to-end encrypted handshake (X25519 +
  XSalsa20-Poly1305, via a TweetNaCl build for the Kindle in
  `native/tweetnacl/`).
- **Networking**: 10th-gen Kindles have no TUN device, so `tailscaled` runs in
  userspace mode and apps reach the tailnet through its SOCKS5 proxy on
  `localhost:1055`. The patched Tailscale plugin sets that up, and can also
  forward local ports so KOReader's OPDS/Calibre browser can reach the PC.
- **No freezes**: network work runs in coroutines stepped by KOReader's UI
  loop, so the reader stays responsive while waiting on the network.

The modules and the design rules for the e-ink UI are in
[docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

## Development

```sh
luajit tests/run.lua                  # every screen against a fake Orca (also in CI)
python tools/kindlectl.py deploy      # copy the plugin to the Kindle over SSH
python tools/kindlectl.py restart     # and restart KOReader
python tools/kindlectl.py shot out.png
```

| Path | What |
| --- | --- |
| `orca.koplugin/` | The KOReader plugin; `main.lua` only wires it together |
| `orca.koplugin/orca/` | `core/` (settings, jobs, connection, i18n), `api/` (Orca RPC wrappers), `ui/` (e-ink UI kit), `features/` (one file per screen or behavior), `render/` (terminal text, diffs, heatmaps), `l10n/` (translations) |
| `orca.koplugin/orcaclient/` | Orca's mobile protocol: WebSocket, NaCl handshake, RPC and streams |
| `tailscale.koplugin/` | Tailscale plugin, patched for kernels without TUN; autostart; port forwards |
| `koreader-patches/` | Keep the Kindle's status bar from drawing over KOReader (firmware 5.16+) |
| `native/tweetnacl/` | NaCl cross-build for armv7 (`build.sh`, needs Zig) |
| `tools/` | PC side: `kindlectl.py` (screenshot, tap, deploy over SSH; set `KINDLE_HOST`), `send_to_kindle.py`, `pull_notes.py`, `screenshots/` (demo data and the cover) |
| `tests/` | PC tests with a fake Orca and stubbed KOReader; `tests/device/` runs on the Kindle, and `rpc_probe.lua` there calls the real desktop |
| `.claude/skills/` | The `send-to-kindle` skill for Claude Code |

**Tested on** a Kindle Basic (KT4, 10th gen), firmware 5.18.1.1.1, KOReader
2026.07.1, with Orca on Windows 11. Other Kindles that run KOReader should
work; `kindlectl`'s touch profile may need adjusting (see
[tools/README.md](tools/README.md)).

## License

[GPLv3](LICENSE), like KOReader.

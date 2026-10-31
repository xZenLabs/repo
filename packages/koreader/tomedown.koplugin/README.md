<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.png">
    <source media="(prefers-color-scheme: light)" srcset="assets/banner-light.png">
    <img src="assets/banner-light.png" alt="tomedown: one Markdown file per book, straight into your notes" width="480">
  </picture>
</p>

<p align="center">
  <a href="https://ko-fi.com/imanubdesigner"><img src="https://img.shields.io/badge/Ko--fi-Buy%20me%20a%20coffee-FF5E5B?style=for-the-badge&logo=ko-fi&logoColor=white" alt="Buy me a coffee on Ko-fi"></a>
  <img src="https://img.shields.io/badge/KOReader-171717?style=for-the-badge&logo=koreader&logoColor=white" alt="KOReader">
  <img src="https://img.shields.io/badge/Obsidian-171717?style=for-the-badge&logo=obsidian&logoColor=white" alt="Obsidian">
  <img src="https://img.shields.io/badge/Markdown-171717?style=for-the-badge&logo=markdown&logoColor=white" alt="Markdown">
  <img src="https://img.shields.io/badge/Lua-171717?style=for-the-badge&logo=lua&logoColor=white" alt="Lua">
</p>

<p align="center">
  <a href="https://github.com/imanubdesigner/tomedown.koplugin/releases/latest"><img src="https://img.shields.io/github/v/release/imanubdesigner/tomedown.koplugin?style=for-the-badge&color=171717&labelColor=171717&logo=github&logoColor=white" alt="Latest release"></a>
  <a href="https://github.com/imanubdesigner/tomedown.koplugin/actions/workflows/test.yml"><img src="https://img.shields.io/github/actions/workflow/status/imanubdesigner/tomedown.koplugin/test.yml?style=for-the-badge&labelColor=171717&logo=githubactions&logoColor=white&label=tests" alt="Test status"></a>
  <a href="LICENSE"><img src="https://img.shields.io/github/license/imanubdesigner/tomedown.koplugin?style=for-the-badge&color=171717&labelColor=171717" alt="License"></a>
</p>

<p align="center">
  Questions, ideas, feedback: <a href="https://github.com/imanubdesigner/tomedown.koplugin/discussions">GitHub Discussions</a>
</p>

## Tomedown

I made Tomedown because I wanted my books organized in a single `.md` file
holding all my highlights.

Every book you read in KOReader becomes one Markdown file of its own, with
YAML frontmatter and an automatic index. The files are written to a folder on
the device first (`clipboard/tomedown`, changeable); sending them to your
cloud (any WebDAV server, or Dropbox/FTP) is an option, and so is reading
them in Obsidian. No app in the middle.

- **One file per book**, not one file for everything: unlike *Export
  highlights and notes*, every volume stays separate;
- **An index that ties the library together**: `00 - Index.md`, a clickable
  table of every book;
- **Your notes survive**: write in the file from Obsidian and the next export
  folds the new highlights in instead of overwriting them;
- **The cloud is optional**: the local export needs no network at all.

It has been in daily use since 1.0, and most of what changed in these releases
comes from reading my own library, and from people who took the time to
report what did not work.

The examples in this repo use **Koofr**: its free plan gives you 10 GB, more
than enough for a whole library of `.md` files.

![The Tomedown menu with a book open](assets/menu/reader/tomedown_reader_menu_1_1.png)

<p align="center">
  <strong>Jump to</strong><br>
  <a href="#install">Install</a> · <a href="#first-export">First export</a> · <a href="#the-menu">The menu</a> · <a href="#special-highlights">Special highlights</a> · <a href="#cloud-upload">Cloud upload</a> · <a href="#keep-my-notes">Keep my notes</a> · <a href="#reference">Reference</a>
</p>

## Install

**Requirements**

- KOReader with highlights in the modern format (old `.sdr` files, where
  highlights live in `highlight` + `bookmarks`, are supported too)
- the **Cloud storage** plugin that ships with KOReader, with any server it
  supports (WebDAV, Dropbox, FTP). The examples use Koofr's WebDAV,
  `https://app.koofr.net/dav/Koofr` (the plain `/dav/` root is not writable).
  **No cloud at all?** The local export works anyway
- optional, to read the notes in Obsidian: **Remotely Save** with a WebDAV
  server (free). Any other Markdown app works too

**Tested on** a Kindle Paperwhite 5 with KOReader 2026.07.2, in daily use,
and a Kindle 4 Non-Touch with KOReader 2026.07.1, Nextcloud WebDAV and
Obsidian, where [Tewel](https://codeberg.org/imanubdesigner/tomedown.koplugin/issues/1#issuecomment-25359526)
verified online merge, the offline round trip and the Obsidian edits on beta
2. The plugin is plain Lua: it runs wherever KOReader runs and touches no
hardware.

1. Plug the Kindle in via USB mass storage.

2. Download `tomedown.koplugin-v*.zip` from the
   [Releases](https://github.com/imanubdesigner/tomedown.koplugin/releases)
   page and unzip it *into* `/mnt/us/koreader/plugins/`: the zip already
   contains the `tomedown.koplugin/` directory.

3. Unplug the Kindle and restart KOReader (or: ☰ menu → *Plugin management* →
   enable *Tomedown*).

4. **Tomedown** is the first entry of KOReader's menu: on top of the
   *Navigation* tab (right before *Table of Contents*) while reading, and on
   top of the first tab in the file browser (right before *Display mode*).

   ![Tomedown first in the reader's Navigation tab](assets/menu/reader/tomedown_reader_menu.png)

<details>
<summary>Installing from a clone of this repo</summary>

Copy the folder, leaving behind what KOReader does not need (tests, docs, git
files and the guide artwork; the logo stays, the About popup shows it):

```
rsync -a --exclude tests --exclude .git --exclude .github \
      --exclude .gitattributes --exclude .gitignore \
      --exclude README.md \
      --exclude TUTORIAL.md \
      --exclude OBSIDIAN.md --exclude SYNC-DIRECTION.md \
      --exclude docs \
      --exclude assets/menu --exclude assets/obsidian \
      --exclude assets/obsidian-guide --exclude assets/tutorials \
      --exclude 'assets/banner-*.png' \
      tomedown.koplugin /mnt/us/koreader/plugins/
```

The result should look like:

```
/mnt/us/koreader/plugins/tomedown.koplugin/main.lua
/mnt/us/koreader/plugins/tomedown.koplugin/tomedown_i18n.lua
/mnt/us/koreader/plugins/tomedown.koplugin/tomedown_render.lua
/mnt/us/koreader/plugins/tomedown.koplugin/tomedown_merge.lua
/mnt/us/koreader/plugins/tomedown.koplugin/tomedown_cover.lua
/mnt/us/koreader/plugins/tomedown.koplugin/tomedown_update.lua
/mnt/us/koreader/plugins/tomedown.koplugin/_meta.lua
/mnt/us/koreader/plugins/tomedown.koplugin/languages/it.po
/mnt/us/koreader/plugins/tomedown.koplugin/assets/logo.png
/mnt/us/koreader/plugins/tomedown.koplugin/LICENSE
```

</details>

## First export

☰ menu → **Tomedown**:

1. On a fresh install, the first time you open the menu Tomedown offers to
   export the highlights of your whole reading history in one tap (*Export* /
   *Not now*; the offer is made only once, and the menu entry stays available
   anyway).
2. Otherwise pick **Export this book**, **Export new and changed books** or
   **Choose books…**. *Export new and changed books* also picks up the books
   you never exported.
3. The files land in the local folder first; with *Upload to cloud* on, the
   upload follows by itself.

```
/mnt/us/koreader/clipboard/tomedown/
├── 00 - Index.md
├── Michael McDowell - Blackwater_ The Complete Saga.md
└── ...
```

With *Export when I close a book* on, closing a book exports it on the spot,
and suspending the device does the same right before sleep, silently and
without touching the network.

<details>
<summary>Quickstart in six sheets</summary>

From the first highlight to a note you keep, in six sheets: the cover and one
sheet per step. Start with **01**.

![From highlight to note: the quickstart cover](assets/tutorials/00-cover.svg)

![01, mark what matters: select a passage, say what it is, find it written down](assets/tutorials/01-mark-what-matters.svg)

![02, your file, your folder: the export lands in the folder you chose, plain Markdown](assets/tutorials/02-your-file-your-folder.svg)

![03, optional: the cloud: point Tomedown at a server once, every export rides along](assets/tutorials/03-optional-the-cloud.svg)

![04, read it in Obsidian: Remotely Save bridges your cloud and your vault](assets/tutorials/04-read-it-in-obsidian.svg)

![05, edit, keep it: write in the file itself, flip one switch and your edits survive every export](assets/tutorials/05-edit-keep-it.svg)

</details>

A full walkthrough (cloud account and app password, Koofr as the example;
first export; optional Remotely Save in Obsidian) is in
[TUTORIAL.md](TUTORIAL.md).

## The menu

From the file browser the menu has seven rows:

![The Tomedown menu in the file browser](assets/menu/reader/tomedown_reader_new_menu.png)

With a book open it has nine: *Export this book* and *Current book* are added
on top.

| Row                              | What it does                                                                                                                                                  |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Export this book**             | the open book alone                                                                                                                                           |
| **Export new and changed books** | only the books whose highlights changed since the last export (per-book hash)                                                                                 |
| **Repair all files**             | writes every file again from KOReader's reading history: for a file deleted by mistake or a sync that went wrong                                              |
| **Choose books…**                | a list with checkboxes: tick the volumes and export just those                                                                                                |
| **Current book**                 | the rows that name the open book: *Keep my notes in this book*, *Notes heading: %1* and *Backup copies…*, explained in [Keep my notes](docs/keep-my-notes.md) |
| **Upload all files again**       | re-uploads every file already in the local folder, after comparing each one with its cloud copy                                                               |
| **Last export**                  | a wide popup, one line per entry: network, server, pending uploads, the last export and upload with timestamp and outcome                                     |
| **Settings**                     | the five groups, described in [Settings](docs/settings.md)                                                                                                    |
| **About**                        | a popup with the logo, the installed version, the description and the GitHub link                                                                             |

![The Last export popup: every entry on its own line, the labels in bold](assets/menu/settings/new_status_popup_messages.png)

## Special highlights

Some highlights matter more than the rest: the quote you want to open first,
the line you will come back to. **Special Highlight** is the flag for those.
When you select text it sits right under *Highlight*, and tapping an existing
highlight offers it at the bottom of the edit menu, with the same row in the
full menu behind the "…" button. The flagged quote becomes a
`> [!highlight]` callout in the file, or `> **quote**` if you pick *Bold* in
Settings, so it always stays visually apart from the plain quotes.

![The highlight menu on a fresh selection: Special Highlight sits right under Highlight](assets/menu/highlights/special_highlights_big_menu.png)

[File format](docs/file-format.md#special-highlights) shows the mark in the
file, how to take it off again, and how the callout reads in Obsidian, Notion
and GitHub.

## Cloud upload

*Settings → Cloud* points Tomedown at a server, once. After every export the
`.md` files and the index go there automatically; with *Include book covers*
the `covers/` folder travels with them, and each cover leaves the device once
its upload succeeded.

No connection? The export still happens locally and the files wait in a
pending list. As soon as KOReader comes back online (the connection event is
enough: no prompt, no dialog), **only those pending files** are uploaded:
books already in the cloud and unchanged are never re-sent, and a book whose
highlights changed since its last upload is uploaded again, overwriting the
old copy. Failed uploads stay pending and are retried on the next connection.

While uploading, an *Uploading N files to the cloud…* message stays on screen
(including the wait times), and each file is tried **up to 3 times**: two
seconds before the second attempt, four before the third. Only **transient**
failures are retried: network errors (no HTTP code, e.g. `connection reset`,
timeout), `5xx`, `408` and `429`. `4xx` errors (missing remote folder, wrong
credentials…) are not retried: the file fails immediately, because retrying
would only cost waiting.

If a file still fails, a window shows `Cloud: X uploaded, Y errors`, the file
stays in the local folder, and **Upload all files again** picks it up after
the fix. The attempts are also logged:

```
tomedown: upload failed (attempt 1 of 3), retrying in 2 s: <path> 500
```

Uploads go through KOReader's *Cloud storage* plugin: if it is not active the
local export still works and only the upload is skipped.

## Keep my notes

With *Keep my notes: all books* on (off by default), an export folds the new
highlights into the file already in your vault instead of overwriting it.
Above the generated block you get a heading and two blank lines of room:
everything you write there, and your own frontmatter properties, survives
every export. *Keep my notes in this book*, in the open book's menu, does the
same for one book alone, and *Keep my notes: index* for `00 - Index.md`.

Two copies sit beside the file when they are needed: `.bak` holds your notes
when Keep my notes goes off, and `.bak.1` is the safety copy for text that
cannot come back by itself. On, off, on: your notes come back each time.
*Backup copies…* lists them and lets you read or delete them.

With Keep my notes off the files are rewritten at every export: treat them as
read-only, or your edits disappear next time.

[Keep my notes](docs/keep-my-notes.md) covers the zones, the switches, the
merge and the two copies, step by step.

## Reference

| Page                                                                     | What is in it                                                          |
| ------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| [Settings](docs/settings.md)                                             | every group and row: Files, Cloud, My notes, Highlights, Updates, Beta |
| [Keep my notes](docs/keep-my-notes.md)                                   | zones, switches, `.bak` and `.bak.1`, two devices, edits from Obsidian |
| [File format](docs/file-format.md)                                       | frontmatter, the whole file, covers, index, link IDs                   |
| [Developing](docs/developing.md)                                         | tests, project structure, debug, languages                             |
| [Tutorial](TUTORIAL.md)                                                  | cloud account, Koofr, Remotely Save, first export, troubleshooting     |
| [Obsidian guide](OBSIDIAN.md)                                            | the files as they sit in the vault, and the Remotely Save setup        |
| [Sync direction](SYNC-DIRECTION.md)                                      | which Remotely Save direction to pick, and where your edits live       |
| [Releases](https://github.com/imanubdesigner/tomedown.koplugin/releases) | zips and release notes                                                 |

## Support

If it saves you time, you can buy me a coffee: the next features are brewed
with it.

<p align="center">
  <a href="https://ko-fi.com/imanubdesigner">
    <img src="https://img.shields.io/badge/Ko--fi-Buy%20me%20a%20coffee-FF5E5B?style=for-the-badge&logo=ko-fi&logoColor=white" alt="Buy me a coffee on Ko-fi">
  </a>
</p>

Something wrong or missing? [Open an issue](https://github.com/imanubdesigner/tomedown.koplugin/issues).

## License

Copyright (C) 2026 Manuel B.

GNU Affero General Public License v3.0, see [LICENSE](LICENSE).

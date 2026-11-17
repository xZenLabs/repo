<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.webp">
    <source media="(prefers-color-scheme: light)" srcset="assets/banner-light.webp">
    <img src="assets/banner-light.webp" alt="Tomedown: one Markdown file per book, straight into your notes" width="440">
  </picture>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/KOReader-plugin-faf6ee?style=for-the-badge&logo=koreader&logoColor=faf6ee&labelColor=2c2823" alt="KOReader">
  <img src="https://img.shields.io/badge/Obsidian-ready-7f6df2?style=for-the-badge&logo=obsidian&logoColor=faf6ee&labelColor=2c2823" alt="Obsidian">
  <img src="https://img.shields.io/badge/Markdown-100%25%20local-f0b00a?style=for-the-badge&logo=markdown&logoColor=faf6ee&labelColor=2c2823" alt="Markdown">
  <img src="https://img.shields.io/badge/Lua-5.1%2B-faf6ee?style=for-the-badge&logo=lua&logoColor=faf6ee&labelColor=2c2823" alt="Lua">
</p>

<p align="center">
  <a href="https://github.com/imanubdesigner/tomedown.koplugin/releases/latest"><img src="https://img.shields.io/github/v/release/imanubdesigner/tomedown.koplugin?style=for-the-badge&color=f0b00a&labelColor=2c2823&logo=github&logoColor=faf6ee" alt="Latest release"></a>
  <a href="https://imanubdesigner.github.io/tomedown.koplugin/docs/"><img src="https://img.shields.io/badge/Docs-Wiki-f0b00a?style=for-the-badge&logo=readthedocs&logoColor=faf6ee&labelColor=2c2823" alt="Docs Wiki"></a>
  <a href="https://github.com/imanubdesigner/tomedown.koplugin/actions/workflows/test.yml"><img src="https://img.shields.io/github/actions/workflow/status/imanubdesigner/tomedown.koplugin/test.yml?style=for-the-badge&color=238636&labelColor=2c2823&logo=githubactions&logoColor=faf6ee&label=tests" alt="Test status"></a>
  <a href="LICENSE"><img src="https://img.shields.io/github/license/imanubdesigner/tomedown.koplugin?style=for-the-badge&color=faf6ee&labelColor=2c2823" alt="License"></a>
  <a href="https://ko-fi.com/imanubdesigner"><img src="https://img.shields.io/badge/Ko--fi-support-f0b00a?style=for-the-badge&logo=ko-fi&logoColor=faf6ee&labelColor=2c2823" alt="Support on Ko-fi"></a>
</p>

<p align="center">
  <a href="https://imanubdesigner.github.io/tomedown.koplugin/">Website</a> ·
  <a href="https://imanubdesigner.github.io/tomedown.koplugin/docs/">Docs Wiki</a> ·
  <a href="https://imanubdesigner.github.io/tomedown.koplugin/changelog/">Changelog &amp; Updates</a> ·
  <a href="https://github.com/imanubdesigner/tomedown.koplugin/discussions">GitHub Discussions</a>
</p>

> [!IMPORTANT]
> **Looking for the full guides or release updates?**  
> All visual walkthroughs, full feature documentation, and release notes are hosted on the **[Tomedown Website & Docs Wiki](https://imanubdesigner.github.io/tomedown.koplugin/docs/)**.  
> You can check the latest updates and version history on the **[Changelog page](https://imanubdesigner.github.io/tomedown.koplugin/changelog/)**.

<p align="center">
  <strong>Jump to</strong><br>
  <a href="#overview">Overview</a> ·
  <a href="#install">Install</a> ·
  <a href="#first-export">First export</a> ·
  <a href="#essentials">Essentials</a> ·
  <a href="#documentation">Documentation</a> ·
  <a href="#support">Support</a>
</p>

---

## Overview

I made Tomedown because I wanted every book I read in KOReader to have its own clean `.md` file holding all of my highlights and notes.

Files are written locally on your e-reader first (`clipboard/tomedown/` by default). Cloud sync (WebDAV, Dropbox, FTP) and Obsidian are completely optional.

- **One file per book:** Export as `.md`, `.txt`, or both, with modular book headers (optional `H1` title, Reading Dashboard, collapsible EPUB synopsis, body tags, and 4 Overview Recap styles).
- **Handwritten notes & stylus drawings:** Exports pen strokes from stylus-enabled KOReader devices as clean vector `.svg` files into `drawings/` and embeds them inside your book notes.
- **Navigable Library Index (`00 - Index.md`):** Includes a Library Dashboard, `### Completed books`, clickable Tag Cloud, optional book covers, progress bars, and compact tag display modes.
- **Chronological Reading Digest (`00 - Reading Digest.md`):** Gathers highlights across all your books grouped by day.
- **Your notes survive (`Keep my notes`):** Write comments or custom YAML frontmatter in Obsidian and future exports merge new highlights without erasing your edits.
- **Portable settings & safe backups:** Export and restore your full plugin configuration (`tomedown_settings_backup.lua`) in one tap for easy device resets or migrations.

---

## Install

**Requirements:** KOReader (modern highlights and legacy `.sdr` files are both supported). No network or cloud account is needed for local exports.

1. **Via AppStore (easiest):** Install wirelessly through **Storefront** or **KOReader AppStore**.
2. **Manual install:** Download `tomedown.koplugin-v*.zip` from [Releases](https://github.com/imanubdesigner/tomedown.koplugin/releases) (or the [Download page](https://imanubdesigner.github.io/tomedown.koplugin/download/)) and unzip it into your KOReader `plugins/` folder (e.g., `/mnt/us/koreader/plugins/` on Kindle).
3. Restart KOReader (or go to `☰` → *Plugin management* and enable *Tomedown*).
4. You will find **Tomedown** at the top of KOReader's menu (and optionally in the top bar via *Settings → Style → Show Tomedown icon in the top bar*).

<details>
<summary>Installing from a git clone</summary>

Copy the plugin files to your e-reader's `plugins/` folder, excluding development and documentation directories:

```bash
rsync -a --exclude tests --exclude site --exclude docs \
      --exclude .git --exclude .github \
      --exclude .gitattributes --exclude .gitignore \
      --exclude '*.md' \
      --exclude assets/menu --exclude assets/obsidian \
      --exclude assets/obsidian-guide --exclude assets/tutorials \
      --exclude 'assets/banner-*' \
      . /mnt/us/koreader/plugins/tomedown.koplugin/
```

</details>

---

## First export

Open `☰` → **Tomedown**:

1. On a fresh install, Tomedown offers a one-tap export of your existing reading history (*Export* / *Not now*).
2. At any time, pick **Export this book**, **Export new and changed books**, or **Choose books…**.
3. Your files appear in the local folder right away:

```text
koreader/clipboard/tomedown/
├── 00 - Index.md
├── 00 - Reading Digest.md
├── drawings/
└── Author - Book Title.md
```

Enable *Export when I close a book* in *Settings → Files* to automatically export silently whenever you close a book or put your e-reader to sleep.

---

## Essentials

A few key things worth knowing right from the start:

- **Protecting your own notes:** By default, exports rewrite the generated files. If you plan to write personal notes or edit frontmatter in Obsidian, turn on **Keep my notes** (*Settings → My notes* or per-book under *Current book*). Tomedown also keeps rotating `.bak` / `.bak.1`–`.bak.3` safety copies when needed.
- **Backing up your settings:** Before resetting your device or reinstalling KOReader, use **Settings → Files → Export settings to file**. It saves all global and per-book preferences to `tomedown_settings_backup.lua` inside your local folder so you can restore everything in one tap later.
- **Cloud sync & Obsidian (optional):** If you want automatic WebDAV sync (for example with Koofr) and two-way vault sync with Obsidian's *Remotely Save* plugin, follow the step-by-step **[Cloud & Obsidian Tutorial](https://imanubdesigner.github.io/tomedown.koplugin/docs/tutorial/)**.

---

## Documentation

All detailed guides live on the **[Tomedown Docs Wiki](https://imanubdesigner.github.io/tomedown.koplugin/docs/)**:

| Topic | What you will find |
| --- | --- |
| **[Getting Started](https://imanubdesigner.github.io/tomedown.koplugin/docs/quickstart/)** | Installation, first local export, and quickstart overview |
| **[Menu & Settings](https://imanubdesigner.github.io/tomedown.koplugin/docs/settings/)** | Every option in Files, Index, Style, Book info, Cloud, My notes, and Updates |
| **[Keep My Notes](https://imanubdesigner.github.io/tomedown.koplugin/docs/keep-my-notes/)** | How note merging works, `.bak` safety copies, and editing in Obsidian |
| **[Formats & Output](https://imanubdesigner.github.io/tomedown.koplugin/docs/file-format/)** | Markdown/TXT layout, frontmatter, covers, `00 - Index.md`, and link IDs |
| **[Highlight Styles & Frontmatter](https://imanubdesigner.github.io/tomedown.koplugin/docs/universal-highlights/)** | 6 highlight styles, inline/footnote comments, custom YAML, and per-book rules |
| **[Templates, Folders & Index](https://imanubdesigner.github.io/tomedown.koplugin/docs/templates-and-folders/)** | Folder grouping, filename patterns, tag pills, and top bar icon |
| **[Reading Digest](https://imanubdesigner.github.io/tomedown.koplugin/docs/reading-digest/)** | Chronological daily journal across your library |
| **[Obsidian Guide](https://imanubdesigner.github.io/tomedown.koplugin/docs/obsidian/)** & **[Sync Direction](https://imanubdesigner.github.io/tomedown.koplugin/docs/sync-direction/)** | Vault structure and Remotely Save configuration |
| **[FAQ](https://imanubdesigner.github.io/tomedown.koplugin/docs/faq/)** | Common questions about formats, tags, stylus notes, and sync |
| **[Changelog & Updates](https://imanubdesigner.github.io/tomedown.koplugin/changelog/)** | Release history and what is new in each version |

---

## Support

If Tomedown saves you time, you can buy me a coffee. Found a bug or have an idea? Feel free to [open an issue](https://github.com/imanubdesigner/tomedown.koplugin/issues) or start a [discussion](https://github.com/imanubdesigner/tomedown.koplugin/discussions).

<p align="center">
  <a href="https://ko-fi.com/imanubdesigner">
    <img src="https://img.shields.io/badge/Ko--fi-Buy%20me%20a%20coffee-f0b00a?style=for-the-badge&logo=ko-fi&logoColor=faf6ee&labelColor=2c2823" alt="Buy me a coffee on Ko-fi">
  </a>
</p>

## License

Copyright (C) 2026 Manuel B.  
Licensed under the **GNU Affero General Public License v3.0**. See [LICENSE](LICENSE) for details.

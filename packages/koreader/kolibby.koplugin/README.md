# KOLibby

KOLibby is an unofficial KOReader companion to the official **Libby web, iOS and Android apps**. Browse library catalogs, manage cards and discover titles in your main Libby app; use KOLibby to synchronize **multiple library cards**, view loans and holds, download native ebooks as EPUBs, and export supported audiobooks as chaptered MP3s.

Android is the first supported test target. The implementation uses portable Lua and KOReader's bundled networking and archive libraries. No Python, browser, FFmpeg or root access is needed, and the official Libby app does not need to be installed on the reading device. Kobo and Kindle support still need real-device validation.

## Install

Use KOReader **2026.07.1 or newer**. Extract the release ZIP into KOReader's plugins directory so that the resulting path is:

```text
plugins/KOLibby.koplugin/main.lua
```

On a typical Android installation the plugins directory is `/storage/emulated/0/koreader/plugins/`. Restart KOReader, then open **Tools → KOLibby ▸**, the first entry on page 1 of the Tools menu in both the file browser and reader. KOReader must have access to the selected download folder.

## How Libby device copying works

Copying links devices to the **same Libby setup**, rather than making a one-time snapshot of your cards. The new device displays a short-lived code that refreshes automatically. Enter that code on an existing Libby device under **Menu → Copy To Another Device**. The code connects the new device to the existing setup; it is not a permanent account password. [Official setup instructions](https://help.libbyapp.com/en-us/6070.htm).

After linking, add, verify, update or remove cards in any linked official Libby app, on mobile or the web. The linked clients pick up shared changes when they synchronize. You do not need to pair KOLibby again for every card change. Libby explicitly notes that removing a card also removes it from other devices linked through device copying. [Card removal and linked devices](https://help.libbyapp.com/en-us/6030.htm). Independently adding the same cards on another device does not link the complete setup; use the copy flow to keep the setup together.

This makes KOLibby a companion to your main app: browse catalogs, add cards, borrow and place holds there, then let KOLibby refresh your cards, loans and holds automatically while KOReader is running and online. **Sync now** refreshes immediately. KOLibby does not synchronize Libby tags, KOReader annotations/reading position or local EPUB/MP3 downloads.

## Connect and read

1. In KOLibby, select **Connect to Libby**.
2. On an existing Libby device, open **Menu → Copy To Another Device** and enter the code displayed by KOLibby. The code expires and refreshes automatically.
3. Open **Loans** or **Holds** for cover art, authors, media/series details, due dates and hold status. **Library cards** provides a view filtered to each card.
4. Select an eligible ebook loan and choose **Download EPUB**. The finished book opens in KOReader. Fixed-layout downloads include a note about KOReader’s rendering limits before opening. For an eligible audiobook, choose **Download MP3**; the result is one MP3 with ID3v2.3 chapters, author/narrator metadata and cached cover art. Import it into your audio player from the displayed location. KOReader does not play audio itself.

EPUBs include the publisher's description when Libby supplies one, with readable paragraph breaks. The synopsis is also available in Bookshelf after download. For an EPUB downloaded with an older version, select **Download again / resume** to add it; existing files are not rewritten automatically.

Open **KOLibby → Loans**, then select **Download all** above the book list to download eligible EPUB and MP3 loans across every card. **Library cards → [card] → Loans on this card → Download all on this card** limits the queue to one card. KOLibby refreshes the shelf first and skips a completed file for the same checkout, even if the download folder setting has changed. Missing files and replacement checkouts are downloaded. Unsupported, expired and unverified loans are omitted.

Download all shows the current cover, loan number and per-loan progress. Each finished download is recorded immediately; **Cancel all** stops the queue while keeping finished files and resumable resources. Run it again to continue. Failures are reported at the end while other loans continue; downloaded books are not opened automatically.

Manage cards in any official Libby app linked to the same setup. KOLibby picks up changes at its next synchronization; **Sync now** refreshes immediately. Partner-library cards are marked **Partner card** and, when Libby provides an unambiguous link, show **Partner via [home library]** with the home card’s name. This attribution appears in Loans, Holds, item details and Library cards. Partner checkouts continue to use their own library/card for downloads and borrowing. Loans with the same title on different cards remain distinct. Card failures preserve that card's cached shelf while other cards refresh normally.

The default sync interval is 30 minutes while KOReader is active and connected, with overdue sync after startup, resume and reconnection. Change the interval and download folder in **Settings**. Work does not continue after KOReader closes or while the device sleeps.

Available holds offer **Borrow**. KOLibby refreshes the hold, loads the library’s loan periods, and asks you to choose a period before borrowing. It then refreshes the shelf. Expired, suspended and stale offers cannot be borrowed. Eligible MP3 audiobooks can be downloaded after borrowing, or played in Libby. A request with an uncertain outcome is reconciled by synchronization, without automatically repeating the borrow.

Cover art is cached during synchronization and remains available offline; missing or invalid covers use a placeholder.

Downloads show the book cover, a progress bar, file counts and saved size. They support cancellation and retry. Previously completed portions are reused when still valid for the current checkout. An existing complete EPUB or MP3 is preserved until a replacement finishes. Audiobook progress reports the current part and byte totals, followed by checking and joining stages.

## Bookshelf integration

KOLibby can supply a shelf source to the optional [Bookshelf plugin](https://github.com/AndyHazz/bookshelf.koplugin). Connect and synchronize KOLibby first, then add or edit a Bookshelf chip and choose **Source / grouping → KOLibby**. Select **Loans** or **Holds**, then **All library cards** or one card. Add multiple chips to keep separate loan, hold or library views.

The chips show cached covers and metadata, including loans that have not been downloaded. Open an existing EPUB through the chip, or select a remote loan for KOLibby's download controls. Hold details offer the existing **Borrow** confirmation when eligible. Audiobooks retain KOLibby's download and MP3-location controls; Bookshelf does not become an audio player. Pull down to synchronize; completed downloads, borrowing and synchronization refresh the source. Shelf browsing uses the local cache and works offline.

Optional Bookshelf template tokens `%kolibby_status`, `%kolibby_library` and `%kolibby_download` expose the due/hold status, library/card label and download state. Add them to Bookshelf's top-panel, cover-caption or list templates as desired.

This uses Bookshelf's documented source interface (version 1), with Bookshelf 6.3.3 used for integration checks. KOLibby remains available under Tools when Bookshelf is absent or its source interface is too old. Existing Bookshelf settings are not changed automatically; readers choose which chips to add.

## Update KOLibby

Open **KOLibby → Settings → Check for updates**. KOLibby checks the [latest stable GitHub release](https://github.com/kolibby/KOLibby.koplugin/releases/latest), displays its release notes, and offers **Install update**. Installation downloads the runtime ZIP, verifies GitHub's SHA-256 digest and its file manifest, then asks you to restart KOReader. **Later** on the release-notes screen leaves the update uninstalled. On Android, close and reopen KOReader after installation; supported platforms offer KOReader’s native restart prompt. Your Libby connection, settings and downloaded books are kept.

Update checks are manual and use a separate GitHub connection with no Libby credentials. Drafts, prereleases, older versions and GitHub's generated source archives are not installed. If no full release has been published, KOLibby reports that normally. A writable plugin folder is required; Git checkouts are updated through Git instead.

## Supported content and limits

- Eligible ebooks can be downloaded as EPUBs, and compatible audiobooks as a single MP3. Adobe Digital Editions / ACSM fulfillment is not supported.
- Audiobook parts are joined without re-encoding and include ID3v2.3 chapter tags. FFmpeg is not needed on the device. Chapter navigation depends on the audio player, and gapless playback is not guaranteed in every player.
- **KOReader does not reliably display all fixed-layout EPUBs.** KOLibby preserves supported layout information and explains this limitation before opening affected books. A reader with fixed-layout EPUB support may be needed for the intended appearance.
- Some large, complex or interactive publications may be unsupported. Allow space for temporary downloads and the completed file.
- PDF downloading, renewals, returns, tags, annotations and Libby reading-position synchronization are not implemented.
- Loan expiry is checked when opening a download through KOLibby.

Device credentials are stored locally in KOReader's settings directory, separately from shelf metadata, with restrictive permissions where the filesystem supports them. Shared Android storage does not provide a hardware-backed credential vault. **Disconnect this plugin** removes the saved connection and shelf; downloaded books remain in the download folder.

Like KOReader's own network requests, KOLibby does not verify the HTTPS certificates of Libby's servers, so a wrong device clock cannot block it. On a network that intercepts HTTPS, the saved Libby connection could be exposed; use networks you trust. Update downloads from GitHub are always verified.

Libby's service may change, which can affect compatibility. Support can vary by publication, library and KOReader device.

## Development

The repository itself is the plugin directory. Core tests need a Lua 5.1-compatible interpreter:

```sh
lua tests/run.lua
python3 tools/package.py
```

The package command reads `VERSION`, writes `dist/KOLibby-<version>.zip` and a SHA-256 sidecar, and includes the file manifest required by self-update. It excludes Git data, tests, development tools and private state. See [release packaging](docs/releases.md). `tests/support/dkjson.lua` retains its upstream MIT notice; production uses KOReader's bundled `dkjson` module. HTML entity mappings are generated from the standard named-character-reference data.

See [development](docs/development.md), [validation](docs/validation.md) and [release packaging](docs/releases.md) for contributor instructions and coverage limits.

## License

Copyright (C) 2026 KOLibby contributors. Licensed under **GNU AGPL version 3 only** (`AGPL-3.0-only`); see [LICENSE](LICENSE) and [NOTICE](NOTICE). Bundled third-party notices retain their original terms. KOLibby is an independent project and is not affiliated with OverDrive or Libby.

# goodreadskosync

Keep your KOReader reading in sync with Goodreads.

An unofficial, community KOReader plugin. Install it from **KOReader Storefront**
or manually from [Releases](https://github.com/gkgangavarapu/goodreadskosync/releases).


## Issue
- **Sign in on-device** - log in is a Hit and miss, it takes a few attempt , Try in a spaced manner- Once Logged in, It stays Logged in

## Features

- **Sign in on-device** — log in to Goodreads from KOReader itself, with an
  on-device prompt if Amazon asks for extra verification, and automatic retries
  when the connection is flaky.
- **Over-the-air (OTA) updates:** checks GitHub Releases about once a week and can
  download, verify (SHA-256), install, and restart for you on request — no cable
  or manual copying needed.
- Automatically updates your shelves: **Want to Read**, **Currently Reading**, and **Read**.
- Syncs reading progress — by time, by percent change, or by page change.
- Marks a book Read when you finish it (configurable), and offers a rating.
- Optional star ratings.
- Links a book to the best Goodreads match automatically, or lets you pick the right one.
- Manual controls: **Sync now**, **Set status**, **Rate this book**, **Find on Goodreads**.
- Reads your Goodreads shelf and never overwrites a book you have marked Read.
- Works offline and syncs when you reconnect; background sync never blocks reading.
- **Sync presets** (Battery saver / Balanced / Frequent) and Wi‑Fi handled the
  KOReader way, so it never fights your device settings.
- Small, non-intrusive notifications.
- No analytics and no telemetry.

## Syncing

Syncs run in the background and never interrupt reading. There are three presets
(**Settings → Sync preset**):

| Preset | Reading progress | Regular check |
|---|---|---|
| Battery saver | on open, close and reconnect | — |
| **Balanced** (default) | on open, close and reconnect | every 15 minutes |
| Frequent | as you turn pages | every 5 minutes |

- Progress is only sent when it changes by your chosen step (default: 5% or 5 pages).
- A sync fetches your latest shelf when a book is opened, when you sync manually,
  or about once an hour; otherwise it reuses the last result, so routine syncs
  stay quick.
- **Sync now** (This book → Sync now) works at any time and shows a small progress window.
- Offline changes are saved and sent automatically when you reconnect.
- Opening a book does not change its shelf until there is progress.
- When you finish a book it is marked **Read** (configurable from Settings).

## Download

Get the latest `goodreadskosync-<version>.zip` from the [Releases](https://github.com/gkgangavarapu/goodreadskosync/releases) page, or install it from **KOReader Storefront**.

## Installation

### From KOReader Storefront

Install **Storefront** on your device, then install **Goodreads Sync (unofficial)**
from its catalogue.

### Manually

1. Unzip the download and copy the `goodreadskosync.koplugin` folder into your KOReader `plugins` directory:
   - Kindle: `/mnt/us/koreader/plugins/` - Tested
   - Kobo: `.adds/koreader/plugins/`     - Untested
   - Android: `/sdcard/koreader/plugins/`- Untested
   - Linux / macOS: `~/.config/koreader/plugins/`- Untested
2. Restart KOReader.
3. Open **Tools → Goodreads Sync (unofficial) → Account → Log in**. (Buggy- Refer Issues)

## Disclaimer

- This is an **unofficial, community project**. It is **not affiliated with, endorsed by, or sponsored by Goodreads, Amazon, or KOReader**.
- Goodreads has no public API. This plugin communicates with Goodreads' web endpoints, which are undocumented and may change or stop working at any time, with or without notice.
- **No warranty.** The software is provided "as is", without warranty of any kind, express or implied. Use it at your own risk. The authors are not liable for any loss, damage, or consequences arising from its use.
- Use it responsibly and in accordance with the terms of service of Goodreads and Amazon. You are responsible for how you use this software.
- Your credentials and session stay on your device. Nothing is sent anywhere except to Goodreads.
- Goodreads and Amazon are trademarks of their respective owners.

## Support

If you find this plugin useful and want to support its continued development, you can [Buy Me a Coffee](https://buymeacoffee.com/gkgangavarapu).

## License

MIT — see [LICENSE](LICENSE).

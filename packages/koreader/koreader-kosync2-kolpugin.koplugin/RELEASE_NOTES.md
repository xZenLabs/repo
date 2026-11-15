# v1.0.0 · 2026-11-04

# KOSync2 v1.0.0

First tagged release of the KOSync2 KOReader plugin.

## Highlights

- Sync reading progress and the full reading statistics database across devices.
- Failed progress pushes are queued and replayed on the next connection, so a lost Wi-Fi link no longer drops the current position.
- Queue entries are scoped by account and server. A queued item is never replayed into another account.
- Dispatcher actions use the `kosync2_*` namespace, so they can coexist with the built-in Progress sync plugin.
- Optional document metadata: filename, title, and authors can be sent with progress updates. Off by default.
- Short menu labels: `↑ Push progress now` and `↓ Pull progress now`.
- Missing `device_id` now falls back to an empty string instead of failing client-side validation.

## Installation

1. Download `kosync2.koplugin.zip` below.
2. Unzip it into your KOReader `plugins/` directory. The result should be `plugins/kosync2.koplugin/`.
3. Restart KOReader.
4. Open Progress & Statistics sync, set your server URL, then register or log in.

## Coexistence with the built-in Progress sync

If you also use KOReader's built-in Progress sync, disable one of them in Plugin management. Running both can duplicate sync traffic, and the built-in plugin registers the same gesture action names first.

## Server compatibility

Statistics sync requires a server that implements `/syncs/statistics`. The companion server is [koreader-sync-serverless](https://github.com/Tokisaki-Galaxy/koreader-sync-serverless).

Optional metadata is stored by the latest serverless backend. Older servers ignore the field, so enabling it is safe but has no visible effect there.

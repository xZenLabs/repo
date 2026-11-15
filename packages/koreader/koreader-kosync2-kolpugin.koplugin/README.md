# koreader-kosync2.kolpugin

> **Advanced Progress & Reading Statistics Synchronization for KOReader**

<p align="center">
    <img src="https://img.shields.io/badge/Language-Lua-blue?style=for-the-badge&logo=lua" />
    <img src="https://img.shields.io/badge/Platform-KOReader-orange?style=for-the-badge" />
    <img src="https://img.shields.io/badge/Protocol-JSON_API-green?style=for-the-badge" />
    <img src="https://img.shields.io/badge/Backend-Serverless-black?style=for-the-badge&logo=cloudflare" />
</p>

**KOSync2** is a feature-rich enhancement of the original KOReader synchronization plugin. While the standard KOSync only tracks reading positions, **KOSync2** synchronizes your entire **Reading Statistics** database—including reading time, page turns, and daily streaks—while providing a beautiful web-based dashboard to visualize your reading habits.

---

## Features

*   **Full Statistics Sync**: Syncs reading duration, pages read, and calendar spans across all your devices (E-ink readers, Android, etc.).
*   **Web Dashboard**: View your reading progress and habits through a modern web interface.
*   **Server-Side Merging**: Uses intelligent logic to merge reading events from different devices, preventing data loss or overwrites common with file-based sync (like WebDAV).
*   **E-ink Optimized**: Built with efficiency in mind. It uses lightweight JSON deltas instead of full database uploads to save battery and bandwidth.
*   **Offline Retry Queue**: Failed progress pushes are kept on the device and replayed on the next connection instead of being lost when Wi-Fi is unavailable.
*   **Optional Metadata**: Can send the document filename, title, and authors with each progress update for servers that store them. Off by default.
*   **Non-Invasive Integration**: Utilizes `user-patching` to hook into the native "Reading Statistics" menu without modifying core KOReader files.

---

## Getting Started

### 1. Installation
1.  Download the latest release of `kosync2.koplugin`.
2.  Copy the folder into your KOReader `plugins/` directory:
    *   **Android**: `/sdcard/koreader/plugins/`
    *   **Kindle/Kobo/PocketBook**: `koreader/plugins/`
3.  Restart KOReader.

### Coexistence with the built-in Progress sync

KOReader ships a built-in **Progress sync** plugin. KOSync2 is a separate plugin and can coexist with it, but running both at the same time is not recommended:

- Both plugins react to the same network and document-close events, which can duplicate sync traffic.
- The built-in plugin registers the same gesture action names first, so bind gestures to the KOSync2 actions explicitly when both are enabled.
- Pending retries are stored in a separate queue file, so progress queued for one account is never replayed into another.

If you only use KOSync2, disable the built-in Progress sync in KOReader's Plugin management menu and restart KOReader.

### 2. Server Setup
KOSync2 requires a compatible backend to store and merge your data. We recommend our **Serverless** implementation for zero-maintenance hosting:

**Get the Server here**: [koreader-sync-serverless](https://github.com/tokisaki-galaxy/koreader-sync-serverless)

*Once deployed, simply enter your Server URL in the KOSync2 settings menu.*

---

## 📡 The Protocol

KOSync2 extends the KOSync protocol. Instead of just sending a `document_id` and a page number, it serializes incremental updates from your `statistics.sqlite` into JSON objects:

```json
{
  "action": "sync_statistics",
  "payload": {
    "book_id": "unique_hash",
    "total_time": 3600,
    "pages_read": 42,
    "events": [...]
  }
}
```

This allows the server to act as a "Single Source of Truth," merging records from multiple devices into a unified timeline.

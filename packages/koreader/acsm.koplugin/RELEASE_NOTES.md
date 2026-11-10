# v0.0.16 · 2026-11-10

## What's Changed
* fix: isolate zlib FFI bindings from other plugins by @kaikozlov in https://github.com/kaikozlov/acsm.koplugin/pull/28


**Full Changelog**: https://github.com/kaikozlov/acsm.koplugin/compare/v0.0.15...v0.0.16

---

## Installation

1. Download `acsm-koplugin-v0.0.16.zip` below
2. Extract `acsm.koplugin` to your KOReader plugins directory:
   - Kindle: `/mnt/us/koreader/plugins/`
   - Kobo: `/.adds/koreader/plugins/`
   - Android: `/storage/emulated/0/koreader/plugins/`
   - reMarkable: `/home/root/koreader/plugins/`
3. Restart KOReader

See README for usage instructions.

# v0.0.15 · 2026-11-04

**Full Changelog**: https://github.com/kaikozlov/acsm.koplugin/compare/v0.0.14...v0.0.15
- Fixed: a failed download no longer resets saved activation
---

## Installation

1. Download `acsm-koplugin-v0.0.15.zip` below
2. Extract `acsm.koplugin` to your KOReader plugins directory:
   - Kindle: `/mnt/us/koreader/plugins/`
   - Kobo: `/.adds/koreader/plugins/`
   - Android: `/storage/emulated/0/koreader/plugins/`
   - reMarkable: `/home/root/koreader/plugins/`
3. Restart KOReader

See README for usage instructions.

# v0.0.14 · 2026-11-03

**Full Changelog**: https://github.com/kaikozlov/acsm.koplugin/compare/v0.0.13...v0.0.14

- **New: Adobe activation submenu with portable backups** — **Tools → More tools → ACSM → Adobe activation** shows whether an activation is saved, and lets you export it to a backup file, load a backup (e.g. to move your activation to another device), or forget it. See [#25](https://github.com/kaikozlov/acsm.koplugin/pull/25).
- **New: optionally delete the `.acsm` file after fulfillment** — turn on **Tools → More tools → ACSM → Delete ACSM after fulfillment** (off by default). Requested in [#23](https://github.com/kaikozlov/acsm.koplugin/issues/23).

---

## Installation

1. Download `acsm-koplugin-v0.0.14.zip` below
2. Extract `acsm.koplugin` to your KOReader plugins directory:
   - Kindle: `/mnt/us/koreader/plugins/`
   - Kobo: `/.adds/koreader/plugins/`
   - Android: `/storage/emulated/0/koreader/plugins/`
   - reMarkable: `/home/root/koreader/plugins/`
3. Restart KOReader

See README for usage instructions.

# v0.0.13 · 2026-08-24

**Full Changelog**: https://github.com/kaikozlov/acsm.koplugin/compare/v0.0.12...v0.0.13

- **Fixed: PDFs that use compressed cross-reference streams now process and open** — some ACSM PDFs (e.g. processed by qpdf or saved with Acrobat's Fast Web View/linearization) failed with a parsing error. The PDF parser now handles all five PNG prediction filter types used by these files. Fixes [#21](https://github.com/kaikozlov/acsm.koplugin/issues/21).
- **Internal cleanup of the PDF and fulfillment code** — consolidated duplicate parsing
paths. Processing is now verified end-to-end against Adobe's full public sample library (26 titles, both EPUB and PDF).

---

## Installation

1. Download `acsm-koplugin-v0.0.13.zip` below
2. Extract `acsm.koplugin` to your KOReader plugins directory:
   - Kindle: `/mnt/us/koreader/plugins/`
   - Kobo: `/.adds/koreader/plugins/`
   - Android: `/storage/emulated/0/koreader/plugins/`
   - reMarkable: `/home/root/koreader/plugins/`
3. Restart KOReader

See README for usage instructions.

# v0.0.12 · 2026-07-31

**Full Changelog**: https://github.com/kaikozlov/acsm.koplugin/compare/v0.0.11...v0.0.12

- **Fixed: ACSM processing crash on some Android devices (e.g. BOOX)** — resolves an "undefined symbol: CRYPTO_free" error caused by missing crypto symbols in vendor builds (https://github.com/kaikozlov/acsm.koplugin/issues/20).

---

## Installation

1. Download `acsm-koplugin-v0.0.12.zip` below
2. Extract `acsm.koplugin` to your KOReader plugins directory:
   - Kindle: `/mnt/us/koreader/plugins/`
   - Kobo: `/.adds/koreader/plugins/`
   - Android: `/storage/emulated/0/koreader/plugins/`
   - reMarkable: `/home/root/koreader/plugins/`
3. Restart KOReader

See README for usage instructions.

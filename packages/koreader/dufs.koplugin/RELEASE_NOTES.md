# v1.0.1 · 2026-11-09

Patch release with two fixes.

## Fixed

- **Scannable QR code** — stable KOReader rendered the address QR at one pixel per module, which was too small to scan. It now fills the available screen width.
- **Android** — the plugin no longer loads there. The server needs to execute a bundled Linux binary and write to `/tmp`, both blocked by Android, so the menu used to appear but the server could never start.

**Full changelog:** https://github.com/Craftwork2720/dufs.koplugin/compare/v1.0.0...v1.0.1

# v1.0.0 · 2026-11-08

## dufs.koplugin 1.0.0

First release. A web file manager for KOReader: manage the files on your e-reader from any browser on the same network. 

### Features

- Browse, upload, download, rename, move, delete, search and sort, with multi-select and batch actions
- List and grid views, light and dark themes, favorite folders
- EPUB, CBZ and PDF cover thumbnails
- Text editor, PDF viewer, image, audio and video preview
- WebDAV on the same address and credentials
- QR code for quick phone access
- Optional login, idle auto-stop, keep running while sleeping
- Bundled binaries for aarch64, armv7 and x86_64

### Notes

- Without a username and password, anyone on the network can modify your files. Set credentials in **Settings**.
- CBR files are listed and downloadable, but have no cover previews.

Built on [dufs](https://github.com/sigoden/dufs), [PDF.js](https://mozilla.github.io/pdf.js/) and [Lucide](https://lucide.dev) icons. License texts ship with the plugin.

<p align="center">
  <img src="assets/icon.png" alt="dufs.koplugin" width="28" height="28">
  <a href="https://github.com/Craftwork2720/dufs.koplugin/releases/latest/download/dufs.koplugin.zip"><img src="https://img.shields.io/badge/Download-dufs.koplugin.zip-00a89c?style=for-the-badge&logo=github&logoColor=white&labelColor=1f2328" alt="Download dufs.koplugin.zip"></a>
  <a href="https://ko-fi.com/Y8Y01JS8SV"><img src="https://img.shields.io/badge/Support-Ko--fi-FF5E5B?style=for-the-badge&logo=kofi&logoColor=white&labelColor=1f2328" alt="Support on Ko-fi"></a>
</p>

# dufs.koplugin

A web file manager for KOReader. Start the server on your e-reader, open its address in any browser on the same network and manage your files like in any cloud drive. Nothing to install on your phone or computer.

It runs [Dufs](https://github.com/sigoden/dufs), a lightweight and fast file server written in Rust that serves a web interface and WebDAV.

<p align="center">
  <img src="docs/dufs-ui-uploads-dark.png" alt="Dufs dark mode with an upload queue and cover preview" width="800">
</p>

## Features

- Browse, upload, download, rename, move and delete files
- Multi-select, batch actions and folder download as ZIP
- Search, sorting, list/grid view, light/dark theme
- File-type icons for books, comics, images, audio, video, archives, code and more
- EPUB, CBZ and PDF cover thumbnails with full-resolution preview
- Text editor, PDF viewer, image preview, audio and video playback
- Favorite folders
- QR code for connecting from your phone
- WebDAV

## Installation

1. Download `dufs.koplugin.zip` and extract it.
2. Copy the `dufs.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

## Usage

1. Go to **Network → Dufs file server → Start server**.
2. Open the shown address in a browser, or scan the QR code. Both devices must be on the same network (or Tailscale).
3. Optional: in **Settings** change the port (default `5020`), root folder or home folder, and set a username and password.

> [!IMPORTANT]
> Without a username and password, anyone on your network can access and modify your files. Setting a password is strongly recommended.

- **Keep server running when sleeping**: the server stays up while the device sleeps.
- **Stop when idle**: the server stops after 5 min to 2 h without requests. Active transfers keep it alive. Off by default.
- To skip signing in every time, bookmark the address with the login, e.g. `http://user:password@192.168.1.5:5020/`. The password is then stored in the bookmark as plain text.

## WebDAV

WebDAV uses the same address, port and credentials as the web interface. On Windows: **Map network drive** → `http://<address>:5020`.

## Updates

**Network → Dufs file server → Check for updates**. The plugin also checks once a week and never installs anything without asking.

<p align="center">
  Enjoying dufs.koplugin? A coffee helps me keep it going ☕
  <br><br>
  <a href="https://ko-fi.com/Y8Y01JS8SV" target="_blank"><img height="36" src="https://storage.ko-fi.com/cdn/kofi6.png?v=6" alt="Buy Me a Coffee at ko-fi.com"></a>
</p>

## License

Plugin code and web UI: **AGPL-3.0-only** ([LICENSE](LICENSE)).
Bundled Dufs binaries: **MIT OR Apache-2.0**. PDF.js: **Apache-2.0**, with its standard-font and CMap notices. UI icons from Lucide: **ISC**. See [licenses](licenses).

#### My [User Patches](https://github.com/Craftwork2720/koreader-patches) for KOReader. ❤️
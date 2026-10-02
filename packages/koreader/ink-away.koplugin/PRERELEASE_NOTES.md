# v3.1.3 · 2026-09-27

Prerelease rolling up **everything since 3.1.0** (3.1.1 and 3.1.2 were prereleases), with a major focus on making landscape fast and correct.

## New
- **Landscape orientation.** Draw with the device held sideways; Ink Away remembers the choice and reopens the same way. A landscape session gets a wide canvas, and its PNG / JPEG / PDF export comes out landscape automatically.
- **Background remover for images.** First-pass remover that flood-fills from the edges, so a photo's subject stays solid while the surrounding background drops out.

## Landscape performance (the big rework)
On e-ink readers that render landscape by rotating the framebuffer in software, drawing and menus used to lag. Landscape is now rebuilt to be as responsive as portrait:
- Panel-order rendering — the canvas is scaled and copied through the screen's native pixel order (a memcpy) instead of a per-pixel rotated copy on every frame.
- The master bitmap is mirrored in panel order, so pan / zoom / redraw never re-rotate the whole screen.
- Shape commits re-render only the shape's rectangle, not the whole drawing area.
- The floating zoom control is cached as a sprite instead of being redrawn every frame; toolbar chrome isn't repainted mid-stroke or mid-drag.

## Settings & grid
- Grid type, size and opacity moved into their own grid sub-sheet, so the settings sheet fits with no scrolling (no more nudging a slider by accident).
- Fixed grid-on drawing slowness (the grid is clipped to the changed region while you draw).

## Reliability
- Reopening Ink Away can no longer stack a second canvas over an old one (which had made the app get slower until a restart); reopening recovers cleanly.
- Notebook shape clipping on rotation fixed; text stays put across rotation.
- Online image browser: fixed a tap-to-add crash and re-searching without the keyboard getting trapped.
- Memory backstops so long sessions don't degrade.

## Known issue
- Very heavy, prolonged switching between portrait and landscape *while drawing* can gradually reduce responsiveness until KOReader is restarted. Normal use is unaffected; a fix is still being investigated.

# v3.1.2 · 2026-09-26

Faster landscape, a tidier settings menu, and a pen-input test to help track down stylus problems.

* Landscape drawing and repaints are noticeably faster.
* The settings menu is tidied up so it fits without scrolling — all the grid options (type, size, opacity) now live together in one Grid panel.
* The grid no longer slows drawing: turning it on, even at a small size, keeps drawing as smooth as with it off.
* New pen-input test in the gear menu, for stylus users: it shows exactly what your pen and palm report to the device. If you're on a stylus device and seeing stray dots or lines under your palm, please run it and send me what it shows — it lets me look into palm rejection on devices I can't test myself.

Prerelease — please try it on your device and let me know how it holds up, especially the pen-input test on stylus devices.

# v3.1.1 · 2026-09-26

Landscape mode, plus a few fixes.

- Portrait or landscape — set it in the gear menu, or just open Ink Away with your device turned. It remembers which way you left it, and the page (and your PNG/JPEG/PDF exports) come out in that orientation.
- Background remover for added images (early version): pick an image in Pan mode and tap Remove background to cut a plain/solid background out to transparent.
- Fixed a crash when tapping (instead of long-pressing) an image in the online image browser.
- Fixed editing your search term in the online image browser — it now keeps what you typed so you can change it.

Prerelease — please try landscape and the background remover on your device and let me know how they hold up.

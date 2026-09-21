# v2.3.0

Palm rejection now clears the stray marks a resting hand could leave before the pen was recognised.

Notebook interface polish:
- The bottom bar now matches the top toolbar: consistent icons, sizing, and a shorter bar with the page number sized to the new-page icon.
- The page menu and the new-notebook paper chooser use the same rounded style as the other menus.
- A chevron at the bottom-left hides and shows the bottom bar.
- Fixed a crash when opening Settings after switching to a notebook.

Major performance tweaks:
- New drawing frees the previous drawing's buffers and collects right away, so starting fresh returns its memory on the spot.
- After a stroke commits, if the heap has grown unusually large over a
  very long session, reclaim garbage between strokes.
- Fixed the canvas slowing down as strokes accumulate
- The live drawing path no longer allocates on every point: the symmetry
  mirror rectangles come from a reused pool computed arithmetically (no
  per-point helper closures) and the segment handed to the rasterizer is
  a reused buffer.

# v2.2.3

Palm rejection should now work reliably on pen readers and is enabled by default where a pen is present.

- Rest your hand on the screen while you write, only the pen marks the page.
- On automatically for Kindle Scribe and reMarkable. On Kobo and other stylus readers, switch it on in Pen Settings.
- Fixed stray lines being drawn between a resting palm and the pen tip.
- The rear eraser and barrel button keep working; a palm can no longer be mistaken for the eraser.
- Major UI overhaul to all the tool menus in the toolbar
- You can now hide the toolbar for a more immersive drawing experience
- Zoom buttons has been moved from the toolbar to the right bottom corner of the screen. It auto hides itself if the ink gets close to it to allow drawing underneath the buttons.

This is a prerelease for testing on pen hardware. While testing, an on-screen note appears the first time the pen and the first time a palm are detected.

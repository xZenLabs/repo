# v4.0 · 2026-11-16

## What's new

- **Color mode:** dots can now be tinted. Pick a color from the palette (color screens only) under Tint; Neutral grey is still the default. 

- **Page turn animations:** new Wipe and Blinds transitions that move toward the side you turn to. Configurable steps, optional skip for comics/manga, and a gesture to toggle them (general -> toggle paper dots page animation)

- **Fast painting fixed:** it was silently failing because of a wrong buffer field, so it never actually ran. It now works, and it is enabled by default on supported screens.

# v3.2 · 2026-11-07

Fixed slowdown when rotating the screen for kindle devices. 

**Known issue**
- On kindle basic 2024, Fibers can still be slower than the other styles.

# v3.1 · 2026-11-02

Fixed slowness when changing orientation

# v3.0 · 2026-10-28

What's new:
1. New styles
2. Fast painting (experimental):
Paints dots by writing directly to the screen buffer instead of calling KOReader once per pixel, which can speed up drawing on some devices. It only activates when the screen uses a compatible RGB32 framebuffer, is not rotated/inverted, and passes a read/write self-test; otherwise it is ignored and the normal method is used automatically. It does not change the pattern’s appearance. Enable it only if the plugin feels slow; disable it if dots look wrong or show artifacts.
3. Minor performance optimizations

# v2.3 · 2026-10-08

-One new style (diagonal lines)

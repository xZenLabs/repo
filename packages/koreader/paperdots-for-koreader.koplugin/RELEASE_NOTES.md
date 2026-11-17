# v4.1 · 2026-11-17

## Performance improvements and optimizations

- **Improved screen rotation performance:** Added optimized column-based rendering paths for Linen, Cross-hatch, Diagonal and Laid styles.
- **Reduced rendering overhead:** Improved framebuffer context handling and reduced unnecessary allocations during screen refreshes.
- **Optimized page-turn animations:** Reworked frame composition to copy only newly revealed areas instead of repeatedly copying large portions of the page.
- **E-ink optimizations:** Added automatic animation step limits to reduce physical screen refreshes (Wipe: 5 steps, Blinds: 2 steps).
- **Improved default animation settings:** Reduced the default animation steps from 15 to 3 for a better balance between smoothness and battery efficiency.
- **Fixed page animation dispatcher action:** Corrected an incorrectly nested function declaration.
- **Preserved existing rendering behavior:** Kept the BB8, RGB32, fast painting, night mode and custom tint rendering paths intact.

## Notes
- Keep in mind that page animations will consume additional battery power, regardless of how well optimized they are. If battery life is a concern, you can reduce the number of steps even further or disable the animation entirely.

- I'm already working on version 5.0, it will include a new feature that I'm really excited about, and I hope you'll like it too. Stay tuned!

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

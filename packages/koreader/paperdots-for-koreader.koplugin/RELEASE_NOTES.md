# v5.1 · 2026-11-19

**Frame margins:** 
fixed the frame flashing (disappearing and redrawing) on every page turn on e-ink devices in day mode. Page turns now refresh with the same waveform the page animation uses, so the frame stays still. I didn't notice this happened as I only tested it with my own page animation turned on.


**Page animation:**
 removed the automatic step limits on e-ink (Wipe was capped at 5 steps and Blinds at 2). You can now choose any value up to 15 and decide what works best for your device, keep in mind that the higher the steps the higher the battery consumption (this is all in theory, you can do your own tests as I'm not really sure how much battery consumption each step will take).

# v5.0 · 2026-11-19

## What's new

**Margin styles:** Decorative frames drawn around the page margins while you read.

- 13 styles to choose from.
- Adjustable line thickness and distance from the edge.
- Custom frame color on color screens.
- Custom gesture to toggle it on/off (gestures/general/toggle paper dots margins)

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

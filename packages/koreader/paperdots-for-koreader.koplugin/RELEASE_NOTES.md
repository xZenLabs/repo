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

# v2.2 · 2026-09-24

**What's New**

 * **Paperdots Gesture:** Easily toggle the feature on and off using your favorite gesture. (Gesture manager>your favorite gesture>general>toggle paperdots)
 * **Expanded Menu Access:** The menu is now also accessible from the file browser (first icon outside a book)
 * **Dark Mode Control:** Added a new setting to disable the feature when Dark Mode is active.
 * **One new style** 
*  **Minor performance optimizations**

# v2.1 · 2026-09-20

**New options**
- Hide dots on menus: keeps dots on the book page only, without dots on menus and dialogs.
- Settings are now saved per style (density, size, shades, fiber length), so a value that looks good in one style doesn't affect the others.

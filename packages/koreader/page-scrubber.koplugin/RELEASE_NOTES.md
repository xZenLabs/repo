# v7.3.5

v7.3.5 — Release Notes

### Reading Pop-Ups Disabled by Default
 * Opt-in Behavior: Both Scrubber Dictionary and Scrubber Selection Menu are now disabled by default (default = false). Fresh installations and updates will preserve KOReader's stock dictionary and selection menus without unexpected interface changes.
 * Users who prefer the minimalist floating pop-ups can enable them at any time in Page Scrubber Settings -> Reading Pop-Ups.

### Reorganized Wallpaper Menu
 * Dedicated Submenu: Wallpaper selection has been moved to its own submenu labeled Choose wallpaper using the sparkles.svg icon, keeping the top-level wallpaper menu clean and concise.
 * Folder Guidance: The system path helper has been renamed to Add wallpaper and placed at the bottom of the wallpaper list.
 * Dynamic State: The Book title background setting is automatically disabled and dimmed when no wallpaper is selected (None), preventing inactive configuration states over the stock white background.
 
**New** Title Background Style: Translucent
 * Translucent Mode: Added a new Translucent option under Wallpaper -> Book title background.
 * E-ink Optimized (Zero-Allocation): Leveraging Bookshelf's native C blending algorithm (blendRectRGB32 with _roundedSpans), the translucent pill composites smoothly over the wallpaper without allocating intermediate Blitbuffers or introducing UI flicker.
 * The title background setting now includes four options:
   * With border: White pill with a solid black outline.
   * No border: Solid white pill without an exterior border.
   * Translucent: Semi-transparent white pill that allows the underlying wallpaper texture to show through.
   * Off: Free-floating title text backed by a dense halo.

**Stability** and Memory
 * Instant RAM flushing and clean widget exit when switching wallpapers (including reverting to None) or toggling title pill styling options.
 
 **Added translations.**
 
[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32577238/page_scrubber.koplugin.zip)

# v7.3.0

v7.3 — Patch Notes
Here is the latest update for Page Scrubber. This release brings key performance enhancements to page navigation, comprehensive UI refinements, and visual customization options.

### Performance & Navigation
 * Aggressive Page Preloading: Neighboring pages are now preloaded ahead of time in the background, making page turns via taps or swipes feel instant.
 * Rewritten Bookmark Logic: The add/remove bookmark logic was completely rewritten to work reliably alongside background preloading, preventing crashes or freeze-ups during live bookmark toggling.

### New Feature: Wallpapers
A customization option designed to match recent aesthetic setups like Bookshelf:
 * Multi-Folder Detection: Automatically loads custom wallpapers from the plugin’s own directory as well as shared system paths (including Bookshelf, SimpleUI, and /mnt/us/Wallpapers/).
 * Title Pill & Dense Halo: Book titles can now sit inside an optional protective "pill" badge. If turned off in settings, a dense 8-pass circular halo renders behind the text to ensure complete readability across textured or dark backgrounds.
 * Clean Divider Line: A crisp horizontal divider line renders directly beneath the top bar when a wallpaper is active.
 * Note on Performance: Full-screen image rendering on E-ink requires additional RAM and CPU cycles. If you notice any interface lag on lower-spec hardware, you can instantly return to the stock white background by selecting None.

**Split View Visual Refinements**:
 * Standardized Geometry: Border thickness, corner radii, and list padding are now aligned across portrait and landscape views, ensuring consistent lines between the Polaroid preview and right-hand list cards.
 * Refined Tabs: Upper category tabs and filter icons received subtle visual adjustments for a cleaner, balanced layout.

**RTL / Manga Navigation Fixes**
 * Directional Arrow Fixes: Resolved issues in landscape RTL mode where Bookmark Browser navigation chevrons and return-to-origin labels pointed in the wrong direction.
 
**Stability & Memory Management**
 * Clean Exits on Heavy Toggles: Switching heavy visual states—such as choosing a new wallpaper, disabling wallpapers via "None", toggling the title pill, or switching day/night mode and frontlight—now safely closes the widget to flush C-buffers from RAM and prevent ghosting or input lag.
 * Minor state synchronization and alignment bug fixes.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32567026/page_scrubber.koplugin.zip)

# v7.2.0


### Performance & Screen Refresh
 * Elimination of Global Full-Screen Flash: Eradicated invasive full screen refresh calls in onPanRelease, onRelease, and onSwipe, replacing them with partial refresh mode to consolidate crisp grayscale rendering without jarring black flashes.
 * Fluid Bottom Bar Scrubbing: Implemented fast refresh mode (rapid waveform without screen inversion) strictly bounded to self._bar_dimen, allowing the knob and page/percentage numeric readouts to track continuous touch drag smoothly.
 * Simple UI & Grid Responsiveness: Optimized render/refresh behavior in Simple Grid views to eliminate lagging, white-blanking.
 
### Navigation & Gestures
 * Hold Gesture Tuning: Reduced initial startup delay to 200 ms and tuned continuous repeat cadence to 650 ms, providing a fluid page-flipping rhythm that respects E-ink particle settling time (specially in simple grid).
 * Removal of Arbitrary Page Limit: Removed hardcoded stop after ~30 continuous steps, allowing uninterrupted navigation as long as hold is maintained.
 * Post-Hold Cleanup: Added a clean partial refresh cycle in onHoldRelease to clear lingering ghost text/halos after a long continuous flip burst.

Visual & UI Improvements
 * Transition to SVG Vector Icons: Replaced font glyphs for bookmark navigation buttons with chevron-left.svg and chevron-right.svg, ensuring razor-sharp edges and eliminating vertical font-offset misalignment.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32448793/page_scrubber.koplugin.zip)

# v7.1.0

* **Manual RTL (Right-to-Left) Mode Toggle:**
  * Added a dedicated **RTL** toggle to manually switch reading direction for manga, comics, or right-to-left documents that do not report native metadata flags.
  * Preserves full automatic detection: if a document already exposes RTL metadata, the toggle automatically reflects its active state (`☑`).
  * Per-document isolation: settings are stored locally in the book's properties (`doc_settings`), keeping the rest of your library untouched.
  * Instant real-time UI refresh: updates the slider, progression, and thumbnail grid immediately upon toggling without requiring a book restart.

* **Streamlined Settings ("Layout" Submenu):**
  * Cleaned up the root settings menu by introducing a unified **Layout** submenu.
  * Consolidated visual layout options under one roof: *3-Page Grid: Show full pages*, *Show chapter marks in slider*, *Text size*, *UI Scale (%)*, and *RTL*.

* **Gesture Manager & Scrubber Actions Integration:**
  * Registered native action: **Page Scrubber: Toggle RTL**. You can now bind reading direction toggling to any swipe or tap gesture in KOReader (*Settings > Taps and gestures > Gesture manager > Reader*).
  * Available directly inside **Scrubber Actions** (+ Add action) with a dedicated arrow icon.
  * Displays a quick toast message confirming the active state (`RTL ON` / `RTL OFF`).

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32429083/page_scrubber.koplugin.zip)

# v7.0.0


### ​Full Landscape Mode Support:
 All plugin interfaces (Grid, 6-Grid, Split View, and Table of Contents) have been adapted for landscape reading. The bottom navigation bar has been reorganized into a standardized two-level layout: a clean top row housing page-turning controls and reading telemetry, and a full-width progress slider below, optimizing ergonomics and thumb reach when holding the device horizontally.  

### ​6-Grid Optimization: Significantly reduced loading latency when generating page thumbnails across the 3x2 grid layout, making browsing smoother.

### ​Faster Startup & Reopening: Greatly improved load times when opening, closing, and reopening the scrubber interface during active reading.

### ​Removed Top Bar: Eliminated the redundant top header to give the entire interface more breathing room and maximize vertical space for thumbnails and reading content.

### ​Origin Page Indicator: A subtle gray dot now marks your starting reading page in the top-left corner (in Simple Grid mode, bookmarks are also clearly marked on the header).  

### ​(index) Chapter Bookmark & Highlight Telemetry: The Table of Contents bottom bar now displays real-time counters showing the exact number of bookmarks and highlights present in the current chapter.  

### ​Enhanced Dictionary Typography: Increased the default font size in the dictionary pop-up for more comfortable and legible reading on high-density displays.  

### ​Visual Polish: Refined press feedback and tactile animations across buttons for a cleaner, modern look.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32409558/page_scrubber.koplugin.zip)

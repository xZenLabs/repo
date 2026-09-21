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

# v6.2.2

v6.2.2 Update
 * True Font Scaling: Dictionary text and buttons now strictly scale relative to the book's font size and device DPI, fixing oversized text issues.
 * Quick Search: Added a ... button to the dictionary header that instantly opens KOReader's native search keyboard.
 * Menu Cleanup: Hidden the duplicate native "AI Assistant" from the + menu, keeping your custom AI plugins and the main sparkles.svg button intact.
 * UI Polish: Removed the redundant lookup word from the definition body and fixed header text updates when swiping between dictionaries.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32215700/page_scrubber.koplugin.zip)

# v6.2.1


What's New in 6.2.1
### **Fixed** Third-Party Plugin Compatibility: 
Action buttons registered by external plugins (such as AI dictionary and custom lookup tools) now correctly appear in the "More" menu instead of being incorrectly filtered out. 

### **​Cleaned** Up Action Overlaps: 
Filtered out unsupported "Share text" entries on Kindle and prevented duplicate X-Ray buttons from showing up in the secondary menu. 

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32191999/page_scrubber.koplugin.zip)

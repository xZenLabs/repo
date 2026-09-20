# 7.1.0


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

# v6.2.0

What's New & Improvements

### ​Selection Bar & "More" Menu (more.svg)
​True Toggle Behavior: Tapping more.svg now toggles the "More" menu open and closed, invalidating and repainting the underlying page background to prevent ghosting on E-ink screens.  
​Focused Primary Bar: Streamlined the main toolbar to prioritize instant annotation and reading actions (Highlight, Invert, Underline, Strikethrough, Note, AI, and X-Ray).  
​6 Integrated System Utilities: Consolidated essential lookup tools into a symmetrical top row inside the "More" card (Sel, Copy, Dict, Wiki, Search, and Trans), removing unsupported or crash-prone Kindle actions (View HTML and Share).  
​Bigger Action Icons: Scaled primary action bar icons to scale(36) and "More" menu utility icons to scale(31) for improved legibility.

### Floating Dictionary
1:1 Book Font Scaling: Definition body text matches the active book font size (scale(base_fs)), preserving identical optical proportions during reading.  
Optimized E-ink Contrast: Removed heavy global bolding; definitions render in pure black (#000000) while preserving native bold tags (<b>, <strong>) for senses and entry numbers without clumping font strokes.  
DPI-Based Icon Scaling: Action icons now scale strictly according to screen DPI rather than book font size.  

**​Architecture & Scaling**
​Decoupled Scrubber Scaling (Reading Pop-Ups): Floating menus and buttons now scale directly according to screen resolution and DPI, preventing popup UI from shrinking when the reading scrubber scale is reduced.  

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32178270/page_scrubber.koplugin.zip)

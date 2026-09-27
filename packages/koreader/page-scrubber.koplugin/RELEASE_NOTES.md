# v7.4.9

### Stable pages should be more... stable

**Stable Pages (*Pagemap*)**
* **Pinpoint Accuracy (Zero Drift):** Eliminated the 1 to 5-page drift from earlier math estimations; stable pages now map with exact 1:1 precision against the physical print edition.
* **Correct Page Totals:** Synchronized page counts so Roman numeral front matter no longer inflates the total (e.g., displaying `879 / 879` instead of `879 / 905`).
* **Instant Mid-Screen Updates:** When a new physical page begins mid-screen, the label updates immediately rather than waiting for the next page turn.

**Six Grid Mode**
* **Fixed RTL Traversal:** Left and right buttons turn pages in the correct direction when reading right-to-left.
* **Boundary Auto-Hide:** Block jump buttons automatically disappear upon reaching the start or end of the book.
* **Simplified Return Button:** Removed extra arrows from the origin button in landscape, standardizing it to a clean `Page X` label matching portrait mode.

**Landscape & Views**
* **Auto-Hiding Chapter Controls:** Chapter jump buttons cleanly disappear when reaching the first or last chapter across all landscape layouts (Six Grid, Grid, Split, and Simple Grid).
* **UI Glitch Fix:** Anchored slider geometry to fixed margins, preventing the bottom bar from turning completely blank when chapter buttons hide.
* **No More Ghost Cards:** Eliminated empty white placeholder cards with loading dots beyond book boundaries in Landscape Grid.

**Table of Contents (ToC)**
* **Clean Scrubbing State:** The chapter page counter hides its number and displays only the icon while dragging the slider; the exact count appears instantly upon release over the active chapter.
* **Adaptive Landscape Pagination:** If chapter list pages overflow toward side buttons (✕ and shutter), pagination dots automatically convert into a compact numeric pill (`X / Y`) matching portrait mode.
* **Clean Navigation Controls:** Chapter list jump buttons (`<<`, `<`, `>`, `>>`) dynamically hide at list boundaries.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32694557/page_scrubber.koplugin.zip)

# v7.4.4

### **Table of Contents (ToC) Improvements**
 * **Dynamic Chapter Page Count:** Added a book-open-text metric in the footer displaying total pages for the active chapter, with full physical page label (pagemap) support.
 * Hierarchical Page Counts: Parent sections calculate the cumulative page count of all nested subchapters instead of stopping at the first child entry.
 * Decoupled Same-Page Entries: Removed inline title merging (Parent Chapter · Child Chaoter); items sharing the same starting page now appear as distinct rows with proper indentation.
 * Streamlined Footer Layout: Grouped bookmarks and annotations on the right side to balance the new chapter page stats on the left, fully integrated across Portrait and Landscape views.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32688160/page_scrubber.koplugin.zip)

# v7.4.0

v7.4- What's New
### Custom Dictionary Text Sizes: 
Added a setting with 5 preset font sizes (Very Small, Small, Normal, Large, Very Large) for the floating dictionary. The Normal preset preserves the default 1:1 ratio with the book font size.

### Full-Screen Table of Contents Action: 
Added "Page Scrubber: Index (Table of Content)" to Dispatcher actions, allowing gestures, corner taps, and shortcuts to open the Index directly with the shutter fully lowered.

Bug Fixes & Improvements
-Index Touch Hitbox Fix: Resolved an issue where tapping lower chapter entries with the shutter down triggered the invisible preview hitbox and navigated back to the previous chapter.
-Index E-ink Stability & Preview Scaling: Stabilized E-ink ghosting during slider dragging and ensured the blank preview card maintains consistent dimensions without visual jumping.

**Simple** **Grid** Refresh Bounds: Fixed refresh coordinate calculations in Simple Grid mode to prevent clipping and visual artifacts.

**Localization**:
-Added Turkish (tr) translation.
-Added Brazilian Portuguese (pt_BR) translation.
-Updated existing translations across supported languages.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32639901/page_scrubber.koplugin.zip)

# v7.3.6

### Fixes & Visual Polish (v7.3.2)

* **Display / E-ink:** Fixed full-screen flash on hold release. Switched the gesture release trigger from an unnecessary deep refresh (`partial`) to an instant, smooth refresh (`ui`). Turning pages continuously by holding no longer triggers screen flashes.
* **Floating Dictionary:** Removed the redundant horizontal divider separating the dictionary title from the definition text for a cleaner, unified reading layout. Action and plugin buttons retain their bottom separators.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32589830/page_scrubber.koplugin.zip)

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

# v7.6.0 · 2026-09-30

### What's New

#### Quick Menu Enhancements
* **Typography Tab**: Added a dedicated Typography tab to the Quick Menu. You can now select your favorite fonts, adjust font size, and fine-tune line spacing on the fly.
* **Gesture Support**: The Quick Menu can now be assigned to a gesture (via Dispatcher) to open it directly while reading.
* **Toggleable Quick Menu**: Added a new setting to enable or disable the Quick Menu entirely, keeping things clean for Page Scrubber purists who only want page scrubbing.
* **Default Starting Tab**: Added an option in settings to choose whether the Quick Menu opens by default on the standard actions tab or the new Typography tab.
* **Instant Style Switching**: Changing styles and typography options via the Quick Menu now updates almost instantaneously without loading screens.

#### Selection & Highlights Menu
* **Instant Highlight Style Changes**: Changing highlight styles in the selection/split menu is now seamless—no more loading screens, refreshing almost instantly.

#### Appearance & Settings Polish
* **Top Bar Separator Line**: Added a new toggle in the Appearance menu to draw an optional separator line beneath the top bar.
* **Visual Improvements**: Refreshed the settings menu layout and visual styling for a cleaner, more intuitive look.

#### Localization & Languages
* **New Languages**: Added full translations for Norwegian (`nb`) and Ukrainian (`uk`).
* **Translation Updates**: Updated all existing translation catalogs (German, Spanish, French, Hindi, Italian, Japanese, Dutch, Polish, Portuguese, Russian, Turkish, and Simplified Chinese) to cover the new menus and settings strings.

---

### Bug Fixes

* **TOC Page Count**: Fixed inaccurate page count calculations when opening the Table of Contents via the Dispatcher.
* **Dictionary Double Pop-Up**: Fixed a bug where long-pressing a word occasionally triggered the dictionary pop-up twice.
* **Dictionary Text Bounds**: Fixed font size calculation in the dictionary to ensure "shrink to fit" renders and paints text properly.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32851569/page_scrubber.koplugin.zip)

# v7.5.0 · 2026-09-28

### FastDict Engine
 * **Instant Dictionary** Lookups: Added an in-memory StarDict lookup engine for significantly faster word searches.
 * Reliable Fallback: Retained full compatibility with the native dictionary engine for missing or advanced queries.
Improvements on Dictionary Pop-Up
 * **Dynamic Window Sizing (Shrink-to-Fit)**: The popup automatically shrinks to fit short definitions, getting rid of awkward empty space.
 * **Reorderable Dictionary Buttons:** Custom order and visibility toggles for all bottom actions directly from settings.
 * X-Ray Integration: Integrated X-Ray directly into the dictionary action bar (set to the end by default and if not just move it with the chevron wherever you like).
 
### Improvements on Selection Menu
 * **Custom Action Ordering**: Added full sorting and toggle support for every tool in the text selection toolbar.
 * Smart "More" Button: Easily move the expansion button (...) to appear either first or last on the bar.
 * X-Ray in Selection: Enabled sorting and toggling for X-Ray alongside standard selection tools.

### Scrubber Actions & Settings UI
 * **Reorderable Quick Actions**: Easily rearrange custom launcher actions with up/down arrows or delete them using the trash icon.
 * Adaptive SVG Chevrons: Replaced plain text arrows with native chevron icons that dynamically hide when an item cannot move further.
 * Stability & Touch Fixes: Isolated modal menus to eliminate ghost touches and accidental window closures, keeping menus properly layered during transitions.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32747242/page_scrubber.koplugin.zip)

# v7.4.9 · 2026-09-27

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

# v7.4.4 · 2026-09-26

### **Table of Contents (ToC) Improvements**
 * **Dynamic Chapter Page Count:** Added a book-open-text metric in the footer displaying total pages for the active chapter, with full physical page label (pagemap) support.
 * Hierarchical Page Counts: Parent sections calculate the cumulative page count of all nested subchapters instead of stopping at the first child entry.
 * Decoupled Same-Page Entries: Removed inline title merging (Parent Chapter · Child Chaoter); items sharing the same starting page now appear as distinct rows with proper indentation.
 * Streamlined Footer Layout: Grouped bookmarks and annotations on the right side to balance the new chapter page stats on the left, fully integrated across Portrait and Landscape views.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32688160/page_scrubber.koplugin.zip)

# v7.4.0 · 2026-09-25

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

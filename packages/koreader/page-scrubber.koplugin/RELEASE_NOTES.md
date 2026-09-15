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

# v6.1.0

This update introduces granular annotation management in Split View, typographic synchronization for the dictionary popup, and dedicated top-bar hold shortcuts.

### ​Granular Annotation Management (Split View)
​Individual item entries: Highlights and notes are tracked as separate entries and marked with discrete superscript indices (¹, ², ³) when sharing a page.  
​Targeted actions: Styling (highlight, invert, underline, strikethrough), note editing, and deletions apply strictly to the selected item without modifying neighboring notes on the same page.  
​Isolated preview: The bottom preview card isolates the active item's text instead of concatenating the entire page.  

### ​Dynamic Floating Dictionary
​Book typography matching: Automatically inherits the active book's font family (BookFont), size, and proportional line height.  
​In-Dictionary Deep Lookup: Look up any unknown word directly inside a definition by holding down on it to trigger a new search seamlessly.  
​Font path caching: Speeds up dictionary rendering by resolving and caching font files per document.  

### ​Top-Bar Hold Shortcuts
​Notes button (Hold): Jumps straight to Split View on the Highlights tab.
​Grid button (Hold): Launches Simple Grid mode instantly.
​ToC button (Hold): Opens the Table of Contents in full-screen mode with the bottom preview bar collapsed.  
​Settings button (Hold): Launches Scrubber Actions directly.
​Origin persistence: Retains the original reading page across deep jumps so the ← Page return button stays consistent.  
​Optimized for responsive navigation on E-ink devices. If you encounter an unexpected issue, please attach a crash.log.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32137671/page_scrubber.koplugin.zip)

# v6.0.0

Page Scrubber v6.0 — Release Notes

### Introducing Scrubber Actions: Your Reading Control Center
Access the features and plugins you actually use without leaving your page or digging through KOReader's nested system menus. Scrubber Actions transforms the page scrubber into a customizable hub:
 * Instant Access to Heavy-Hitting Tools: Launch your most important tools in a single tap—open Vocabulary Builder, launch other plugins like Bookshelf or SimpleUI, trigger cloud Progress Sync (push and pull), switch Screen Orientation, jump into Reading Statistics, browse your File Manager, and more.
 * Curated System Palette: Pick up to 8 dedicated shortcuts tailored to your personal workflow from an extensive, filtered list of available system and plugin actions.
 * Frictionless Management: Add, or remove shortcuts on the fly. Active items display a clear checkmark (✓) status, preventing accidental duplicates.
 * Seamless Action Dispatch: Executes chosen actions instantly via the wharehouse icon on the Mini-Menu.
 
### Smart Markdown Annotation Export
Exporting your notes and highlights now preserves the exact style and intent of your reading session:
 * Type-Aware Visual Glyphs: Highlights automatically include dedicated Unicode symbols directly inside Markdown blockquotes (> glyph text):
   * ✪ Standard highlight (lighten)
   * ﹏ Underline (underscore)
   * ◧ Inverted text (invert)
   * ✖ Strikethrough (strikeout)
 * Clean Document Structure: Bookmarks are indexed neatly at the top under ⚑ (⚑ : 12, 34, 85), keeping chapter and page headers clean (## page).
 
### Stability & Internationalization
 * Touch & Modal Crash Fix: Fixed an event-loop crash when selecting duplicate actions, ensuring existing entries are skipped safely without freezing the interface.
 * Full Multi-Language Support: Scrubber Actions is translated into 10 languages: English, Spanish, French, German, Italian, Portuguese, Russian, Simplified Chinese, Japanese, Dutch, and Polish.

[page_scrubber.koplugin.zip](https://github.com/user-attachments/files/32035243/page_scrubber.koplugin.zip)

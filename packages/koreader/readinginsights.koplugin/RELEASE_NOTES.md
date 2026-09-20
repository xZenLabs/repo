# v6.7.0

### New

**Book progress popup**
- **Popup position:** show it at the top of the screen (as before) or as a centered box.
- **Show or hide parts:** you can now turn off This chapter, Next chapter, the Read row, the Reading time row and the Read today row. If everything in a section is off, its header disappears too.
- **All chapters:** the chapter bar can now draw every chapter in one row, with no 100-chapter limit.

**Fixes**
- The remaining reading time now matches Bookends calculation exactly.

You'll find the new options under **Settings → Advanced settings → Book progress popup**.

# v6.6.1

Loading indicator for slow heatmap opens

# v6.6.0

### New

Progress bar for the "This book" section: shows how far you are into the book, on/off toggle plus configurable colors and height in the menu.

# v6.5.3

Reading insights popup: prefetch the other two chart modes (hours/days/books) in the background after opening, so switching modes no longer triggers a slow, uncached DB query the first time each day

# v6.5.2

### Fixed
- In the previous release missed to raise to _meta.lua version. Nothing else changed. #78

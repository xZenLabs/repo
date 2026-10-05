# v0.2.7.24 · 2026-09-30

Smart Webtoon Scroll v0.2.7.24
This release improves the reading experience on different screen aspect ratios and makes the interface cleaner and easier to use.
✨ What's New
- Full Viewport Adaptive Background
  - Smart Webtoon Scroll now analyzes the visible content and automatically chooses a black or white background.
  - The selected color is applied to the entire screen, not just the side margins.
  - Fixes mismatched white/black areas when using Fit-to-Height or Sidebar.
  - Produces a much more seamless result with dark webtoon scenes.
- Symmetric Sidebar Mode
  - Optional sidebar for wide and 3:2 displays.
  - Adjustable from 1–20%.
  - Space is distributed equally between the left and right sides, keeping the webtoon centered.
- Compact Settings
  - Shorter and cleaner setting labels.
  - Easier to use on smaller displays.
  - Settings remain vertically scrollable when they don't fit on screen.
- Configurable Render Preload
  - Choose how many upcoming pages are pre-rendered for smoother navigation.
📖 Improved Chapter Navigation
- Reaching the final Smart Screen can transition directly to the next CBZ/chapter.
- Pressing Previous from the first Smart Screen opens the previous chapter.
- When returning to the previous chapter, Smart Webtoon Scroll automatically restores its last Smart Screen, instead of starting from the top.
⚡ Performance
The adaptive full-screen background uses the existing lightweight edge analysis and a single viewport fill before rendering, so it adds negligible overhead during normal reading.
🔄 Upgrade
v0.2.7.24 is the new recommended stable build.
It includes all improvements introduced since v0.2.7.10 while keeping Smart Webtoon Scroll focused on lightweight, continuous webtoon reading.

# v0.2.7.21 · 2026-09-30

Smart Webtoon Scroll v0.2.7.21
This release focuses on smoother chapter navigation, better support for wider displays, and a more seamless webtoon reading experience.
What's new
- Seamless next-chapter navigation
  Reaching the end of the webtoon strip now transitions correctly to the next CBZ/chapter.
- Previous chapter navigation
  Pressing Previous from the very beginning of a chapter now opens the previous CBZ automatically.
- Return to the correct position
  When moving back to the previous chapter, Smart Webtoon Scroll automatically positions you at its last Smart Screen, instead of opening it from the beginning.
- Symmetric Sidebar mode
  Added an optional sidebar for wider displays, especially useful on 3:2 screens where full-width webtoons can feel too large.
  Sidebar width is configurable from 1–20% and is distributed equally on both sides, keeping the webtoon centered.
- Configurable Render Preload
  Choose how many upcoming pages should be preloaded for smoother navigation.
Improvements
- Cleaner chapter-boundary handling.
- Better continuity between CBZ files.
- Sidebar-aware rendering and layout.
- Maintains automatic black/white side-background handling.
- No additional heavy image processing during normal scrolling.
Reading flow
Previous chapter ← Smart Webtoon Scroll → Next chapter
Chapter navigation now behaves much more like one continuous webtoon, even when the content is split across multiple CBZ files.
Recommended upgrade from v0.2.7.10.

# v0.2.7.10 · 2026-09-25

Release v0.2.7.10

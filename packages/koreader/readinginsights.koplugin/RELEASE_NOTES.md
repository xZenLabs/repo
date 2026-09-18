# v6.6.0

### New

Progress bar for the "This book" section: shows how far you are into the book, on/off toggle plus configurable colors and height in the menu.

# v6.5.3

Reading insights popup: prefetch the other two chart modes (hours/days/books) in the background after opening, so switching modes no longer triggers a slow, uncached DB query the first time each day

# v6.5.2

### Fixed
- In the previous release missed to raise to _meta.lua version. Nothing else changed. #78

# v6.5.1

### Added
- "Show week numbers" option (off by default, in Advanced settings > Date & time): adds a gray week-number column to both reading calendars. #77

# v6.5.0

### New
- Added a hamburger menu to the top-left of the Reading Insights popup's title bar, giving quick access to the Streak, Heatmap, Records, and Achievements popups without navigating the full page.
  - Added an Advanced settings toggle (Reading insight popup → "Hamburger menu") to show/hide it. Default: off.
- French translation added #75 (Thanks @maxxfly) and added some missing translations for other languages.

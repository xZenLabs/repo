# v1.0.0

## v1.0.0 (2026-09-15)

First tagged release of the Dead Reckoning preset: a navigation-themed reading cockpit for KOReader's Bookends plugin.

*   The preset (`dead-reckoning.lua`, a 232-line exporter-format data table): session pages and pace, chapter pages left with a time-to-finish ETA, percent read with pages left and a projected finish date, weekday and date, clock, series line, and battery state with a charging flag and a low-battery warning under 20%, over a pacman-style progress bar with a tick at every chapter boundary.
*   README: layout table, requirements, installation through `settings/bookends_presets/`, a margins note separating KOReader's native status bar and document margins from the preset's internal drawing geometry, and a support section.
*   AGPL-3.0-or-later license, matching the sibling VirInvictus KOReader presets, plus the sibling-standard Lua .gitignore.

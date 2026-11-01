# v1.5.2 · 2026-11-01


### Added
- Slovak (`sk`) and Czech (`cs`) translations.

# v1.5.1 · 2026-11-01


### Fixed
- Cap daily reading-time credits per page turn with KOReader's **Max. read time per page** (`statistics.max_sec`, default 120 s) instead of a hard-coded 45 minutes, so idle time with an open book no longer inflates the daily time target ([#19](https://github.com/advokatb/readingstreak.koplugin/issues/19)).

# v1.5.0 · 2026-09-09


### Added
- **Colors** settings submenu on colour screens (Settings → **Colors**):
  - **Toast color** — background tint for toast notifications (default white).
  - **Calendar fill** — fill colour for streak days in the calendar (default stock gray).

# v1.4.0 · 2026-08-30


### Added
- Optional toast notifications for streak achievements (Settings → Tracking → **Use toast notifications**). When enabled, notifications appear at the top of the screen and dismiss automatically instead of requiring a tap ([#9](https://github.com/advokatb/readingstreak.koplugin/issues/9)).

### Changed
- Removed dead code and unused translations left over from the old modal settings dialog.
- Translations load directly from `locale/*.po` at runtime — no `.mo` compilation required. Ukrainian locale code is now `uk`.

### Fixed
- Skip Project Title footer integration when Project Title is missing, so uninstalling or renaming it no longer crash-loops KOReader ([#14](https://github.com/advokatb/readingstreak.koplugin/issues/14)).

# v1.3.7 · 2026-08-05


### Fixed
- Fixed reading time continuing to run when the device was suspended (thanks to @jandamm, #17).

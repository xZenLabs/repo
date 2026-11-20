# v1.2.2 · 2026-11-20

- Fixed a bug where the screensaver disappeared behind the pinpad dialog.

**Full Changelog**: https://github.com/Lena2309/pinpad_screenlock_plugin/compare/v1.2.1...v1.2.2

# v1.2.1 · 2026-11-16

* A few fixes to improve how the plugin is integrated in Koreader 2026.07..
* Added a release workflow to ease updates.

**Full Changelog**: https://github.com/Lena2309/pinpad_screenlock_plugin/compare/v1.2.0...v1.2.1

# v1.2.0 · 2026-11-16

## What's Changed
* fix: closing background before suspend after first unlock resolved #9 by @fvelsg in https://github.com/Lena2309/pinpad_screenlock_plugin/pull/11
* Fix image size rendering and caching, code cleaning by @Lena2309 in https://github.com/Lena2309/pinpad_screenlock_plugin/pull/13

## New Contributors
* @fvelsg made their first contribution in https://github.com/Lena2309/pinpad_screenlock_plugin/pull/11

**Full Changelog**: https://github.com/Lena2309/pinpad_screenlock_plugin/compare/v1.1.0...v1.2.0

# v1.1.0 · 2025-11-17

**New Features:**
- PIN Pad appearing on the current screensaver without having to rebuild everything.
- Can show digits when typing.
- Pin pad disappears when suspending device before unlocking the pad.
- Additional settings in menu.

**Improved Optimization:**
- Easier installation process with the icon directly in the plugin.
- Less flashy overall.

# v1.0.5 · 2025-10-26

**Fix:**
* The PIN pad does not appear anytime the UIManager runs, which was annoying. Instead the plugin entirely runs via event listening.

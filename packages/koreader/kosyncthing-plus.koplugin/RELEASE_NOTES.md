# v1.2.3 · 2026-11-01

## What's Changed
* Remove legacy support by @d0nizam in https://github.com/d0nizam/kosyncthing_plus.koplugin/pull/9


**Full Changelog**: https://github.com/d0nizam/kosyncthing_plus.koplugin/compare/v1.2.2...v1.2.3

# v1.2.2 · 2026-07-31

## What's Changed
* fix: use POSIX arithmetic in start-syncthing by @Philantrop in https://github.com/d0nizam/kosyncthing_plus.koplugin/pull/8

## New Contributors
* @Philantrop made their first contribution in https://github.com/d0nizam/kosyncthing_plus.koplugin/pull/8

**Full Changelog**: https://github.com/d0nizam/kosyncthing_plus.koplugin/compare/v1.2.1...v1.2.2

# v1.2.1 · 2026-07-23

## [v1.2.1] — 2026-07-23

### Fixed
- **Downloading the legacy binary could fail with "did not contain a valid Linux
  Syncthing binary".** A release archive holds three entries named `syncthing`,
  and the plugin picked whichever the filesystem happened to list first —
  sometimes one of the two helper scripts, which was then correctly rejected as
  not an executable. The legacy download was affected on every device; the
  ordinary binary update only when it fell back from system `tar`. The
  executable is now selected by its path inside the archive and extracted on its
  own. Verified against the v1.2.2, v1.27.12 and v2.x archives.
- **The old-kernel notice reappeared on almost every wake.** The hint pointing
  at Legacy mode was meant to show once, but nothing recorded that it had been
  shown, and `init()` runs on every plugin instantiation — each FileManager to
  Reader transition, and after resume. On an old-kernel device it therefore
  returned indefinitely, and being a delayed pop-up it landed on top of whatever
  was drawing at the time, including lock-screen plugins. It is now shown at
  most once, recorded only when it is actually displayed, and cleared by a
  factory reset. The standing information stays in the menu, which marks
  *Legacy Syncthing* whenever the kernel needs it.

### Changed
- Binary extraction now also falls back to system `tar` if `ffi/archiver` is
  unavailable, which keeps the legacy download working on older KOReader builds
  — the devices most likely to need it.
- Extraction failures now report the underlying reason, so a failed download can
  be diagnosed from the message instead of guessed at.

## What's Changed
* Enhance binary extraction by @d0nizam in https://github.com/d0nizam/kosyncthing_plus.koplugin/pull/6


**Full Changelog**: https://github.com/d0nizam/kosyncthing_plus.koplugin/compare/v1.2.0...v1.2.1

# v1.2.0 · 2026-07-18

## [v1.2.0] — 2026-07-18

### Fixed
- KOReader commit 751b497 removed `Device:unpackArchive`, breaking plugin and binary updates on newer KOReader builds. Added `U.unpackArchive` with a direct `ffi/archiver` fallback so updates work on all KOReader versions.

**Full Changelog**: https://github.com/d0nizam/kosyncthing_plus.koplugin/compare/v1.1.9...v1.2.0

# v1.1.9 · 2026-06-20

## [v1.1.9] — 2026-06-21

### Fixed
- **A successful pairing no longer shows a warning icon.** After accepting a
  pairing request in the wizard, the "Paired with … successfully" message was
  displayed with a ⚠ warning icon instead of the neutral info icon, making a
  success look like something had gone wrong. The icon now matches the outcome.
  (The failure message is unchanged - it still shows the warning icon.)

### Added
- **Windows test setup.** A one-command `spec/setup_windows.ps1` (installs
  MinGW-w64, LuaRocks and `luafilesystem`, then runs the suite) plus Windows
  path/command shims in `spec/run_tests.lua`, so the full 506-test suite runs
  on Windows as well as Linux/WSL. Dev tooling only - not part of the shipped
  plugin.

### Changed
- **The LICENSE is now bundled with the installed plugin.** It was previously
  excluded from the install package; it now ships alongside the runtime files.
- **Dropped the deprecated `name` field from `_meta.lua`.** KOReader derives the
  plugin name from its directory and logs a deprecation warning for a `name`
  key in `_meta.lua`; removing it silences that warning with no change to the
  plugin's identity.

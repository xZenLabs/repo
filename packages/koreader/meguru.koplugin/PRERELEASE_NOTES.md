# v1.8.4-dev-cover · 2026-11-10

Test build for the missing local CBZ cover.

Local CBZ covers are now always rendered from MuPDF page 1.

**Install:** download `meguru.koplugin.zip` below and unzip it into the KOReader plugins folder, replacing the existing `meguru.koplugin`. This is a prerelease, so the plugin updater will not offer it.

# v1.7.2-dev-android-derainbow-fix · 2026-11-01

## Pre-release: Android Derainbow fix — testers with a colour Android screen needed

The **Derainbow** row was missing on Android because the plugin directory lives on
shared storage, which is mounted `noexec`: the system linker refuses to load the
native libraries from there. Meguru now copies the two libraries into the app's
private files directory first and loads that copy, the same way
`derainbowify.koplugin` does.

**What to check on a colour Android device (Boox, Meebook, …):**

- Open a Meguru book → bottom menu → **Tone** tab. A **Derainbow** row should be
  there, after Dithering.
- Turn it on: the page repaints, and `crash.log` shows one
  `Meguru: derainbow filter running (WxH, N ms)` line, then a
  `Meguru: derainbow WxH = N ms` line per tile.
- Panel view, two-page view and zoom should still filter, with no errors in the log.

The row exists only in Meguru books — it does not appear in MuPDF. If it is still
missing, please attach `crash.log`; the lines to look for are
`Meguru: could not stage derainbow library` and
`Meguru: derainbow libraries are present but would not load`.

This is a development build: the updater does not offer it and
`/releases/latest` skips it. Install it by hand from `meguru.koplugin.zip`.

Refs #9.

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.7.1...v1.7.2-dev-android-derainbow-fix

# v1.5.1-dev-derainbow-filter · 2026-10-09

Pre-release: testers with a color E-Ink screen needed, I don't have one. Please check:
- does derainbow work?
- does it work in panel view?
- does it work in dual page mode?

# v1.5.0-dev-derainbow-filter · 2026-10-06

**Full Changelog**: https://github.com/Craftwork2720/meguru/compare/v1.4.0...v1.5.0-dev-derainbow-filter

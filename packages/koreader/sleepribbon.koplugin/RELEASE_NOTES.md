# v1.1.0 · 2026-09-30

SleepRibbon v1.1.0 adds per-book profiles and cover-derived color palettes, while moving the plugin to a more reliable and convenient location directly under KOReader's Settings menu.

### Highlights

- Per-book profiles with Global fallback
- Per-book message, position, opacity, typography, colors and progress-bar settings
- 25-color palette generated from the current book cover
- Cover palette caching and manual refresh
- Direct message, position and opacity controls inside SleepRibbon
- SleepRibbon now appears directly under Settings using KOReader's normal plugin menu registration
- Horizontal padding range now scales with screen width
- Updated preview behavior and menu organization

### Compatibility

Tested with:
- KOReader emulator based on v2026.07.2
- Kindle Colorsoft

### Installation

Download `SleepRibbon-v1.1.0.zip` below, extract the `sleepribbon.koplugin` folder into `koreader/plugins/`, and restart KOReader.

SleepRibbon still requires KOReader's native sleep-screen custom message to be enabled and its container set to **Banner**.

See the README and CHANGELOG for details.

### SHA-256

`09ab6e9f3012512fc7812c4e1c0e0a6f2adc977c0a707acf60fb3d4b429fbed4`

# v1.0.0 · 2026-09-29

Initial public release of SleepRibbon.

SleepRibbon is a minimal, customizable sleep-screen banner plugin for KOReader, designed to display useful reading information while keeping the book cover visually dominant.

### Highlights

- Custom font family, style and size
- Text alignment and horizontal padding
- Custom text and banner background colors
- Optional transparent/no-background mode
- Optional progress bar with configurable position, thickness and colors
- Live preview using the expanded KOReader sleep-screen message
- Persistent fallback for the `%H` time-remaining token
- English, Portuguese and Spanish interface
- No polling, background timers or periodic tasks

### Compatibility

Tested with:
- KOReader emulator based on v2026.07.2
- Kindle Colorsoft

### Installation

Download `SleepRibbon-v1.0.0.zip` below, extract the `sleepribbon.koplugin` folder into `koreader/plugins/`, and restart KOReader.

See the README for configuration details.

### SHA-256

`204c7dfa80b1fc5ab5fc71d66ac39c931fde6af090f7a54ab94e68064ee6da51`

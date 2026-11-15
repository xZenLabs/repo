# v1.2.0 · 2026-11-15

SleepRibbon v1.2.0 introduces full-screen previews and automatic preview updates, making it easier to customize the sleep-screen ribbon and immediately see the result.

### What's new

- **Full-screen preview:** Displays the applicable sleep-screen image with the configured ribbon, respecting KOReader's image scaling and rotation settings.
- **Automatic previews:** Opens the preview after confirmed changes to typography, colors, message, layout, positioning, opacity and progress-bar settings.
- **Profile support:** Preview reflects the selected Global or Current book profile.
- **Non-intrusive operation:** Preview does not suspend the device or change the frontlight intensity.
- **Easy navigation:** Tap anywhere to dismiss the preview and return to the previous menu. Manual preview remains available.

### Installation

1. Download `SleepRibbon-v1.2.0.zip` from the release assets below.
2. Extract the `sleepribbon.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

Existing settings are preserved.

**Note:** KOReader's native sleep-screen custom message must be enabled, with its container set to **Banner**.

For the complete release history, see [CHANGELOG.md](https://github.com/araponga321/sleepribbon.koplugin/blob/main/CHANGELOG.md).

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

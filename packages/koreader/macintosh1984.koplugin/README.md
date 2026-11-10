# Macintosh 1984 for KOReader

**English** | [简体中文](README.zh-CN.md)

Bring the black-and-white Macintosh 1984 interface to KOReader and SimpleUI on any device that can run KOReader.

- Storefront installation and updates
- Manual update checks and installs through GitHub Releases

[Download the latest release](https://github.com/hytaoist/macintosh1984.koplugin/releases/latest)

![Macintosh 1984 for KOReader](preview/mac1984-ui.png)

## Requirements

- A device supported by KOReader
- KOReader installed; currently verified with `v2026.07.2`
- SimpleUI `3.0` is optional and is not required to use the theme

Other devices and KOReader versions may work, but have not been fully verified.

## Features

- 103 KOReader icons optimized for high-resolution e-ink displays
- 34 SimpleUI icons with automatic ChicagoFLF font selection
- Classic striped title bars, square windows, hard shadows, and rounded buttons
- No modifications to KOReader's core Lua source; replaced files are backed up and can be restored from the menu

<details>
<summary>View the complete icon sets</summary>

![KOReader icons](preview/icon-sheet.png)

![SimpleUI icons](preview/simpleui-icon-sheet.png)

</details>

## Installation

### Storefront (Recommended)

1. Open **Storefront** in KOReader.
2. Search for **Macintosh 1984**, or enter the repository name `hytaoist/macintosh1984.koplugin`.
3. After installation, fully quit and reopen KOReader.

Use **Update All** in Storefront to install future updates.

### Manual Installation

Download the latest `macintosh1984-v*.koplugin.zip` and extract it into `koreader/plugins/`. The final directory should be:

```text
koreader/plugins/macintosh1984.koplugin/
```

Alternatively, expose the device storage on a computer and run:

```bash
./install.sh /path/to/mounted-device
```

Fully quit KOReader and reopen it after installation. If the theme does not appear,
make sure KOReader has fully exited rather than only leaving the app. If only the
plugin menu is visible, open **Tools → Macintosh 1984 → Theme diagnostics**.

Current releases include a compatibility fallback that loads the theme when
KOReader skips or disables startup user patches.

### Upgrading from `mac1984-koreader.koplugin`

Existing Storefront installations keep working with **Update All**; Storefront
updates the folder that is already installed. The built-in **Check for updates**
path also follows GitHub's rename redirect automatically.

For a manual side-by-side install, remove the old
`koreader/plugins/mac1984-koreader.koplugin/` folder after extracting the new
package. `install.sh` does this automatically. If both folders are present, the
new plugin takes precedence, disables the old folder for the next start, and
offers **Remove old plugin folder** in its menu. User settings and the
original-file backup in `.mac1984-theme` are preserved.

## Updates

- Storefront users: **Storefront → Update All**
- Manual-install users: **Tools → Macintosh 1984 → Check for updates**

Manual updates are verified against the SHA-256 checksum published with the
release, and an interrupted update restores the previous plugin folder on the
next start.

Restart KOReader when prompted after updating.

## Plugin Menu

The **Tools → Macintosh 1984** menu lets you:

- Toggle pinstripes and window shadows immediately
- Switch between the ChicagoFLF and system UI fonts, or enable safe mode (restart required)
- Reinstall or repair theme files
- Check for updates
- Disable the theme and restore the original files
- Inspect startup patch and theme runtime diagnostics
- View version and about information

## Sponsor

If this theme is useful to you, you can scan the WeChat reward code to support ongoing maintenance:

**Tools → Macintosh 1984 → About → Sponsor this project → Show WeChat reward code**

## Restore and Uninstall

First run:

**Tools → Macintosh 1984 → Disable and restore original files**

Then remove the plugin from Storefront or `koreader/plugins/`. You can also run:

```bash
./uninstall.sh /path/to/mounted-device
```

## Development

See [DEVELOPMENT.md](DEVELOPMENT.md) for build, test, deployment, and advanced configuration details.

This is an unofficial fan theme and is not affiliated with Apple or the KOReader project.
The code is licensed under MIT, the icons under CC0, and the font license is available at
`assets/fonts/LICENSE-ChicagoFLF.txt`.

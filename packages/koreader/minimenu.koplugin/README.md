# MiniMenu for KOReader

![MiniMenu popup menu with a nested submenu over a book page](assets/header.png)

Create popup menus you can open from a tap, gesture, or another
plugin.  
Inspired by the start menu in [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin).

## Install

Download `minimenu.koplugin.zip` from the
[latest release](https://github.com/vishnumad/minimenu.koplugin/releases/latest),
unzip it into KOReader's `plugins/` folder and restart.

### Updates

Choose **Tools (<picture><source media="(prefers-color-scheme: dark)" srcset="assets/koreader-tools-icon-dark.svg"><img src="assets/koreader-tools-icon.svg" alt="" height="18" align="absmiddle"></picture>) › MiniMenu › Check for updates**. If you installed v1.0.0
or v1.0.1, update by hand once, as above.

## Usage

1. **Tools (<picture><source media="(prefers-color-scheme: dark)" srcset="assets/koreader-tools-icon-dark.svg"><img src="assets/koreader-tools-icon.svg" alt="" height="18" align="absmiddle"></picture>) › MiniMenu › New menu…** creates a new menu.
2. Open the menu's page and choose **Edit items…** to add, remove and
   arrange items.
3. Bind it in **Settings (<picture><source media="(prefers-color-scheme: dark)" srcset="assets/koreader-settings-icon-dark.svg"><img src="assets/koreader-settings-icon.svg" alt="" height="18" align="absmiddle"></picture>) › Taps and gestures › Gesture manager** under
   **General › MiniMenu: <name>**.

## Development

Install project dependencies with `mise install`.  
Set up [mise](https://github.com/jdx/mise) if you don't have it.

```sh
make check
make lint
make fmt
make fmt-check
make test       
make integration KOREADER_DIR=<emulator>/koreader # Add KO_PLUGINS_DISABLED=zenos to skip plugins installed in the emulator
```

### Publishing a new release

```sh
make release VERSION=x.y.z
git push origin master vx.y.z
```

### Icons
`minimenu/icons/glyphs.lua` is generated from KOReader's bundled symbols font:

```sh
mise exec uv@latest -- uv run --no-project --with fonttools \
    python tools/gen_glyphs.py <koreader>/resources/fonts/nerdfonts/symbols.ttf
```

# MiniMenu for KOReader

![MiniMenu popup menu with a nested submenu over a book page](assets/header.png)

Create popup menus you can open from a tap, gesture, or another
plugin.  
Inspired by the start menu in [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin).

## Install

Copy `minimenu.koplugin` into KOReader's `plugins/` folder and restart.

## Usage

1. **Tools › MiniMenu › New menu…** creates a new menu.
2. Open the menu's page and choose **Edit items…** to add, remove and
   arrange items.
3. Bind it in **Settings › Taps and gestures › Gesture manager** under
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

### Icons
`minimenu/icons/glyphs.lua` is generated from KOReader's bundled symbols font:

```sh
mise exec uv@latest -- uv run --no-project --with fonttools \
    python tools/gen_glyphs.py <koreader>/resources/fonts/nerdfonts/symbols.ttf
```

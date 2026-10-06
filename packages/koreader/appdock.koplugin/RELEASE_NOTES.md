# v7.4.10 · 2026-10-06

# AppDock 7.4.10 — Live keyboard input

## Live text entry

- The AppDock keyboard now reports every edit immediately through a live-change callback.
- AppDock-owned input flows no longer leave a KOReader `InputDialog` visible behind the AppDock keyboard.
- The original action callbacks remain compatible: `Search`, `Save`, `Unlock`, and similar actions still receive the current value when `Done` is pressed.
- The AppDock homescreen search bar now displays and filters the entered text while typing.
- Secure numeric fields remain masked.

## dChat compatibility

- dChat is integrated as an external KOReader plugin through AppDock's optional Beta plugin host, not as a built-in AppDock DApp.
- Standard dChat input dialogs captured by the host now use the same dialog-free AppDock editor and receive the value live through the original plugin input object.
- Complex standalone dChat windows that do not expose a standard KOReader input dialog remain outside AppDock's interception scope.

## Verification

- Lua 5.1 syntax validation passed for the plugin and tests.
- AppDock keyboard regression test passed, including live target updates and native-dialog closure.
- Browser regression test passed.

# v7.4.9 · 2026-10-05

# AppDock 7.4.9

Die PNG-Logo-Bibliothek enthält jetzt zusätzlich textfreie, transparente Rasterlogos für dChat, DockUpdate und Minecraft. Die DApp-Definitionen verwenden die neuen Logo-IDs `dchat`, `dockupdate` und `minecraft`; die klassische thematische FrameContainer-Darstellung bleibt unverändert.

# v7.4.8 · 2026-10-05

# AppDock 7.4.8

Die experimentellen Surface- und Liquid-Glass-Bilder sowie die zugehörige Surface-Schicht wurden vollständig entfernt. AppDock verwendet wieder die klassischen thematischen FrameContainer-Flächen.

Die PNG-Logo-Bibliothek wurde um echte, textfreie Rasterlogos für Kalender, Rechner, Dokumente, Musik und Batterie erweitert. Das Batterie-Logo wird zusätzlich im WidgetGenerator neben dem Batteriestand angezeigt.

# v7.4.7 · 2026-10-05

# AppDock 7.4.7

Dies ist der vollständige Liquid-Glass-Fix aus dem aktuellen Main-Stand. Die alten farbigen FrameContainer-Füllungen bleiben unsichtbar, die echten PNG-Flächen werden flexibel auf Breite und Höhe gestreckt und formmaskierte Liquid-Glass-Varianten verhindern Überstand an Kreis-, Kachel-, Container- und Pill-Rändern.

# v7.4.6 · 2026-10-05

## AppDock 7.4.6 — DockUpdate Asset Fix

### Fixes

- Resized all generated PNG surface assets to DockUpdate-compatible dimensions.
- Kept the assets as real RGBA raster images; no SVGs were added.
- Moved the liquid-glass texture off the homescreen background.
- Liquid glass is now applied only inside AppDock buttons, app tiles, cards, pills and Quick Settings containers, underneath the active theme color.

### Validation

- Lua 5.1 syntax check passed for all plugin Lua files.
- PNG assets are RGBA and no larger than 1024 pixels on their longest side.

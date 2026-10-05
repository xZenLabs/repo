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

# v7.4.5 · 2026-10-05

## AppDock 7.4.5 — Raster Surfaces & Liquid Glass

### Highlights

- Replaced rigid homescreen cards and launcher surfaces with real AI-generated RGBA PNG overlays.
- Added a dedicated circular raster overlay for round app tiles and round navigation buttons.
- Added a text-free liquid-glass background texture for the homescreen.
- Applied raster surfaces to homescreen cards, app tiles, search/header pills, quick-access containers and Quick Settings tiles.
- Theme colors remain dynamic: the PNGs provide only neutral texture, highlights and depth while the active AppDock theme supplies the actual surface color.
- Added `appdock_surface.lua` as the shared surface-layer implementation.
- No SVG artwork was introduced.

### Validation

- Lua 5.1 syntax check passed for all plugin Lua files.
- Keyboard and browser regression tests passed.
- DApp regression test remains dependent on the external `lfs` Lua module in the test environment.

# v8.7.0 · 2026-11-01

- Vector graphics
- STYLUS **PRESSURE** driver
- Stylus driver
- Different brushes
- lasso
- Moveable, resizeable canvas
- etc.

# v8.6.2 · 2026-11-01

Fixed major issue with color pallette on Homescreen when using a store theme

# v8.6.1 · 2026-11-01

Oh man...

# v8.5.11 · 2026-10-26

# AppDock 8.5.11 — Game-Updates über bereits installierte Pakete

Der AppStore kann Game-Pakete jetzt aktualisieren, wenn die vorherige Version bereits unter `.adds` installiert ist. Beim Update werden die vom ZIP gelieferten Binärdateien und Standard-Level ersetzt, während weitere Daten im Game-Home erhalten bleiben.

Damit scheitern Updates nicht mehr an vorhandenen Dateien aus der zuvor installierten ZIP-Version.

# v8.5.10 · 2026-10-26

# AppDock 8.5.10 — Game-Installer-ZIP-Prüfung

Der separate `unzip -tq`-Vorabtest wurde entfernt. Auf dem Kobo schlug genau dieser Test fehl, obwohl der Installer anschließend die normale Extraktion hätte ausführen können. Der Game-Installer prüft das ZIP weiterhin vor dem Entpacken auf unsichere Pfade; maßgeblich für die Integrität ist jetzt der Exit-Status der tatsächlichen Extraktion, die ZIP-Daten und CRCs dabei ebenfalls überprüft.

Die kurze, stufenspezifische Fehlermeldung aus 8.5.9 bleibt erhalten, falls die eigentliche Extraktion nach diesem Fix weiterhin fehlschlägt.

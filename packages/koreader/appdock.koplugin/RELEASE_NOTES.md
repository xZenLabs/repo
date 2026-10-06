# v7.7.0 · 2026-10-06

# AppDock 7.7.0

## Intuitivere Homescreen-Bearbeitung

- Ein dauerhaft sichtbarer **Edit**-Knopf startet den Editmodus direkt im normalen und im Simple-Modus.
- Langes Drücken auf eine App startet die Bearbeitung sofort statt zunächst ein separates Verwaltungsmenü zu öffnen. Während der Bearbeitung bleibt das App-Menü über langes Drücken erreichbar.
- Die ausgewählte App wird hervorgehoben; kurze Hinweise erklären Ziehen, Verschieben und Beenden.
- Widget-Größenregler sind größere Touch-Ziele und zeigen den aktuellen Maßstab, zum Beispiel **125 %**.
- **Fertig** beendet den Editmodus. Regressionstests prüfen den sichtbaren Einstieg, den direkten Langdruck, Größenanzeige und Abschluss.

# v7.6.1 · 2026-10-06

# AppDock 7.6.1

## Hotfix: App-Verschieben im Homescreen-Editor

Fixes a crash when moving pinned apps in the homescreen editor. The app-order helper is now loaded at plugin scope, where `AppDock:movePinned()` can access it. A regression test exercises the real `movePinned` method and verifies persistence of the new order.

# v7.6.0 · 2026-10-06

# AppDock 7.6.0

## Visueller Homescreen-Editmodus
- Langes Drücken auf eine angeheftete App öffnet den Manager; **Homescreen bearbeiten** startet den Editmodus direkt am Homescreen.
- Das gerasterte Layout erlaubt, Apps per Drag-and-drop in eine andere Zelle zu verschieben. Die neue Reihenfolge wird gespeichert.
- Store-Widgets lassen sich im Editmodus per Drag-and-drop neu anordnen. Plus-/Minus-Aktionen skalieren einzelne Widgets unabhängig voneinander zwischen 75 % und 150 %; die Einstellung bleibt erhalten und der Standardmaßstab wird beim Zurücksetzen nicht als unnötiger Konfigurationswert gespeichert.
- **Fertig** beendet den Modus. Die Bedienung funktioniert sowohl im normalen als auch im Simple-Modus.
- Regressionstests decken den Einstieg, die App-Verschiebung, das Widget-Reordering, individuelle Widget-Skalierung und den Abschluss des Editmodus ab.

# v7.5.2 · 2026-10-06

# AppDock 7.5.2

## Scroll- und Suchaktualisierung

- Der AppStore-Scroller reserviert seine Scrollbarbreite zusätzlich zur nutzbaren Zeilenbreite. Dadurch bleiben Karten- und Installationsaktionen beim Scrollen sichtbar statt unter der Scrollbar abgeschnitten zu werden.
- Nach einer über die DuckDuckGo-Homescreenleiste gestarteten Suche wird nach dem Browser-Neuaufbau ein vollständiger E-Ink-Bildschirmrefresh eingeplant.
- Regressionstests prüfen den Full-Refresh-Pfad; AppStore- und DApp-Tests berücksichtigen die reservierte Scrollbar.

# v7.5.1 · 2026-10-06

# AppDock 7.5.1

## AppDock Store identity

- Replaced the external Play mark and “Google Play” wordmark in the store header with AppDock’s existing AppStore logo and the **AppDock Store** wordmark.
- Updated the AppStore regression test to require the AppDock identity and reject the old external branding.
- Clarification: current catalog rows use the catalog-declared AppDock logo kind and AppDock’s logo renderer; they do not currently load per-app PNG artwork directly from the remote catalog. The logo renderer can use bundled PNG assets for supported built-in logo kinds, with a procedural fallback when no bundled image exists.

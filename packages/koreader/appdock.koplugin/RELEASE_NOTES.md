# v7.8.2 · 2026-10-07

# AppDock 7.8.2

## Deutsch

### Settings-App
- Die Settings-App wurde fast vollständig an die Android-Settings-Optik angepasst.
- Neue linke Kategoriennavigation mit Icons, Untertiteln und hervorgehobener aktiver Kategorie.
- Neues Suchfeld zum Filtern der AppDock-Einstellungen.
- Einstellungen erscheinen jetzt als gruppierte, scrollbarere Android-/Material-Präferenzzeilen.
- Zeilen enthalten Chevron-Navigation, verständliche Icons und native wirkende Ein-/Aus-Schalter.
- Der Bereich **Display** zeigt eine klickbare Hell-/Dunkelmodus-Vorschau.
- Bestehende Settings-Aktionen, Persistenz und KOReader-Nativeinstellungen bleiben erhalten.

### Qualitätssicherung
- Lua-Syntax aller Plugin-Dateien geprüft.
- Regressionstests für Keyboard, AppStore, Browser, DApps, Reihenfolge und Setup-Assistent erfolgreich ausgeführt.
- Neue Regressionen prüfen Suchfeld, Kategorien, Präferenzzeilen, Scroll-Layout, Display-Vorschau und Switches.

## English

### Settings app
- The Settings app is now closely aligned with the Android Settings visual language.
- Added icon-based left category navigation with subtitles and an active category state.
- Added a settings search field for filtering AppDock preferences.
- Preferences are rendered as grouped, scrollable Android-/Material-style rows.
- Rows include chevron navigation, semantic icons, and native-looking on/off switches.
- **Display** now includes a clickable light/dark appearance preview.
- Existing Settings actions, persistence, and KOReader-native controls remain intact.

### Quality assurance
- Lua syntax checked for all plugin files.
- Keyboard, AppStore, Browser, DApps, ordering, and setup-assistant regression tests pass.
- New regressions cover the search field, categories, preference rows, scroll layout, display preview, and switches.

# v7.8.1 · 2026-10-07

# AppDock 7.8.1

## Deutsch

### Schnelleinstellungen

- Das Dropdown hat jetzt eine klar umrandete Fläche und im normalen Modus einen sichtbaren Griff.
- Die Schnellkacheln verwenden aussagekräftige AppDock-Symbole statt Buchstaben-Platzhaltern.
- Die Schließen-Schaltfläche in der Kopfzeile funktioniert jetzt tatsächlich.
- Der Helligkeitsregler zeigt einen eigenen Schieberknopf; Touchpositionen werden korrekt relativ zur Bildschirmposition des Reglers ausgewertet.
- Der kompakte Simple Mode bleibt erhalten und bekommt ebenfalls Symbole, einen Schließen-Zugang und einen klar erkennbaren Helligkeitsregler.

### Qualitätssicherung

- Regressionen prüfen Symbole, Griff, Schließen-Aktion und Helligkeits-Touchpositionen in den relevanten Modi.
- Lua-Syntax und alle sechs verfügbaren Regressionstests erfolgreich geprüft. Der optionale BWR-Video-Testdatensatz war in der Testumgebung nicht vorhanden.

## English

### Quick Settings

- The dropdown now has a clearly outlined sheet and a visible grab handle in the normal mode.
- Quick tiles use meaningful AppDock icons instead of letter placeholders.
- The close control in the header now works as expected.
- The brightness slider displays its own thumb, and touch positions are correctly mapped relative to the slider's screen position.
- Simple Mode remains compact and also receives icons, a close action, and a clearly visible brightness thumb.

### Quality assurance

- Regression tests cover icons, the grab handle, the close action, and brightness touch positioning in the relevant modes.
- Lua syntax and all six available regression tests pass. The optional BWR Video test fixture was not present in the test environment.

# v7.8.0 · 2026-10-07

# AppDock 7.8.0

## Deutsch

### Android-inspirierter Homescreen

- Der normale Homescreen wurde mit einer kompakten Statuszeile und einer breiten, einzeiligen DuckDuckGo-Suchleiste neu aufgebaut.
- Zuletzt verwendete Apps erscheinen als beschriftungsfreies Icon-Dock am unteren Rand. Ein gezeichnetes Raster-/Suchsymbol öffnet **Alle Apps**; die AppDock-Oberfläche verwendet keine Google-Logos oder -Marken.
- Geräte- und Lesekarten stehen als ruhige, abgerundete Info-Karten nebeneinander.
- Store-Widgets werden bei mehreren Installationen zweispaltig angeordnet. Eine vergrößerte Karte kann die gesamte Zeile einnehmen; die übrigen Widgets fließen darunter weiter.
- Im Editmodus werden nicht editierbare Blickfang-Karten vorübergehend ausgeblendet. Widget-Ziele berücksichtigen nun sowohl die horizontale als auch die vertikale Position.

### Qualitätssicherung

- Regressionen für Suchleiste, Icon-Dock, Widget-Spalten, Größenänderung, Zeilenumbruch und zweidimensionales Widget-Verschieben ergänzt.
- Lua-Syntax und alle sechs verfügbaren Regressionstests erfolgreich geprüft.

## English

### Android-inspired homescreen

- Rebuilt the normal homescreen around a compact status row and a wide, single-line DuckDuckGo search pill.
- Recently used apps appear in a label-free icon dock at the bottom. A custom drawn grid-and-search glyph opens **All apps**; the AppDock UI uses no Google logos or marks.
- Device and reading cards sit side by side as calm, rounded glance cards.
- Multiple Store widgets use a two-column layout. Enlarged cards can span the full row, with remaining widgets reflowing below.
- Non-editable glance cards temporarily yield space in edit mode. Widget drop targets now use both horizontal and vertical position.

### Quality assurance

- Added regression coverage for the search pill, icon dock, widget columns, resizing, reflow, and two-dimensional widget dragging.
- Lua syntax and all six available regression tests pass.

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

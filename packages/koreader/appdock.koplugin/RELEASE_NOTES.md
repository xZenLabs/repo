# v7.9.3 · 2026-10-10

# AppDock 7.9.3 — Stabilität und Bedienbarkeit

## Fehlerkorrekturen

- Das Page-Key-Hold-Verhalten aus **7.8.51** bleibt erhalten. Powerdialog und Screensaver werden erst im nächsten UI-Zyklus geöffnet, nachdem KOReader den aktuellen Hardware-Tastenwiederholungs-Callback abgeschlossen hat. Dialog und Screensaver verbrauchen verbleibende Wiederholungen der gehaltenen Taste.
- AppDock-eigene Auswahl-, Eingabe-, Bestätigungs- und Statusdialoge verwenden ihre eigene Tap-Geometrie korrekt. Das beseitigt den Absturz beim Zeichnen eines Dialogs, der entstehen konnte, wenn KOReader eine GestureRange-Callbackfunktion als Geometrie behandelte. AppDock-WLAN-Statusmeldungen bleiben im eigenen Overlay.
- Draw startet auch auf Geräten, deren Screen-API `getSize()` statt `getWidth()`/`getHeight()` anbietet. Außerdem folgen Canvas und Werkzeug-Buttons mit ihren Touch-Bereichen jetzt den tatsächlichen Bildschirmkoordinaten.
- Die fehlerhafte **Draw**-Schnellkachel ist durch **Rotate** ersetzt. Die neue Kachel wechselt die von KOReader unterstützten Bildschirmausrichtungen; vorhandene gespeicherte Draw-Kacheln werden bei der nächsten Konfiguration einmalig in eine Rotate-Kachel umgewandelt.
- Farbvideos stürzten beim Schreiben der BRC2-Frames ab, weil ein KOReader-`ColorRGB32`-Struct über einen `uint32_t*` gespeichert wurde. Der Decoder schreibt nun durch den korrekten Struct-Zeigertyp in das RGB32-BlitBuffer; die fünf reinen Palettenfarben bleiben unverändert.

## Prüfung

Alle 12 Lua-Regressionsdateien liefen erfolgreich. Die Tests enthalten jetzt gezielte Prüfungen für den echten Draw-DApp-Hoststart, getSize-only-Geräte, absolute Touch-Geometrie, eigene Dialogaktionen und Tastatureingabe, die Migration der Kachel, den `SetRotationMode`-Event sowie das KOReader-`ColorRGB32`-Pixelformat. Alle Lua-Quelldateien lassen sich mit LuaJIT kompilieren; `git diff --check` ist sauber.

# v7.9.2 · 2026-10-10

# AppDock 7.9.2 — Draw-Zeichenfläche korrigiert

## Fehlerkorrektur

- Die Draw-Werkzeuge und das Zeichen-Canvas werden jetzt in einem KOReader-`OverlapGroup` anhand ihrer vorgesehenen Offsets angeordnet. Das behebt die fehlerhafte Darstellung beim Öffnen der Mal-App, bei der Inhalte am oberen linken Bildschirmrand überlagert werden konnten.
- Die Zeichenfläche wird im Regressionstest nun über die vollständige Pane-Geometrie aufgebaut; der Test prüft die tatsächliche Toolbar-/Canvas-Positionierung und den weißen Start-Hintergrund.

## Prüfung

Alle 11 Lua-Regressionsdateien liefen erfolgreich. Sämtliche AppDock-Lua-Quelldateien ließen sich mit LuaJIT kompilieren; `git diff --check` meldete keine Formatfehler.

# v7.9.1 · 2026-10-10

# AppDock 7.9.1 — YouTube MiniPlayer, schnellere Farbe und Draw-Kachel

## Änderungen

- **YouTube-Oberfläche:** Stellt das Watch-Layout aus 7.8.51 wieder her. Videos aus der Bibliothek und „Up next“ öffnen standardmäßig im MiniPlayer; Vollbild bleibt über die ausdrückliche Vollbild-Aktion verfügbar.
- **Schnellere Farbumwandlung:** Der optionale Fünf-Farben-Pfad nutzt vor der Palette-Ditherung FFmpegs `fast_bilinear`-Scaler statt des rechenintensiveren Lanczos-Filters. Auflösung und Bildrate bleiben unverändert; die Ausgabe enthält weiterhin ausschließlich reines Rot, Grün, Blau, Schwarz und Weiß. Der schnellere Skalierer kann etwas weniger fein wirken.
- **Draw in Quick Settings:** Eine semantisch gezeichnete Draw-Kachel startet die integrierte Mal-DApp. Sie ist konfigurierbar und auch im Simple Mode verfügbar. Bestehende Kachel-Listen erhalten Draw einmalig; nach einer bewussten Entfernung wird die Kachel nicht automatisch wieder hinzugefügt.
- Die Wiedergabe-Timing-Verbesserung aus 7.9.0 bleibt erhalten; Änderungen an der MiniPlayer-UI setzen das unmittelbare Video-Startverhalten nicht zurück.

## Prüfung

Alle 11 Lua-Regressionsdateien liefen erfolgreich; sämtliche AppDock-Lua-Quelldateien ließen sich mit LuaJIT kompilieren und `git diff --check` meldete keine Formatfehler. Ein lokaler synthetischer FFmpeg-Skalierungstest (1280×720 → 600×800, 12 fps, 12 Sekunden) lief mit `fast_bilinear` in 0,174 s gegenüber 0,228 s mit Lanczos (rund 24 % schneller auf dieser Sandbox-CPU; tatsächliche Reader-Hardware kann abweichen).

# v7.9.0 · 2026-10-10

# AppDock 7.9.0 — Draw, YouTube-Farbe und Dialoge

## Neu in 7.9.0

- **Eigene AppDock-Dialoge:** Auswahl-, Eingabe-, Bestätigungs- und Statusdialoge der AppDock-Oberfläche verwenden jetzt ein gemeinsames, kontrastreiches AppDock-Overlay. WLAN-Schaltvorgänge zeigen AppDock-eigenen Verbindungsstatus statt KOReaders transienter Ein-/Ausschalt-Popups.
- **Optionale YouTube-Farbwiedergabe:** Der neue BRC2-Framepfad nutzt eine feste Palette aus Weiß, Schwarz sowie reinem Rot, Grün und Blau. Geordnetes Dithering kann räumlich zwischen diesen Palettenfarben wechseln; RGB-Mischpixel werden nicht ausgegeben. Monochromes BWR1/BWR2 bleibt abwärtskompatibel.
- **Draw-DApp:** Schnelle Zeichenfläche mit Stift, Radierer, vier Pinselgrößen, Linie, Rechteck, Kreis, Füllwerkzeug und bis zu sechs Ebenen.
- Zeichnungen lassen sich als begrenztes, nicht ausführbares `.adraw`-Projekt speichern und laden oder über ein bereits vorhandenes `ffmpeg` als JPEG exportieren.
- Optionales Dithering für die fünf reinen Farben. Druck- und Stylus-Tastenfelder werden genutzt, sofern KOReader sie im Eingabeereignis bereitstellt; Geräteunterstützung variiert.
- Bestehende Installationen erhalten Draw bei der Layoutmigration einmalig als Launcher-Kachel hinter YouTube. Eine später manuell entfernte Kachel wird nicht erneut angelegt.

## Umfangsgrenze

AppDock-eigene Oberflächen verwenden nun AppDock-Dialoge. Eigenständige Ansichten und Dialoge, die KOReader selbst oder fremde Plugins außerhalb der AppDock-Oberfläche öffnen, bleiben unter deren Kontrolle; AppDock verändert diese nicht global.

# v7.8.51 · 2026-10-10

# AppDock 7.8.51

## Flüssigere Wiedergabe auf E-Ink-Geräten

Beim Start der YouTube-Wiedergabe deaktiviert der Player KOReaders Einstellung `color_rendering` temporär. Dadurch verwendet KOReader während der Wiedergabe den schnelleren Rendering-Pfad, was besonders auf Kobo-MTK-Geräten zu flüssigerem Video führt.

Beim Stoppen des Players wird der vorherige Wert exakt wiederhergestellt. Das gilt auch dann, wenn die Einstellung vorher nicht in der KOReader-Konfiguration vorhanden war. Die Änderung wird über `ColorRenderingUpdate` sofort an KOReader gemeldet.

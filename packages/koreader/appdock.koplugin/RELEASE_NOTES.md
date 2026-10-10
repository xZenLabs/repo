# v7.9.12 · 2026-10-10

# AppDock 7.9.12

## Echter Vollbildmodus für YouTube

Die YouTube-Wiedergabe kann jetzt die gesamte AppDock-Displayfläche nutzen. AppDock-Kopf- und Navigationsleisten werden ausgeblendet, und der Videoplayer erhält den vollständigen Bildschirmbereich.

Eine eingeblendete Steuerleiste bietet die Rückkehr zur Bibliothek, Zurück-/Vorwärtsspringen um fünf Sekunden, Wiedergabe/Pause und Neustart. Beim Zurückkehren zur Bibliothek läuft das Video im MiniPlayer weiter. Das zuvor verwendete AppDock-Layout beziehungsweise die Fenstergröße wird beim Verlassen des Vollbildmodus wiederhergestellt.

## Validierung

Alle 12 Lua-Regressionstests bestehen; alle Plugin-Lua-Module und Testskripte kompilieren mit LuaJIT. Der DApp-Test meldet zusätzlich, dass sein optionales externes BWR-Video-Fixture in dieser Umgebung nicht installiert ist.

# v7.9.11 · 2026-10-10

# AppDock 7.9.11

## Deutlich schnellere YouTube-Farbkonvertierung

Die Farbpackung ersetzt die pixelweise Fehlerdiffusion durch vorberechnete 8×8-Muster. Dadurch muss Lua pro Pixel keine drei Farbfehler mehr berechnen und weitergeben. Farben innerhalb des darstellbaren Palettenbereichs können weiterhin mit mehreren – bei Bedarf allen fünf – exakten Farben Weiß, Schwarz, Rot, Grün und Blau gemischt werden. Neutrale Grautöne und Farben außerhalb des Palettenbereichs behalten die bisherige Paarzuordnung.

Das neue geordnete Muster ersetzt die serpentinische Floyd–Steinberg-Textur durch ein regelmäßiges 8×8-Dithermuster. Im isolierten LuaJIT-Benchmark der Farbpackstufe sank die Bearbeitungszeit eines 632×840-Frames in der Entwicklungsumgebung von 28,9 ms auf 1,1 ms (25,6× schneller, nach einmaligem Aufbau der Lookup-Tabellen). Das ist kein End-to-End-Wert für Download, FFmpeg-Decodierung und Dateischreiben; deren Laufzeit hängt weiterhin von Quelle und Gerät ab.

## Lesbare Draw-Werkzeugleiste

Die Mal-App verwendet jetzt KOReaders natives Button-Widget statt selbst gezeichneter Kleinstbeschriftungen. Größere, fette Schrift auf einer hellgrauen Fläche verbessert den Kontrast; die Werkzeugaktionen und Touchbereiche bleiben erhalten.

## Validierung

Alle 12 Lua-Regressionstests bestehen; alle Plugin-Lua-Module kompilieren mit LuaJIT. Der DApp-Test meldet zusätzlich, dass sein optionales externes BWR-Video-Fixture in dieser Umgebung nicht installiert ist.

# v7.9.10 · 2026-10-10

# AppDock 7.9.10

## YouTube-Farbvideos mit Mehrfarben-Fehlerdiffusion

Die Farbkonvertierung mischt nun über benachbarte Pixel mehr als zwei der fünf erlaubten Palettefarben. Zuvor wurde für jeden Quellpixel unabhängig nur das beste Farbpaar ausgewählt; Farbreste wurden nicht an Nachbarpixel weitergegeben. Ein serpentinischer Floyd–Steinberg-Schritt diffundiert diese Reste jetzt räumlich, sodass passende Bildbereiche beispielsweise Schwarz, Rot und Grün gemeinsam nutzen können. Die tatsächlichen Ausgabepixel bleiben weiterhin exakt Weiß, Schwarz, Rot, Grün oder Blau.

Die Palette begrenzt weiterhin den darstellbaren Farbumfang: Farben außerhalb ihres Mischbereichs – etwa leuchtendes Vollgelb – können nur angenähert werden, nicht exakt dargestellt werden.

## Audio endet beim Verlassen der App

AppDock signalisiert nun direkt die PID des laufenden GStreamer-Players, statt sich auf die möglicherweise abweichende Prozessgruppen-PID von `setsid` zu verlassen. Dadurch wird die Wiedergabe beim Verlassen der YouTube-App zuverlässig gestoppt; der PCM-Datenlieferant beendet sich anschließend ebenfalls.

## Validierung

Alle 12 Lua-Regressionstests bestehen; die Lua-Module kompilieren mit LuaJIT. Neue Farbtests prüfen eine tatsächliche Dreifarbmischung aus Schwarz, Rot und Grün.

# v7.9.9 · 2026-10-10

# AppDock 7.9.9

## Draw-Absturz auf Farbgeräten behoben

Die Draw-Zeichenfläche vergleicht Farbwerte des BlitBuffers nicht mehr mit einem `nil`-Sentinel. Auf Farbgeräten sind diese Werte FFI-CData; ihr Vergleich konnte beim Start einen Fehler in der Gleichheits-Metamethode auslösen. Ein Regressionstest deckt diesen Farbpfad ab.

## Natürlichere YouTube-Farben durch Dithering

Die BRC2-Palettenzuordnung bewertet Kandidaten nun in einem farbempfindlichen YUV-Farbraum. So werden Mischfarben wie Gelb, Cyan und Magenta durch Dithering mit den passenden reinen Grundfarben dargestellt, statt überwiegend in Schwarzweiß oder mit unpassenden Farbtönen zu erscheinen. Die Ausgabe bleibt auf die fünf erlaubten Farben beschränkt.

## Kobo-MTK-Audiowiedergabe wiederhergestellt

Der MediaTek-GStreamer-Pfad verwendet wieder rohe PCM-Daten über `fdsrc`, wie im funktionierenden Release 7.8.51, statt vom optionalen `wavparse`-Plugin abzuhängen. Der tatsächliche WAV-Datenoffset wird auch bei zusätzlichen RIFF-Metadaten berücksichtigt; das PCM-Kanal-Layout ist explizit angegeben. Pause und Stopp steuern die zugehörige Prozessgruppe.

## Validierung

Alle 12 Lua-Regressionstests bestehen. Die Plugin-Module kompilieren mit LuaJIT; außerdem wurde die GStreamer-PCM-Pipeline mit einem Test-Sink und einer WAV-Datei mit zusätzlichem `LIST`-Chunk geprüft.

# v7.9.8 · 2026-10-10

# AppDock 7.9.8

## Fix: lesbarer Text in AppDock-Dialogen

Korrigiert den Kontrast der neuen AppDock-eigenen Dialoge. Titel, Aktionsbeschriftungen und Seitennavigation verwenden nun schwarze Schrift auf weißen oder hellgrauen Flächen. Schwarze Flächen hinter Text wurden entfernt, damit die Beschriftungen auch auf KOReader-Renderpfaden mit invertierter Textdarstellung erkennbar bleiben.

Ein Regressionstest prüft die Textfarbe und die hellen Dialogflächen.

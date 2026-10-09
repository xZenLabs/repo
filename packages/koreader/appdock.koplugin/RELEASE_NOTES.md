# v7.8.30 · 2026-10-09

# AppDock 7.8.30

## Schnellere Videokonvertierung

- FFmpeg übernimmt standardmäßig die 1-Bit-Umwandlung (`monow`) statt jeden Grauwert-Frame pixelweise durch den Lua-Bayer-Encoder zu schicken. Bestehende Installationen werden einmalig auf diesen schnelleren Modus umgestellt. Die Bayer-Matrix bleibt unter **YouTube → Tools → Dithering** auswählbar.
- Die BWR2-Frameverarbeitung nutzt größere CPU-Batches (bis zu 12 Frames bzw. 160 ms pro Tick) mit kürzeren Leerlaufzeiten zwischen UI-Ticks.
- Der BWR2-Writer bildet XOR-Deltas mit 32-Bit-Operationen, vermeidet eine zusätzliche Kopie zum zlib-Encoder und überspringt bei bereits kompakter DEFLATE-Ausgabe den zweiten, Lua-basierten RLE-Scan.

Im Sandbox-Benchmark mit 600×800-Testframes stieg die gemessene Rate von etwa 1.003 Frames/s (Bayer) auf 3.380 Frames/s (FFmpeg), ungefähr **3,4×** in diesem synthetischen Test. Das ist keine Messung des KOReader-Geräts; die reale Beschleunigung hängt von CPU, Auflösung, Quellvideo und Speicherkarte ab.

# v7.8.29 · 2026-10-09

# AppDock 7.8.29

## GStreamer-Ton bleibt aktiv

Der Audio-/Videosync wartete zuvor auf die exakte Meldung `New clock:`. Manche GStreamer-Builds melden stattdessen zuerst oder ausschließlich `Setting pipeline to PLAYING`; wenn keine der erwarteten Meldungen erkannt wurde, beendete der Acht-Sekunden-Timeout die Audio-Pipeline. Das konnte dazu führen, dass ein Video völlig ohne Ton lief.

AppDock akzeptiert nun beide üblichen Startmeldungen. Wenn ein Gerät gar keine bekannte Meldung in die Logdatei schreibt, startet das Video nach dem Timeout trotzdem, lässt den Audioprozess aber weiterlaufen — ein fehlendes Logsignal schaltet den Ton nicht mehr stumm. Regressionstests decken beide Bereitschaftsmeldungen und den nicht-stummschaltenden Timeout ab.

# v7.8.28 · 2026-10-09

# AppDock 7.8.28

## Synchronisierter Wiedergabestart

Beim GStreamer-Backend galt das Starten des Hintergrundprozesses bisher schon als Audio-Start. Die Videouhr lief dadurch an, während GStreamer den Audio-Sink noch initialisierte; auf Geräten mit langsamer Initialisierung konnte der Ton mehrere Sekunden hinter dem Bild beginnen.

AppDock wartet jetzt auf GStreamers Meldung `New clock:` und startet erst dann die Videouhr. Das Warten wird über kurze UI-Ticks ausgeführt, die Oberfläche blockiert also nicht. Wird innerhalb von acht Sekunden keine Wiedergabebereitschaft bestätigt oder meldet GStreamer einen Fehler, beendet AppDock den verspäteten Audioprozess statt ihn später asynchron einsetzen zu lassen. `aplay` und `tinyplay` behalten ihren direkten Startpfad.

Regressionstests prüfen, dass der Videostart während der Initialisierung eingefroren bleibt, bei bestätigter Audiouhr freigegeben wird und bei Timeout kein verspäteter Ton nachläuft.

# v7.8.27 · 2026-10-09

# AppDock 7.8.27

## Audio/Video-Wiedergabe korrigiert

- Der Player liest WAV-Dateien jetzt über ihre RIFF-Chunks statt einen festen 44-Byte-Header anzunehmen. So werden auch von FFmpeg erzeugte WAVs mit vorgeschalteten `LIST`-Metadaten korrekt erkannt; Seek-Clips beginnen am angeforderten Audio-Sample.
- Pause, Stop und Seek signalisieren jetzt die tatsächlich gestartete Audio-Backend-PID. Zuvor wurde teilweise eine nicht vorhandene Prozessgruppe signalisiert, sodass Audio nach Pause oder Sprung weiterlaufen und aus dem Takt geraten konnte.
- Kleine Laufzeitunterschiede zwischen Framezahl und Companion-WAV (bis 3 %) werden beim Wiedergabetakt berücksichtigt; bei deutlich abweichenden Tracks wird nicht automatisch gestreckt.
- Der Player findet die Companion-WAV auch bei einer großgeschriebenen `.BWR`-Endung.

## Komprimiertes BWR2-Videoformat

- Neue Konvertierungen schreiben weiterhin `.bwr`, aber nun **BWR2**: komprimierte Keyframes plus XOR-Deltas, Wiederholungsmarker und Null-Lauf-Kompression. Der Keyframe-Index begrenzt zufälliges Suchen standardmäßig auf höchstens 11 Delta-Decodierungen.
- **Bestehende BWR1-Videos bleiben in AppDock abspielbar.** Externe Player, die nur BWR1 unterstützen, verstehen BWR2 nicht.
- BWR2 nutzt System-zlib, wenn sie vorhanden ist, und fällt andernfalls auf eingebaute Codecs zurück. Neue zusätzliche ausführbare Werkzeuge sind nicht erforderlich.
- Sandbox-Messung auf synthetischem bewegtem 600×800-`testsrc2`, 36 Frames: 150.044 Byte statt 2.160.000 Byte roher Frame-Daten (93,1 % kleiner). Die tatsächliche Größe hängt stark vom Videoinhalt ab; dies ist kein allgemeines Kompressionsversprechen.
- Der Decoder liest und expandiert nur den benötigten Frame. Die Kompression verändert die Bildqualität oder das Dithering nicht.

## Prüfung

BWR1/BWR2-Roundtrips und Zufallszugriffe, Audio-Prozesssignale und WAV-Seeking hinter einem `LIST`-Chunk sowie der echte FFmpeg-Konvertierungs- und Player-Ladepfad werden durch Regressionstests abgedeckt.

Das detaillierte Containerlayout steht in [`BWR2_FORMAT.md`](BWR2_FORMAT.md).

# v7.8.26 · 2026-10-09

# AppDock 7.8.26

## YouTube-Progressbars werden während des Jobs neu gezeichnet

Der Setup-Fortschritt und die Fortschrittsanzeigen von Download und Videokonvertierung werden jetzt bei aktivem YouTube-Pane in gedrosselten Abständen durch einen partiellen Pane-Neuaufbau aktualisiert. Dabei werden aktueller Prozentwert, Phasenpuls und Statuszeile aus dem laufenden Jobzustand erneut gerendert. Ein manueller Screen-Refresh ist nicht mehr nötig. Die Aktualisierung wird nicht per Vollbild-Refresh und nicht bei jedem einzelnen Frame ausgelöst.

Beim Neuaufbau bleibt außerdem die aktuelle Position des indeterminierten Setup-Fortschritts erhalten, statt auf den Anfang zurückzuspringen.

## Verifikation

Regressionstests prüfen, dass Setup- und Videojobs einen partiellen Pane-Neuaufbau anfordern und dass dabei aktueller Status beziehungsweise Prozentwert erneut in die sichtbaren Widgets übernommen werden. Die vollständige lokale Regressionstestsuite und die Lua-Syntaxprüfung aller Plugin-Dateien liefen erfolgreich.

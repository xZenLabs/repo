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

# v8.5.9 · 2026-10-26

# AppDock 8.5.9 — Lesbare Game-Installationsfehler

Fehler beim Installieren eines Games erscheinen jetzt mit kurzer Überschrift und einem kompakten, stufenspezifischen Grund auf einer eigenen Zeile. Das verhindert, dass der lange, doppelte Dialogtext den entscheidenden Teil der Meldung abschneidet.

Die neue Meldung unterscheidet unter anderem ZIP-Auflistung, Integritätsprüfung, Entpacken nach `.adds`, fehlenden Launcher und fehlende Ausführungsrechte. Damit lässt sich der konkrete Gerätefehler beim nächsten Installationsversuch gezielt beheben.

# v8.5.8 · 2026-10-26

# AppDock 8.5.8 — Game-Paketinstallation auf KOReader-Geräten

Der Game-Installer unterstützt jetzt sowohl Info-ZIP als auch BusyBox `unzip`. Für die sichere Archivprüfung wird die portable Listenoption `-lq` statt der Info-ZIP-spezifischen Option `-Z1` verwendet; der Installer prüft außerdem, dass tatsächlich ZIP-Einträge gelesen wurden.

Nach dem Entpacken setzt AppDock den erwarteten Launcher unter `<game>/bin/<game>` auf ausführbar (`0755`). Damit werden beide Hürden abgedeckt: Archive ohne Unix-Ausführungsbits und Geräte, die nur BusyBox statt eines separaten `unzip` bereitstellen.

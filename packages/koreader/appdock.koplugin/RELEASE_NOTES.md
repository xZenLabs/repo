# v7.8.26 · 2026-10-09

# AppDock 7.8.26

## YouTube-Progressbars werden während des Jobs neu gezeichnet

Der Setup-Fortschritt und die Fortschrittsanzeigen von Download und Videokonvertierung werden jetzt bei aktivem YouTube-Pane in gedrosselten Abständen durch einen partiellen Pane-Neuaufbau aktualisiert. Dabei werden aktueller Prozentwert, Phasenpuls und Statuszeile aus dem laufenden Jobzustand erneut gerendert. Ein manueller Screen-Refresh ist nicht mehr nötig. Die Aktualisierung wird nicht per Vollbild-Refresh und nicht bei jedem einzelnen Frame ausgelöst.

Beim Neuaufbau bleibt außerdem die aktuelle Position des indeterminierten Setup-Fortschritts erhalten, statt auf den Anfang zurückzuspringen.

## Verifikation

Regressionstests prüfen, dass Setup- und Videojobs einen partiellen Pane-Neuaufbau anfordern und dass dabei aktueller Status beziehungsweise Prozentwert erneut in die sichtbaren Widgets übernommen werden. Die vollständige lokale Regressionstestsuite und die Lua-Syntaxprüfung aller Plugin-Dateien liefen erfolgreich.

# v7.8.25 · 2026-10-09

# AppDock 7.8.25

## YouTube-Player lädt das ausgewählte Video korrekt

Beim Starten der Wiedergabe lud AppDock die BWR1-Datei zunächst erfolgreich. Der anschließende Neuaufbau der DApp-Ansicht deaktivierte jedoch das bisherige Bibliothekspane, dessen Aufräumcode den gerade geladenen Player wieder stoppte. Deshalb zeigte der Player „No BWR1 file is loaded“ und sein Play-Knopf „No video is loaded“.

Die Bibliotheksansicht schließt den Player jetzt nicht mehr, wenn der Wechsel gerade in die Wiedergabe führt. Beim Verlassen der Player-Ansicht wird die Wiedergabe weiterhin ordnungsgemäß beendet.

## Verifikation

Die YouTube-Regression simuliert jetzt ausdrücklich die Deaktivierung der alten Bibliotheksansicht nach dem Laden eines gültigen BWR1-Videos. Der Player muss danach weiterhin einen geladenen Engine-Zustand besitzen. Die vollständige Regressionstestsuite und die Lua-Syntaxprüfung aller Plugin-Dateien liefen erfolgreich.

# v7.8.24 · 2026-10-09

# AppDock 7.8.24

## YouTube-Fortschritt aktualisiert sich live

Die Video-Fortschrittsleiste übernimmt während des Jobs jetzt die jeweils neu gemeldeten Prozentwerte. Beim erstmaligen Einrichten der Werkzeuge bewegt sich eine Ladeanzeige, solange die Installation keinen verlässlichen Gesamtfortschritt liefern kann. Fortschrittsänderungen verwenden E-Ink-schonende Teilaktualisierungen.

## Video-Konvertierung beschleunigt

Die Konvertierung war zuvor künstlich auf höchstens zwei Frames pro Sekunde begrenzt: Pro UI-Tick wurden zwei Frames gelesen, danach wartete der Job eine volle Sekunde. Beide Dither-Pfade – FFmpeg `monow` und AppDocks Bayer-Konverter – lesen jetzt bis zu sechs Frames pro kurzem Tick, begrenzt durch ein kleines CPU-Zeitbudget. So kann FFmpeg kontinuierlich ausgeben, statt durch den UI-Poller ausgebremst zu werden; die Oberfläche bleibt dabei responsiv. Die tatsächliche Geschwindigkeit hängt weiterhin vom Reader, Video-Codec und der gewählten Auflösung/Bildrate ab.

## Verifikation

Die vollständige lokale Regressionstestsuite lief erfolgreich. Der YouTube-Integrationstest prüft beide Dither-Pfade an einer erzeugten Videodatei, den kurzen Tick-Takt, die gebündelte Frame-Verarbeitung und die Fortschrittsaktualisierung. Die optionale externe BWR-Video-Fixture war in der lokalen Umgebung nicht vorhanden.

# v7.8.23 · 2026-10-09

# AppDock 7.8.23

## YouTube-Downloads korrigiert

Die YouTube-DApp verwendet jetzt ausdrücklich den Android-Player-Client von yt-dlp. Damit umgeht sie bei unterstützten Videos die zuletzt häufiger abgewiesenen Browser-Client-Streams. Die Einstellung betrifft Video-Downloads; Suche und lokale Konvertierung bleiben unverändert.

Bei Fehlern nennt die Fortschrittsansicht jetzt die erkannte Ursache – darunter Bot-/Anmeldeprüfungen, HTTP 403, fehlende kompatible Formate, PO-Token-Anforderungen und Netzwerkprobleme. Die yt-dlp-Ausgabe bleibt als Diagnose sichtbar. Anmelde- oder Bot-Prüfungen werden nicht umgangen.

## Verifikation

Die Lua-Syntax aller 26 Plugin-Dateien und die vollständige lokale Regressionstestsuite liefen erfolgreich. Der YouTube-Test deckt die Client-Auswahl und die verständlichen Fehlermeldungen ab. Die optionale externe BWR-Video-Fixture war in der lokalen Umgebung nicht vorhanden. Die Netzwerk-Reproduktion zeigte außerdem, dass YouTube je nach Sitzung die Anmeldung zur Bot-Prüfung verlangen kann; dies kann ein Clientwechsel nicht beheben.

# v7.8.22 · 2026-10-09

# AppDock 7.8.22

## Kobo-Entpackfehler behoben

Auf dem Kobo konnte `tar` den v7.8.21-Runtime-Tarball laden, aber nicht entpacken: das Dateisystem verweigerte das Anlegen von `python-runtime/etc/ssl/cert.pem` als Symlink (`Operation not permitted`).

Das ARMHF-Runtime-Archiv enthält jetzt Kopien der verlinkten Bibliotheken und Zertifikate statt Symlinks. Der Installer lädt dieses neue Asset und prüft dessen neue SHA-256-Prüfsumme. Es ist rund 17 MB groß und belegt entpackt etwa 44 MB.

## Verifikation

Das veröffentlichungsfertige Archiv enthält keine Symlinks oder Hardlinks. Frisch entpackt starteten CPython/yt-dlp unter ARM-QEMU; yt-dlp meldete Version 2026.08.19 und die YouTube-Suche lieferte acht Treffer. Ein Test auf dem physischen Kobo steht noch aus.

**Für betroffene Geräte:** AppDock zuerst auf 7.8.22 aktualisieren, KOReader neu starten und dann in der YouTube-App **Retry setup** wählen.

Asset: `appdock-youtube-armhf-musl-python-3.12.15.tar.gz`  
SHA-256: `5348e11472e5ca6c07d7b0ec75a2f1df1d181be7eb52d9e3cafb43267b1f916c`

# v7.8.47 · 2026-10-09

# AppDock 7.8.47

## Erste-Frame-Vorschauen

Videokarten verwenden jetzt den ersten bereits konvertierten Frame direkt aus der jeweiligen `.bwr`-Datei als Vorschau. Dadurch werden Thumbnails sofort lokal angezeigt, ohne Netzwerkdownload oder JPG-Cache.

Fehlt die BWR-Datei oder kann der erste Frame nicht gelesen werden, bleibt die robuste Play-Fläche als Fallback erhalten. Library-Navigation und Thumbnail-Sicherheit aus 7.8.46 bleiben enthalten.

# v7.8.45 · 2026-10-09

# AppDock 7.8.45

## Startverzögerung nach Audiostart

Die frei einstellbare Videoverzögerung wird jetzt nach erfolgreichem Audiostart für alle Audio-Backends angewendet. In 7.8.44 war der Pfad für aplay/tinyplay versehentlich innerhalb des GStreamer-Zweigs verschachtelt und wurde daher ignoriert.

GStreamer wartet weiterhin auf sein Startsignal und danach auf den eingestellten Offset. Andere Audio-Backends starten den Offset-Timer direkt nach erfolgreichem Audio-Start.

# v7.8.44 · 2026-10-09

# AppDock 7.8.44

## Library und Vorschaubilder

Die YouTube-Watch-Ansicht besitzt jetzt eine echte klickbare Library-Navigation. Sie öffnet eine eigene Liste der konvertierten Videos; jedes Video kann direkt aus der Library gestartet werden.

Suchergebnisse fragen außerdem die YouTube-Thumbnail-URL ab und laden das Bild asynchron in einen lokalen Cache. Konvertierte Videos verwenden ein passendes JPG neben der BWR-Datei. Falls ein Bild noch nicht geladen werden konnte, bleibt eine sichtbare Play-Fläche als Fallback erhalten.

# v7.8.43 · 2026-10-09

# AppDock 7.8.43

## Stabilität der Audio-/Video-Wiedergabe

Die fehlerhafte Frame-Lock-Wiedergabe aus 7.8.40 wird zurückgenommen. Sie koppelte den Videofortschritt an unregelmäßige UI-Ticks, während der Audioprozess unabhängig in Echtzeit lief. Dadurch konnte sich der Versatz während der Wiedergabe scheinbar zufällig ändern.

7.8.43 verwendet wieder die stabile Echtzeit-Zeitbasis des Players. Der frei einstellbare Offset aus 7.8.41 bleibt erhalten und gilt weiterhin für alle Audio-Backends.

# v7.8.42 · 2026-10-09

# AppDock 7.8.42

## YouTube-Watch-Ansicht in allen Orientierungen

Die alte AppDock-Listenansicht wird nicht mehr als Hochformat-Fallback verwendet. Die YouTube-DApp nutzt jetzt in Quer- und Hochformat dieselbe Watch-orientierte Struktur mit schwarzer YouTube-Navigation, Hauptvideo, Titel-/Aktionsbereich und Empfehlungsleiste.

Im Querformat wird die Empfehlungsleiste rechts neben dem Hauptvideo angezeigt. Im Hochformat wird sie unterhalb des Hauptvideos angeordnet. Die Kartenbreite der Empfehlungsleiste wird separat berechnet, damit sie nicht mehr über die gesamte Seite läuft.

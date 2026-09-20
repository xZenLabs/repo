# v6.6.2

# v6.6.0

# v6.5.13

# AppDock 6.5.13

## Korrektur

Die fünf DApps werden nicht mehr in AppDock gebündelt. Sie verbleiben ausschließlich im offiziellen Repository [arduinodude456/DApps](https://github.com/arduinodude456/DApps) und werden dort über den bestehenden AppStore-Katalog `dapps.txt` angeboten.

Der vorherige Bundle-Commit wurde vollständig zurückgenommen.

# v6.5.12

# AppDock 6.5.12

## Fünf integrierte DApps

AppDock bündelt jetzt fünf geprüfte, offline-first DApps aus dem Repository `arduinodude456/DApps`, damit eine neue Installation sofort mehr als die Kernwerkzeuge bietet und nicht zuerst den AppStore öffnen muss.

| App | Funktion |
|---|---|
| **Calc** | Wissenschaftlicher Taschenrechner und Funktionsplotter |
| **Calendar** | Lokaler Monatskalender mit Terminen |
| **Snake** | E-Ink-freundliches Snake-Spiel |
| **2048** | Lokales 2048-Kachelspiel |
| **Status Message** | Testet lokale AppDock-Benachrichtigungen |

Die Apps werden beim Start über einen sicheren, pluginrelativen Pfad geladen und nur dann registriert, wenn sie den erwarteten DApp-Vertrag mit `id`, `title` und `buildPane` erfüllen. Bestehende Store-Installationen und gespeicherte DApp-Zustände bleiben kompatibel.

# v6.5.11

# AppDock 6.5.11

## UI-Überarbeitung

AppDock erhält eine ruhigere Launcher-Hierarchie, die drei Einflüsse verbindet: die zurückhaltende, informationsorientierte ZenOS-Anmutung, die klare Lesbarkeit von SimpleUI und die pillen- und flächenbasierte Informationsstruktur von Android 12. Die Darstellung bleibt für E-Ink optimiert und verwendet weiterhin keine unnötigen Animationen, Unschärfen oder Transparenzeffekte.

Der normale Homescreen zeigt oberhalb des App-Rasters nun eine eindeutige App-Sektion mit der aktuell sichtbaren Anzahl. Dadurch werden Widgets, Suche und Launcher visuell klarer getrennt. Die bestehende Material-Palette, die großen Touch-Flächen und die E-Ink-freundlichen Abstände bleiben erhalten.

Die Änderung ist rein präsentational: App-Reihenfolge, Simple-Mode-Schutz, DApps, Widgets und bestehende Navigation bleiben kompatibel.

# v6.6.3 · 2026-10-04

# Hotfix: Open DApps on eInk devices now refreshes the screen
## Thx to "00nly1" (DChat Username) for the issue report :)

# v6.6.2 · 2026-09-20

# v6.6.0 · 2026-09-20

# v6.5.13 · 2026-09-14

# AppDock 6.5.13

## Korrektur

Die fünf DApps werden nicht mehr in AppDock gebündelt. Sie verbleiben ausschließlich im offiziellen Repository [arduinodude456/DApps](https://github.com/arduinodude456/DApps) und werden dort über den bestehenden AppStore-Katalog `dapps.txt` angeboten.

Der vorherige Bundle-Commit wurde vollständig zurückgenommen.

# v6.5.12 · 2026-09-14

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

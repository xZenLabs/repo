# v9.5.1 · 2026-11-14

# AppDock 9.5.1

## Deutsch

- **Night Mode ist jetzt AppDock-eigen.** Der Schalter ändert nur AppDocks gespeicherte Theme-Palette und löst kein KOReader-`ToggleNightMode`-Ereignis aus. KOReaders globale Bildschirminvertierung wird dadurch nicht eingeschaltet.
- Die dunkle Palette wird direkt gezeichnet; auf Graustufenlesern verwendet AppDock passende Helligkeitsrollen.
- Enthält außerdem das AppDock-Modul **Health & reading** für optionale Augenpflege, Lesestatistik, Lesepausen und Schlafenszeiterinnerungen.

## English

- **Night mode is now AppDock-local.** The switch updates AppDock's persisted theme palette and does not emit KOReader's `ToggleNightMode` event or enable KOReader's global screen inversion.
- The dark palette is rendered directly; grayscale readers use appropriate brightness roles.
- Also includes AppDock's **Health & reading** module for optional eye-care scheduling, reading statistics, break reminders, and bedtime reminders.

# v9.3.5 · 2026-11-12

UPPERCASE
lowercase
CamelCase

* This release fixed doom ctrlsrelease event timeout

# v9.3.4 · 2026-11-12

# AppDock 9.3.4

## Animation refresh fix

- Discards stale KOReader repaint and refresh queues before the first animation frame.
- Prevents the hidden pre-animation refresh that caused visible E-Ink flicker on the homescreen, dropdowns, and app views.
- Removes the redundant fast refresh when launching an app from the homescreen.
- Keeps the homescreen page transition's single full refresh after the animation completes.

# v9.3.3 · 2026-11-12

# AppDock 9.3.3 — Kein Vorab-Refresh beim Seitenwechsel

Dieses Patch-Release behebt den noch sichtbaren Refresh unmittelbar vor der Homescreen-Seitenanimation.

Das Animations-Overlay wird nun ohne eigenen Vorab-Refresh registriert. Der erste bewegte Frame wird direkt in den bereits sichtbaren Screen-Puffer gezeichnet und erst anschließend aktualisiert. Dadurch beginnt die Animation ohne statischen Zwischenframe.

Nach dem Seitenwechsel wird das Overlay ohne zusätzlichen Zwischenrefresh entfernt. Erst danach wird genau einmal ein Full-Refresh ausgeführt, um E-Ink-Ghosting zu beseitigen.

Auch das Quick-Settings-Dropdown verwendet beim Schließen keinen zusätzlichen Overlay-Refresh vor dem abschließenden UI-Refresh.

# v9.3.2 · 2026-11-12

# AppDock 9.3.2 — Animationsstart und Dropdown-Abschluss

Dieses Patch-Release behebt verbleibendes Flackern beim Homescreen-Seitenwechsel und im Quick-Settings-Dropdown.

Der Animationsrunner startet nun direkt mit dem ersten bewegten Frame statt zunächst einen statischen `t=0`-Frame zu zeichnen. Dadurch entsteht vor dem Homescreen-Seitenwechsel kein zusätzlicher sichtbarer Refresh.

Das Quick-Settings-Dropdown startet ebenfalls ohne statischen Vorab-Frame. Beim Wegfahren werden Dropdown und Animationsebene zuerst vollständig entfernt; anschließend wird genau einmal ein normaler UI-Refresh für die darunterliegende Seite ausgeführt, um Ghosting sauber zu entfernen.

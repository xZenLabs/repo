# v9.5.2 · 2026-11-15

# AppDock 9.5.2

## Deutsch

- **Neue Navigationsleiste in Apps.** Wie bei Android: **Zurück**, **Home** und **Offene Apps**, jeweils ein Drittel der vollen Breite. Zurück verlässt zuerst den Vollbildmodus, lässt sonst die App eine Unterseite schließen (`onBack`) und schließt andernfalls die App.
- **Optionale Wischgesten** unter *Einstellungen → Anzeige → Gestennavigation*: vom linken oder rechten Bildschirmrand wischen = Zurück, unten schnell nach oben wischen = Home, unten langsam nach oben wischen = Offene Apps. Die Buttons werden dann durch eine schmale Leiste ersetzt.
- Der Neuigkeiten-Dialog weist auf die neue Navigation hin.

## English

- **New navigation bar inside apps.** Android-style **Back**, **Home** and **Open apps**, each spanning a third of the full width. Back first leaves fullscreen, then lets the app close a sub page (`onBack`), otherwise closes the app.
- **Optional swipe gestures** under *Settings → Display → Gesture navigation*: swipe from the left or right screen edge = Back, fast swipe up from the bottom = Home, slow swipe up from the bottom = Open apps. The buttons are then replaced by a slim bar.
- The What's new dialog points out the new navigation.

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

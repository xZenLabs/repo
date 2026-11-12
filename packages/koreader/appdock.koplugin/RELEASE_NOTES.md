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

# v9.3.1 · 2026-11-12

# AppDock 9.3.1 — Flackerfreie Animationen

Dieses Patch-Release entfernt die zusätzlichen Full-/Partial-Refreshes vor und nach den UI-Animationen.

- Homescreen-Seitenwechsel übergeben jetzt regional mit `fast` an die echte UI.
- Quick Settings und Recently-used/Open Apps verwenden beim Ein- und Ausblenden keine zusätzlichen `partial`- oder normalen UI-Refreshes mehr.
- Die kurzen Schalteranimationen in Quick Settings lösen keinen abschließenden Full-Refresh mehr aus.
- Die Animationsebene bleibt beim Übergang auf die echte UI im regionalen Fast-Refresh-Pfad, wodurch das sichtbare Flackern auf E-Ink-Geräten entfällt.

# v9.3.0 · 2026-11-12

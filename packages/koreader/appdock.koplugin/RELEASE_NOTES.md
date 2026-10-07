# v7.8.10 · 2026-10-07

# AppDock 7.8.10

## Deutsch

### Helligkeit und Bildschirmschoner

- Die Blättertasten ändern die Helligkeit jetzt in **10er-Schritten** statt in Einerschritten.
- Beim Start des animierten Bildschirmschoners wird die Frontlight-Helligkeit vollständig ausgeschaltet.
- Beim Beenden des Bildschirmschoners wird die vorherige Helligkeit automatisch wiederhergestellt.
- Die Wiederherstellung ist defensiv abgesichert und verändert das Verhalten auf Geräten ohne verfügbare Frontlight-Steuerung nicht.

### Qualitätssicherung

- Lua-Syntax aller Plugin-Dateien geprüft.
- Keyboard-, AppStore-, Browser-, DApp-, Ordering- und Setup-Assistant-Regressionstests erfolgreich ausgeführt.

## English

### Brightness and screensaver

- Page keys now change brightness in **10-step increments** instead of single steps.
- The frontlight is fully switched off when the animated screensaver starts.
- The previous brightness is restored automatically when the screensaver closes.
- Restoration is guarded defensively and does not change behavior on devices without frontlight control.

### Quality assurance

- Lua syntax checked for all plugin files.
- Keyboard, AppStore, Browser, DApp, ordering, and setup-assistant regression tests pass.

# v7.8.9 · 2026-10-07

# AppDock 7.8.9

## Deutsch

### Bildschirmschoner speicherschonend gemacht

Die Bildschirmschoner-Frames waren komprimiert jeweils ungefähr 1,6 MB groß, benötigten beim Dekodieren jedoch etwa 13,5 MB Speicher pro Bild. Beim Animieren mehrerer Frames konnte KOReader deshalb mit `not enough storage` abbrechen.

Die vier Frames wurden auf 816 × 1088 Pixel und 8-Bit-Graustufen optimiert. Der dekodierte Speicherbedarf sinkt dadurch auf unter 1 MB pro Frame. Zusätzlich werden animierte Frames nicht mehr im globalen `ImageWidget`-Cache gesammelt, und sie werden direkt in der benötigten Zielgröße geladen.

### Qualitätssicherung

- Lua-Syntax aller Plugin-Dateien geprüft.
- Keyboard-, AppStore-, Browser-, DApp-, Ordering- und Setup-Assistant-Regressionstests erfolgreich ausgeführt.
- Screensaver-Frames von insgesamt etwa 6,5 MB auf unter 1 MB komprimierte Asset-Größe reduziert.

## English

### Screensaver memory usage reduced

The screensaver frames were only about 1.6 MB each when compressed, but required approximately 13.5 MB of memory per image when decoded. Animating multiple frames could therefore make KOReader fail with `not enough storage`.

All four frames are now optimized to 816 × 1088 pixels and 8-bit grayscale. Decoded memory usage is reduced to under 1 MB per frame. Animated frames are also excluded from the global `ImageWidget` cache and loaded directly at the required target size.

### Quality assurance

- Lua syntax checked for all plugin files.
- Keyboard, AppStore, Browser, DApp, ordering, and setup-assistant regression tests pass.
- Screensaver frames reduced from approximately 6.5 MB to under 1 MB of compressed assets in total.

# v7.8.8 · 2026-10-07

# AppDock 7.8.8

## Deutsch

### Framebuffer-Crash endgültig behoben

Der vollständige Stacktrace zeigte die konkrete Ursache in `framecontainer.lua:55`: Der schwarze Füllbalken des Helligkeitsindikators war ein `FrameContainer` ohne Kind. KOReader rief deshalb `self[1]:getSize()` auf einem leeren Container auf.

Der Füllbalken besitzt jetzt ein echtes `HorizontalSpan`-Kind. Damit ist der Container gültig und der Fehler `attempt to index a nil value` beim Drücken der Blättertasten beseitigt.

### Qualitätssicherung

- Lua-Syntax aller Plugin-Dateien geprüft.
- Keyboard-, AppStore-, Browser-, DApp-, Ordering- und Setup-Assistant-Regressionstests erfolgreich ausgeführt.

## English

### Framebuffer crash definitively fixed

The complete stack trace identified the exact cause at `framecontainer.lua:55`: the black fill bar of the brightness indicator was a `FrameContainer` without a child. KOReader therefore called `self[1]:getSize()` on an empty container.

The fill bar now has a real `HorizontalSpan` child. The container is valid and the `attempt to index a nil value` error when pressing page keys is fixed.

### Quality assurance

- Lua syntax checked for all plugin files.
- Keyboard, AppStore, Browser, DApp, ordering, and setup-assistant regression tests pass.

# v7.8.7 · 2026-10-07

# AppDock 7.8.7

## Deutsch

### Helligkeitsanzeige stabilisiert

- Der Helligkeitsindikator verwendet jetzt einen direkten, garantiert nicht-leeren `FrameContainer` mit einem direkten `VerticalGroup`-Kind.
- Die unnötige Verschachtelung aus `WidgetContainer`, `CenterContainer` und zusätzlichem `FrameContainer` wurde entfernt.
- Dadurch wird der fragile Paint-Pfad beseitigt, der auf manchen Geräten weiterhin den Fehler `framebuffer.lua: attempt to index a nil value` auslösen konnte.
- Die seitliche Prozent- und Balkenanzeige bleibt erhalten.

### Qualitätssicherung

- Lua-Syntax aller Plugin-Dateien geprüft.
- Keyboard-, AppStore-, Browser-, DApp-, Ordering- und Setup-Assistant-Regressionstests erfolgreich ausgeführt.

## English

### Brightness indicator stabilized

- The brightness indicator now uses a direct, guaranteed non-empty `FrameContainer` with a direct `VerticalGroup` child.
- The unnecessary `WidgetContainer` → `CenterContainer` → `FrameContainer` nesting has been removed.
- This removes the fragile paint path that could still trigger `framebuffer.lua: attempt to index a nil value` on some devices.
- The side percentage and bar indicator remain available.

### Quality assurance

- Lua syntax checked for all plugin files.
- Keyboard, AppStore, Browser, DApp, ordering, and setup-assistant regression tests pass.

# v7.8.6 · 2026-10-07

# AppDock 7.8.6

## Deutsch

### Blättertasten und Framebuffer-Stabilität

- Die Helligkeitsanzeige wird nach einem Blättertasten-Ereignis erst im nächsten KOReader-UI-Zyklus aufgebaut.
- Dadurch wird ein Race Condition zwischen physischer Tastaturverarbeitung und Framebuffer-Neuzeichnung vermieden, die auf manchen Geräten den Fehler `framebuffer.lua: attempt to index a nil value` auslösen konnte.
- Der native Helligkeitswechsel bleibt erhalten; ein temporär nicht verfügbarer Framebuffer kann die Tastaturaktion nicht mehr zum Absturz bringen.
- Aufbau und Ausblenden der Anzeige sind zusätzlich defensiv abgesichert.

### Qualitätssicherung

- Lua-Syntax aller Plugin-Dateien geprüft.
- Keyboard-, AppStore-, Browser-, DApp-, Ordering- und Setup-Assistant-Regressionstests erfolgreich ausgeführt.

## English

### Page keys and framebuffer stability

- The brightness indicator is now rebuilt in the next KOReader UI cycle after a page-key event.
- This avoids a race between physical-key processing and framebuffer repainting that could cause `framebuffer.lua: attempt to index a nil value` on some devices.
- Native brightness changes remain available; a temporarily unavailable framebuffer can no longer crash the key action.
- Showing and hiding the indicator are additionally guarded defensively.

### Quality assurance

- Lua syntax checked for all plugin files.
- Keyboard, AppStore, Browser, DApp, ordering, and setup-assistant regression tests pass.

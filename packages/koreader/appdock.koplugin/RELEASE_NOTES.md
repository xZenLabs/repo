# v9.12.0 · 2026-11-20

# AppDock 9.12.0
## DockAI-Sicherheit
- DockAI nutzt den dchat-Supabase-Proxy; Groq-API-Keys werden serverseitig gespeichert und nicht an AppDock zurückgegeben.
- Tageslimit 25 und Wochenlimit 100 werden serverseitig pro TBS-Geräte-ID atomar erzwungen; zurückgewiesene/fehlgeschlagene Provider-Anfragen werden wieder freigegeben.
- Admin kann in AppDock API-Keys hinzufügen. Anzeigen, Löschen, Dateiimport und lokale Limitänderungen wurden entfernt.
- DockAI benötigt ein angemeldetes TBS-Konto. Zähler setzen um Mitternacht UTC bzw. Montag UTC zurück.
- Admin-Passwortprüfung erfolgt auf dem Server; das frühere im Plugin enthaltene Passwort wurde aus dem Client entfernt.

# v9.8.2 · 2026-11-17

# AppDock 9.8.2

## Deutsch
- **Fix:** Behebt einen Homescreen-Startabsturz auf Farbgeräten. Ein KOReader-FFI-Farbobjekt wird nicht mehr mit `nil` verglichen.

## English
- **Fix:** Fixes a homescreen startup crash on color devices by avoiding comparison of a KOReader FFI color object with `nil`.

# v9.8.1 · 2026-11-17

# AppDock 9.8.1

## Deutsch
- **Fix:** Die Kategorie „Lockscreen“ wird jetzt tatsächlich in der Settings-Sidebar angezeigt. Entsperrmethode, Profilname, Profilbild und Uhrzeit-Stil sind dadurch erreichbar.

## English
- **Fix:** The “Lockscreen” category is now included in the Settings sidebar, making unlock method, profile name, profile image and clock style accessible.

# v9.8.0 · 2026-11-17

# AppDock 9.8.0

## Deutsch
- **Themes mit Verlaufsfarben pro Rolle:** Neben dem Hintergrund-Verlauf kann ein Theme jetzt auch für Primär-, Button-, Sekundär-, Tertiär-, Flächen- und Variantenfarben einen Verlauf festlegen (`gradients = { button = ... }`). Aurora nutzt das für Buttons, Kacheln und Chips. Die Textfarbe wird gegen jeden Verlaufsstopp geprüft; auf Graustufen-Displays und im hohen Kontrast bleibt es bei flachen Farben.
- **Neue Einstellungs-Kategorie „Lockscreen“:** enthält Entsperrmethode, Name, Profilbild und neu den **Uhrzeit-Stil**: Standard, Liquid Glass oder Bunt (Stunden und Minuten groß in 2 Zeilen, jede Ziffer in eigener Farbe).

## English
- **Per-role gradients in themes:** besides the background gradient, a theme can now define a gradient for the primary, button, secondary, tertiary, surface and surface-variant colors (`gradients = { button = ... }`). Aurora uses it for buttons, tiles and chips. Text contrast is checked against every gradient stop; grayscale panels and high contrast keep flat colors.
- **New settings category "Lockscreen":** unlock method, name, profile image and the new **clock style**: Standard, Liquid Glass or Color (hours and minutes big on 2 lines, one color per digit).

# v9.7.1 · 2026-11-16

# Fixes:
- bookshelf now opens in DReader
- book titles in Bookshelf fixed

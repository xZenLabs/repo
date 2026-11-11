# v9.2.1 · 2026-11-11

The open Apps screen was reworked to look amazing

# v9.2.0 · 2026-11-11

# v9.1.5 · 2026-11-11

AppDock 9.1.5 verwendet für Quick Settings denselben abgesicherten Frosted-Veil-Mechanismus wie die AppDock-eigenen Dialoge: Alpha-Blending, kurzlebiges addblitFrom-Overlay und sicherer Graustufen-Fallback ohne persistenten Backdrop-Puffer.

# v9.1.4 · 2026-11-11

AppDock 9.1.4 behebt den tatsächlichen Quick-Settings-Absturz: Der native ColorRGB32-Cache wird nicht mehr mit nil verglichen und löst damit den fehlerhaften Geräte-__eq-Operator nicht mehr aus.

# v9.1.3 · 2026-11-11

AppDock 9.1.3 entfernt den nativen Backdrop-Puffer aus Quick Settings. Damit wird der native pthread_mutex-Absturz durch einen bereits zerstörten Blitbuffer-Mutex vermieden; Glass-Kacheln und Slider bleiben erhalten.

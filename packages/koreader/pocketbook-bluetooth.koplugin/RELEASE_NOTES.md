# 0.0.5 · 2026-11-01

A big reliability release for PocketBook, tested on beta.

- **Faster backend:** a new "Fast (D-Bus)" mode alongside "Compatible" (`bluetoothctl`). Automatic, the default, picks D-Bus and falls back when needed.
- **Pairing a phone works** now that an agent stays up for the whole pairing.
- **Wake and start-up:** the radio comes back as it was (on a cold start, and on wake only if it was on at suspend) and last-connected devices reconnect. Bluetooth is never switched on by itself.
- **Held devices:** disconnecting a device by hand keeps it off on wake until you connect it again. Blocked devices show as blocked.
- **Menu:** shows saved devices while Bluetooth is off, keeps your page during a scan, ignores taps while the radio is switching, and has shorter confirmations. Live updates while the menu is open are experimental and off by default.
- **Robustness:** reads time out (including on older BusyBox), failed reads never wipe the saved list, and the device cache keeps only paired devices.
- **Logging:** state changes and timings are logged, with MAC addresses masked.

# 0.0.4 · 2026-10-13

OTA updates now work, with Stable, Beta and Development channels.

If you're on 0.0.3 or older, install this release by hand once (replace the bluetooth.koplugin folder in koreader/plugins); later updates arrive over OTA.

# 0.0.3 · 2026-07-07

The internal updater is still a work in progress, so be mindful you might miss future updates in the meantime.. Leave the repo a star if nothing else to keep in touch with it otherwise

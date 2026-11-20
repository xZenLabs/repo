# 0.0.6-dev.4 · 2026-11-20

**Kindle: Set up remotes from the plugin** (Settings → Set up remotes…)

Kindle only pairs headphones on its own. This adds the one-time setup that lets remotes, keyboards and controllers pair, which used to need SSH.

- Explains the risks first, with a checklist of what to back up. Older models known to white-screen (Oasis 1, Paperwhite 3 and earlier) get a second warning. Other models can try.
- Every changed file is backed up to `koreader/settings/bluetooth_kindle_setup/`, the system partition is always locked again, and a failed step rolls back.
- **Undo remote setup…** restores the originals.
- **Untested on a Kindle so far.** Please report success or failure in an issue, with the model and firmware the setup screen shows.

Also in this build (same as 0.0.6-beta.1): Turn off if none reconnect, and notification settings with Silent mode.

# 0.0.6-beta.1 · 2026-11-20

First beta of 0.0.6: everything since 0.0.5.

**New**
- Button binding: bind a remote's buttons to any KOReader action (Settings → Buttons).
- Dispatcher actions: Bluetooth on, off and toggle, for gestures and profiles.
- Turn off if none reconnect (optional): after a wake or start-up, Bluetooth turns off when no starred or last-connected device reconnects within 15 s. It tries again on the next wake.
- Notifications: Silent mode and per-kind switches for confirmation pop-ups. Errors always show.
- Kindle backend (tested on Paperwhite 5 and 6). Remotes need a one-time setup: see "Kindle" in the README.
- Kobo backend for MTK models. **Untested on a real Kobo**: please report how it goes in an issue.
- Pair by address, and menus hide what the device can't do.

**Fixes**
- Bindings re-applied after a view change; Cancel goes back a step in the bind flows.
- Several Kobo, Kindle and menu fixes from review.

# 0.0.6-dev.3 · 2026-11-18

- New Dispatcher actions: **Toggle Bluetooth**, **Turn on Bluetooth** and **Turn off Bluetooth** (Device section). Bind them to gestures or profiles, or add them to quick-action menus such as SimpleUI's. Closes #14.

# 0.0.6-dev.2 · 2026-11-03

Fixes
- Button bindings now work straight after switching between the file browser and a book, without opening the Bluetooth menu first (they apply once the new view has read its devices).
- Binding and editing buttons: Cancel no longer closes the whole menu. Each step has « Back to the previous one, and the first step's Cancel returns to the Buttons menu. The binding lists stay open and update after a change or removal.

# 0.0.6-dev.1 · 2026-11-01

Work held back during the 0.0.5 freeze, now on the development channel.

- **Button binding:** bind keys on a Bluetooth remote or keyboard to reader actions from the menu.
- **Kindle backend (untested):** uses lipc, adds "Pair by address…" and a setup pop-up. See the README's Kindle section; root setup is manual.
- **Kobo MTK backend (untested):** built on the D-Bus code, with a fallback to `bluetoothctl`.
- **Multi-device groundwork:** a shared backend contract, capability checks, and a menu that hides features a backend can't do.
- **Smaller fixes:** device info skips Trusted/Blocked where unsupported and skips reads for devices paired by address.

Kobo and Kindle testers wanted. PocketBook remains the tested platform.

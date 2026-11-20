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

# 0.0.5-beta.5 · 2026-10-27

Everything from 0.0.5-dev.10 and 0.0.5-dev.11 since beta.4.

New
- Fast mode (D-Bus) for device reads and actions, next to Compatible (bluetoothctl). Automatic is the default and picks for you. Live updates are opt-in.
- Phones pair: the pairing session now answers the phone's request.
- Blocked devices show in the menu with how to unblock them.

Fixes
- Extra taps on the Bluetooth switch are ignored only while your own switch is under way; wake, connect and suspend no longer swallow a tap.
- One pairing session at a time, and a sleep during pairing no longer abandons it.
- The scan screen says why a pairing didn't start (another pairing running, or an invalid address).
- Pairing ends straight away on "not available" or no controller, instead of after about 20 s.
- Works with BusyBox builds whose grep lacks -E.
- Clearer logs around wake reconnects.

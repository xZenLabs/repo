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

# 0.0.5-dev.11 · 2026-10-27

Fixes from the independent review of dev.10.

- The Bluetooth switch ignores extra taps only while your own switch is under way; wake, connect and suspend no longer swallow a tap.
- Pairing: one session at a time, guarded so an old session can't unlock a newer one, and a sleep during pairing no longer abandons the session.
- The scan screen says why a pairing didn't start (another pairing running, or an invalid address).
- Pairing ends straight away on "not available" or no controller, instead of after about 20 s.
- Works with BusyBox builds whose grep lacks -E.
- A WARN is logged again when a tap during wake skips the reconnect.
- Stronger pairing tests.

# 0.0.5-dev.10 · 2026-10-26

## Changes since 0.0.5-dev.9

**New: Fast mode (D-Bus).** On PocketBook, Bluetooth now talks to BlueZ over D-Bus by default (Settings → Backend → Automatic). Reads take about 0.1 s instead of 0.4 s, and connect, disconnect, trust, block and unpair go over D-Bus too. If D-Bus doesn't work on a device, the plugin falls back to Compatible (bluetoothctl) by itself. You can pick a mode by hand under Backend.

**New: Live updates (experimental, off by default).** Settings → Live updates. While the Bluetooth menu is open in Fast mode, it updates as soon as a device changes instead of every 3 seconds.

**Fixes and changes**
- Bluetooth restores its last state at start-up (from beta.3).
- Disconnecting a device by hand keeps it off until you connect it again (from beta.4).
- Phones now pair. The pairing session keeps an agent running, so the phone's prompt can be answered: tap Pair on the phone.
- Blocked devices show "(blocked)" and are no longer ticked as connected. Tapping one explains how to unblock it.
- Unpair is confirmed properly in Fast mode.

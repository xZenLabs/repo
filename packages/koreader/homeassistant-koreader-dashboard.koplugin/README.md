```text
 .--------------.
 |  \ | /       |    _                         _             _
 | -- O --  /\  |   | |_   ___  _ __   ___  __| | __ _  ___ | |_
 |  / | \  /  \ |   | ' \ / _ \| '  \ / -_)/ _` |/ _` |(_-< | ' \
 |         |[]| |   |_||_|\___/|_|_|_|\___|\__,_|\__,_|/__/ |_||_|
 '--------------'
```

**Turn an old jailbroken Kindle into a calm e-ink Home Assistant dashboard.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![KOReader plugin](https://img.shields.io/badge/KOReader-plugin-orange.svg)](https://koreader.rocks)
[![Home Assistant](https://img.shields.io/badge/Home%20Assistant-REST%20API-41BDF5.svg)](https://www.home-assistant.io)

`homedash.koplugin` is a [KOReader](https://koreader.rocks) plugin that opens a full-screen Home
Assistant dashboard: current weather, an hourly forecast chart with night shading, a daily forecast,
a few sensor values and big buttons that call Home Assistant services (open the garage, open the
gate). It is built for e-ink: black and white, slow refresh, touch only, no animations.

<p align="center">
  <img src="docs/images/kindle-touch-photo.jpg" alt="homedash running on a Kindle Touch (2011) with live Home Assistant data" width="380">
  &nbsp;
  <img src="docs/images/dashboard-en.png" alt="homedash dashboard on a 600x800 Kindle screen" width="360">
</p>
<p align="center"><sub>Left: a 2011 Kindle Touch running KOReader with live data. Right: emulator render at the same 600x800.</sub></p>

| Action: garage opened | Paperwhite resolution (1072x1448) | Polish UI (`lang = "pl"`) |
| --- | --- | --- |
| <img src="docs/images/dashboard-en-garage-open.png" alt="Garage button after opening" width="260"> | <img src="docs/images/dashboard-en-paperwhite.png" alt="1072x1448 screenshot" width="260"> | <img src="docs/images/dashboard-pl.png" alt="Polish interface" width="260"> |

The screenshots are real renders from the KOReader emulator against the bundled mock server (see
[docs/development.md](docs/development.md)), not mock-ups.

## Features

- Current conditions: weather icon, temperature (optionally from a separate sensor), humidity, wind with
  direction, pressure.
- Hourly chart: temperature line with labels, precipitation bars, night shading, sunrise and sunset
  captions (from `sun.sun`).
- Daily forecast rows with high, low, a computed "feels like" (wind chill or heat index), and precipitation.
- Values grid: any entity or attribute, with units and state-to-text maps.
- Buttons that call any Home Assistant service, with an optional confirmation dialog, a live state
  caption, a state-dependent icon, and state-dependent actions (for example "close" when open, "open"
  when closed).
- Status line with the last update or the last error, battery and Wi-Fi in the header.
- Refreshes itself every few minutes, with a periodic full e-ink flash to clear ghosting, and refreshes
  once after the device wakes up.
- Built-in English and Polish; every UI string can be overridden in the config.
- Errors never crash it: a missing or broken config, an unreachable Home Assistant or a bad token are
  shown on screen, and the last good data stays visible.

## Supported devices

Any touch device that runs KOReader. It was tested

- in the KOReader emulator at 600x800 @ 167 dpi, 758x1024 @ 212 dpi and 1072x1448 @ 300 dpi, and
- on a Kindle Touch (firmware 5.3.7.3).

All sizes scale with the screen. Non-touch Kindles (keyboard or D-pad only) are not supported: the
dashboard is operated by tapping buttons.

## Requirements

- [KOReader](https://koreader.rocks) installed on the device (for a Kindle: jailbroken, plus KUAL or
  the KOReader package).
- Home Assistant reachable from the device over the local network. HTTP on the LAN is fine.
  Use the **IP address** in the URL: `homeassistant.local` (mDNS) usually does not resolve on a Kindle.
  Give the Home Assistant host a DHCP reservation.
- A long-lived access token. Create it for a **dedicated non-admin user** that is allowed to log in
  **only from the local network** (Settings > People > Users; see [Security notes](#security-notes)).

## Installation

1. Download the latest **[homedash.koplugin.zip](https://github.com/wroblisko/homeassistant-koreader-dashboard/releases/latest/download/homedash.koplugin.zip)**
   (all versions: [releases page](https://github.com/wroblisko/homeassistant-koreader-dashboard/releases)) and unzip it
   into `koreader/plugins/` on the device (on a Kindle: `/mnt/us/koreader/plugins/`); the zip contains the
   `homedash.koplugin` folder. Alternatives:
   - a plugin store on the device: [appstore.koplugin](https://github.com/omer-faruq/appstore.koplugin) /
     [KoStore](https://github.com/ThePixelPro366/KoStore) find it via the `koreader-plugin` GitHub topic, and
     [updatesmanager.koplugin](https://github.com/advokatb/updatesmanager.koplugin) can keep it updated from releases;
   - over Wi-Fi with `scripts/deploy.sh` ([docs/development.md](docs/development.md#deploying-to-a-device-over-ssh));
   - build the zip yourself with `bash scripts/package.sh`.

   Updating: replace the `homedash.koplugin` folder the same way and restart KOReader. Your config and token
   in `koreader/settings/` are not touched.
2. Copy `homedash.koplugin/config.example.lua` to `koreader/settings/homedash_config.lua`
   (`/mnt/us/koreader/settings/homedash_config.lua`) and edit the URL, the entity ids and the buttons.
3. Put the token in a file, one line, for example `/mnt/us/koreader/settings/homedash.token`
   (the example config reads it from there, so the config itself contains no secret).
4. Restart KOReader.
5. Open it from the Tools menu: **Tools > More tools > Home Assistant dashboard**. To open it with a tap or a gesture: Settings > Taps and gestures > Gesture manager,
   pick a gesture, then General > Home Assistant dashboard.

If the config is missing or has an error, the dashboard says so on screen and shows the exact path
it expects. Swipe down or tap **Close** to leave; **Refresh** fetches everything now.

## Configuration

`homedash_config.lua` is a Lua file that returns one table: the Home Assistant connection, refresh
timing, locale, and a list of `sections` that make up the card. The commented
[`config.example.lua`](homedash.koplugin/config.example.lua) is the quickest reference;
[docs/configuration.md](docs/configuration.md) lists every key.

```lua
return {
    ha = { url = "http://192.168.1.10:8123", token = "..." },
    locale = { lang = "en" },
    sections = {
        { type = "header", title = "Home" },
        { type = "weather_now", weather = "weather.home" },
        { type = "chart", weather = "weather.home", sun = "sun.sun" },
        { type = "buttons", items = {
            { id = "gate", label = "Gate", icon = "gate",
              action = { service = "switch.turn_on", data = { entity_id = "switch.driveway_gate" },
                         confirm = "Open the gate?" } },
        }},
        { type = "footer" },
    },
}
```

## How it works

The plugin draws everything itself with KOReader's drawing primitives (no web view, no browser). Data
comes from the Home Assistant REST API:

- `GET /api/states/<entity_id>` for every entity the card shows (including `sun.sun`),
- `POST /api/services/weather/get_forecasts?return_response` for the hourly and daily forecasts,
- `POST /api/services/<domain>/<service>` when you tap a button.

"Feels like" is computed on the device from temperature, wind and humidity (wind chill, heat index)
unless the weather entity provides an apparent temperature. Night shading uses the next sunrise and
sunset of `sun.sun`. Requests are blocking with short timeouts, and after the first network error the
rest of that refresh is skipped, so an unreachable Home Assistant costs one timeout, not one per entity.
Details and real response samples: [docs/ha-api.md](docs/ha-api.md).

## Security notes

- The token lives on the device (in `koreader/settings`, readable by anyone who can read the Kindle's
  storage, over USB or over KOReader's SSH server). Treat the device as holding that secret.
- **Any Home Assistant user can call any service**; Home Assistant has no per-token service scopes.
  Whoever gets the token can do everything the user is allowed to. That is why the token should belong
  to a dedicated **non-admin** user that can **only log in from the local network**, and why the example
  buttons use `confirm`.
- Do not put the token in a config you share, paste into an issue or commit. Keep it in a separate file
  (`*.token` is git-ignored here).
- Plain HTTP on the LAN sends the token unencrypted on your network. Use HTTPS if your Home Assistant
  offers it on the LAN.

See [SECURITY.md](SECURITY.md) to report a vulnerability.

## Power and keep-alive

KOReader suspends the device after a while, and then neither the clock nor the data refresh runs. For a
wall-mounted dashboard:

- Keep the device on a charger.
- Use KOReader's **Keep alive** plugin (Tools > More tools > Keep alive, then "Stay alive"; it keeps
  the Kindle from sleeping and costs battery, hence the charger) or lengthen the auto-suspend timeout.
- Set the screensaver to **Leave screen as-is** (Settings > Screen > Sleep screen), so the dashboard
  stays visible while suspended. The plugin refreshes everything about three seconds after the device
  wakes up.

## Development

Building the KOReader emulator, the mock Home Assistant, headless screenshots, unit tests and the
architecture: [docs/development.md](docs/development.md). Guidance for AI coding tools:
[AGENTS.md](AGENTS.md) / [CLAUDE.md](CLAUDE.md).

## Contributing

Issues and pull requests are welcome; see [CONTRIBUTING.md](CONTRIBUTING.md). Release notes are in
[CHANGELOG.md](CHANGELOG.md).

## License

[MIT](LICENSE) (c) 2026 homedash contributors. The garage and gate drawings in `homedash.koplugin/icons/` are
original line art for this plugin and covered by the same license.

## Acknowledgements

- [KOReader](https://github.com/koreader/koreader) (AGPL-3.0), the platform this plugin runs on.
- [Weather Icons](https://erikflowers.github.io/weather-icons/) by Erik Flowers (SIL Open Font
  License 1.1) and [Font Awesome 4](https://fontawesome.com/v4/) (battery, Wi-Fi and other glyphs). Both
  ship inside KOReader's `fonts/nerdfonts/symbols.ttf`; the plugin only draws glyphs from that font and
  does not bundle it.
- [Home Assistant](https://www.home-assistant.io) and the [met.no](https://www.met.no) weather data it
  serves (the sample fixtures were captured from a met.no weather entity).

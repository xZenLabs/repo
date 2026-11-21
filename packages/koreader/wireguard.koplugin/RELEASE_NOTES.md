# v1.0.5 · 2026-11-21

Hostname endpoints work on Kobo

An Endpoint given as a hostname was never routed outside the tunnel on
Kobo, because the plugin looked the name up with getent and Kobo does not
have it. With a full tunnel the encrypted traffic was then sent into the
tunnel itself. The plugin now uses the address wg already resolved, so no
extra lookup tool is needed.

Failed commands are now reported. Under KOReader's LuaJIT every command
looked like it had succeeded, so for example an endpoint that could not be
resolved still ended in "WireGuard connected" with no peer on the
interface. Connecting now stops and shows what went wrong.

## Other fixes

- /etc/resolv.conf is put back reliably on disconnect. On some Kindles the
  tunnel's DNS stayed in place and the next connect could not resolve the
  endpoint
- If putting resolv.conf back fails, the disconnect message says so and the
  original is kept in /tmp/resolv.wg.bak instead of being lost
- The default gateway and its device are read from the same route. They
  could come from two different lines and break the endpoint route

## Thanks

- @augustus-7613 for the endpoint fix (#4)
- @TechnoCode44 and @umaxtu for reporting the getent problem (#5), and
  @TechnoCode44 for the first fix for it (#6)
- @dmascali for tracking down the resolv.conf restore (#2)
- @Dasmonk3003 for the default route report (#2)

Tested on a Kobo Clara Colour.

## What's Changed
* Pin the endpoint from the address wg resolved, not getent by @augustus-7613 in https://github.com/wtb04/wireguard.koplugin/pull/4

## New Contributors
* @augustus-7613 made their first contribution in https://github.com/wtb04/wireguard.koplugin/pull/4

**Full Changelog**: https://github.com/wtb04/wireguard.koplugin/compare/v1.0.4...v1.0.5

# v1.0.4 · 2026-09-18

Security fix: a config file could run commands as root

Endpoint, Address and AllowedIPs went into shell commands unquoted, so a .conf
file from an untrusted source could run commands as root. For Endpoint and
AllowedIPs the plugin also read commented-out lines, so the payload could sit
on a line that WireGuard itself ignores. Values are now checked when the
config loads and quoted at the point of use.

This affects every earlier version. Worth updating if you use configs you did
not write yourself.

## Other fixes

- Commented-out Endpoint and AllowedIPs lines are no longer acted on
- Config names containing a hyphen can connect
- Several error messages crashed instead of showing what was wrong
- Search domains in DNS are written as a search line instead of nameservers
- The readme now says plainly which devices cannot run the plugin

## Thanks

- @ayaOwO for working out which Kobo kernels have TUN support (#1)
- @Dasmonk3003 for testing on Kindle and finding the firewall requirement,
  now documented in the readme (#2)
- @token98 for the endpoint routing report (#3)

The endpoint routing problems reported in #2 and #3 are not fixed in this
release. That work is still open.

**Full Changelog**: https://github.com/wtb04/wireguard.koplugin/compare/v1.0.3...v1.0.4

# v1.0.3 · 2026-06-07

**Full Changelog**: https://github.com/wtb04/wireguard.koplugin/compare/v1.0.2...v1.0.3

# v1.0.2 · 2026-06-07

**Full Changelog**: https://github.com/wtb04/wireguard.koplugin/compare/v1.0.1...v1.0.2

# v1.0.1 · 2026-06-07

**Full Changelog**: https://github.com/wtb04/wireguard.koplugin/compare/v1.0.0...v1.0.1

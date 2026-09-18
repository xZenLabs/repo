# v1.0.4

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

# v1.0.3

**Full Changelog**: https://github.com/wtb04/wireguard.koplugin/compare/v1.0.2...v1.0.3

# v1.0.2

**Full Changelog**: https://github.com/wtb04/wireguard.koplugin/compare/v1.0.1...v1.0.2

# v1.0.1

**Full Changelog**: https://github.com/wtb04/wireguard.koplugin/compare/v1.0.0...v1.0.1

# v1.0.0

**Full Changelog**: https://github.com/wtb04/wireguard.koplugin/commits/v1.0.0

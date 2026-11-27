# v0.8.1 · 2026-11-27

## What's Changed

* Report the real plugin version by @laughedelic in https://github.com/laughedelic/mcp.koplugin/pull/18

### Fixes
- The plugin now reports its real version to the relay and to MCP clients. Until now, every release said 0.3.0. The version is read from `_meta.lua`.

**Full Changelog**: https://github.com/laughedelic/mcp.koplugin/compare/v0.8.0...v0.8.1

# v0.8.0 · 2026-11-27

## What's Changed

* Authenticate relay polling, validate Origin, fix protocol handling by @laughedelic in https://github.com/laughedelic/mcp.koplugin/pull/14
* Support stateless MCP 2026-07-28 and ask before overwriting notes by @laughedelic in https://github.com/laughedelic/mcp.koplugin/pull/15
* Set the plugin version to 0.8.0 by @laughedelic in https://github.com/laughedelic/mcp.koplugin/pull/16
* Add CI checks and a release workflow by @laughedelic in https://github.com/laughedelic/mcp.koplugin/pull/17

### Security
- The plugin now verifies the relay's TLS certificate and host name before sending anything. If verification fails, check the device's date and time. For a self-signed development relay, set `mcp_relay_tls_verify = false`.
- The device generates a secret that authenticates its connection to the relay, so knowing the device ID is no longer enough to receive requests. This needs the updated relay; the default relay is updated.
- Credentials come only from `/dev/urandom`. The plugin refuses to register rather than use weak randomness.
- The local server checks `Origin` to block DNS-rebinding attacks from web pages.

### MCP
- Supports MCP 2026-07-28 (stateless) as well as 2025-03-26, 2025-06-18 and 2025-11-25.
- `annotate` no longer silently overwrites an existing note. Clients with forms ask the user directly. Other clients get a question to relay and pass `if_note_exists` (`replace`, `append` or `keep`).
- Removed sampling, logging and resource subscriptions, which no current client used.

### Fixes
- `search_book`, and `annotate` by text, work for non-Latin scripts. Previously, a Cyrillic query matched almost anything.
- The passcode is shown after a first registration that had to retry.

### For developers
- `scripts/push-to-device.sh <reader-ip>` installs a checkout over KOReader's SSH server.
- CI compiles every Lua file with LuaJIT; releases are published by the Release workflow.

**Full Changelog**: https://github.com/laughedelic/mcp.koplugin/compare/v0.7.0...v0.8.0

# v0.7.0 · 2026-02-04

## What's Changed
* feat: OAuth 2.0 authentication by @laughedelic in https://github.com/laughedelic/mcp.koplugin/pull/11


**Full Changelog**: https://github.com/laughedelic/mcp.koplugin/compare/v0.6.0...v0.7.0

# v0.6.0 · 2026-02-01

## What's Changed
* feat: add bidirectional communication to relay by @laughedelic in https://github.com/laughedelic/mcp.koplugin/pull/7
* feat: add client features (sampling, elicitation, logging) by @laughedelic in https://github.com/laughedelic/mcp.koplugin/pull/9
* feat: add resource subscription notifications by @laughedelic in https://github.com/laughedelic/mcp.koplugin/pull/10


**Full Changelog**: https://github.com/laughedelic/mcp.koplugin/compare/v0.5.1...v0.6.0

# v0.5.1 · 2026-02-01

## What's Changed
* feat: add MCP tool annotations by @laughedelic in https://github.com/laughedelic/mcp.koplugin/pull/6


**Full Changelog**: https://github.com/laughedelic/mcp.koplugin/compare/v0.5.0...v0.5.1

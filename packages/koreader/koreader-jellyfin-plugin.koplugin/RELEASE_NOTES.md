# v1.2.0

- Overhaul the interface.
- Allow sorting and filtering when browsing books.
- Show the cover, genre, series, and other metadata when browsing books.
- Automatically send current book progress to the Jellyfin server (and fetch current progress too).
- Allow setting desired download location for books.
- Improve error messages.
- Fix assorted bugs and performance issues.

The plugin now depends on Jellyfin v12.0 or later due to features introduced in v12.0.

**Full Changelog**: https://github.com/DeclanChidlow/KOReader-Jellyfin-Plugin/compare/v1.1.0...v1.2.0

# v1.1.0

- Improves handling and display of errors returned by the API.
- Moves to Jellyfin's new [authentication system](https://gist.github.com/nielsvanvelzen/ea047d9028f676185832e51ffaf12a6f), adding support for Jellyfin instances with `EnableLegacyAuthorization` set to `false`, such as versions 10.12 and later.

**Full Changelog**: https://github.com/DeclanChidlow/KOReader-Jellyfin-Plugin/compare/v1.0.0...v1.1.0

# v1.0.0

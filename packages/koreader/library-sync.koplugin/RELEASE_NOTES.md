# v0.7.6 · 2026-11-08

# Library Sync 0.7.6

Use Library Sync's folder and filename rules when downloading from BookOrbit's
own KOReader catalogue, without editing BookOrbit's installed files.

## What's new

- Optional **Use Library Sync file rules for BookOrbit downloads** under
  **Library Sync → BookOrbit integration**. **Experimental; OFF by default.**
- Existing Library Sync folder and naming profiles apply to single EPUB/CBZ
  downloads, their destination preview and native bulk downloads from the
  matching BookOrbit server.
- BookOrbit retains ownership of transfers, verification, local file linking,
  existing-file handling and its reading-progress sync. Existing books are not
  moved and KOReader's global download folder is not changed.
- Missing required metadata, invalid custom rules, unsafe paths, changed
  settings and detected compatibility conflicts stop managed downloads rather
  than silently choosing a fallback folder. Cancel/Close remains usable.
- Read-along edition changes update the verified destination; delayed callbacks
  do not start a download after their sheet closes.
- English and Swedish controls, help and owned error messages.
- Fix the updater's no-JSON fallback to match hyphenated package names literally
  and never select a checksum sidecar. Both canonical and legacy ZIPs are tested.

The reviewed compatibility targets are **BookOrbit plugin 2.1.0** (server source
tag 3.6.0) and **2.2.0** (server source tag 3.7.0). Unknown plugin versions are
blocked for managed downloads until reviewed. Other servers and non-EPUB/CBZ
formats keep their native routing. No server extension or new account login is
required. Genre/tag-dependent bulk profiles may add one detail request per book;
flat/author profiles do not require these extra metadata calls.

The existing **0.7.5 HTTP-409 BookOrbit download fallback**, error reporting and
Mirror cleanup protections are included unchanged.

## Install or update

Existing installations: **Library Sync → Check for updates**, then restart
KOReader. New installations: download **library-sync.koplugin.zip** and extract
it into `koreader/plugins/`. Legacy `grimmory-sync.koplugin` installations retain
their matching updater asset. Do not install both directories.

After updating, explicitly enable the new setting if desired. Configure
BookOrbit and the same server address in Library Sync first; use Library Sync's
folder/naming settings while the integration is enabled.

## Verification and limitations

The existing provider contracts and 24 routing cases pass locally under Lua 5.5
and LuaJIT. The supplement runs real, SHA-verified official single-download,
bulk, sheet and path-check methods at frozen 3.6.0/3.7.0 revisions; network,
filesystem, widgets and transfer execution are mocked. Syntax and canonical/
legacy package equivalence/checksums are checked. CI also runs Lua 5.1/LuaJIT.

**Physical Bigme download, restart, cancellation and sleep/resume testing remains
outstanding.** Nothing is installed on a device or deployed to a server by this
release. Back up settings and reading data before trying the opt-in feature.

## Svenska

Från **Library Sync → BookOrbit integration → Använd Library Syncs filregler för
BookOrbit-nedladdningar** kan du låta samma mapp- och filnamnsregler styra nya
EPUB/CBZ-filer även när hämtningen startas i BookOrbit-pluginet. Funktionen är
experimentell och **avstängd som standard**. Förhandsvisning och massnedladdning
omfattas också. BookOrbit sköter fortfarande överföringen och kopplingen till
sin lässynk; inga befintliga böcker flyttas och inget servertillägg behövs.

0.7.5:s tidigare nedladdningsfixar ingår. Automattesterna är gröna, men test på
den fysiska Bigmen återstår. Uppdatera via pluginets uppdateringsmeny, starta om
KOReader och aktivera därefter funktionen om du vill prova den.

# v0.7.5 · 2026-10-26

# Library Sync 0.7.5

Reliable BookOrbit downloads when an advertised OPDS EPUB returns HTTP 409.

## What's new

- Retry BookOrbit OPDS downloads through the authenticated file API when the
  advertised EPUB endpoint returns HTTP 409 Conflict.
- Reuse the authenticated BookOrbit token during a sync and retry once after an
  expired token.
- Show downloaded and failed counts, plus the latest error, while syncing.
- Report incomplete missing-book and metadata syncs instead of presenting failed
  downloads as unchanged books.
- Skip Mirror cleanup whenever one or more missing-book downloads fail.
- Validate BookOrbit file IDs before constructing fallback URLs and cover the
  fallback contract in the provider tests.

The fallback requires normal BookOrbit account credentials with permission to
download books. OPDS remains the primary download path and other server behavior
is unchanged.

## Install or update

Existing installations can use **Library Sync > Check for updates**. New manual
installations should download **library-sync.koplugin.zip**. Legacy installations
inside `grimmory-sync.koplugin` remain supported by the matching OTA asset.

## Verification

Provider contract tests pass under Lua 5.1 and LuaJIT. All Lua sources pass
syntax compilation. Both runtime packages and their SHA-256 sidecars are built
with the repository packaging script. The fallback API route was also verified
against a live BookOrbit server using an EPUB whose OPDS route returned HTTP 409;
the fallback returned a valid EPUB archive.

# v0.7.4 · 2026-10-20

# Library Sync 0.7.4

Clearer installation and discovery for ordinary KOReader users.

Library Sync downloads missing EPUB books and CBZ comics from Grimmory or
BookOrbit, organizes local files and refreshes server metadata. It does not
require Bookshelf, OrbitUI or SimpleUI.

## What's new

- Updated English introduction, feature overview and requirements.
- Separate Storefront/AppStore and manual installation instructions, with a clear
  distinction between new installations and the legacy Grimmory directory.
- Explicit explanation of optional UI integrations, opt-in Mirror/automatic
  refresh, and what belongs to BookOrbit's separate progress-sync plugin.
- Reproducible runtime packages, SHA-256 sidecars and automated packaging checks.

This is a documentation and packaging release. Server providers, sync behavior,
saved credentials, local paths, routing profiles and manifests are unchanged from
0.7.3. That version's Grimmory library-source support remains included.

## Install or update

New installation: choose **library-sync.koplugin.zip**, extract it into
`koreader/plugins/`, and restart. Storefront/AppStore users should choose the
**komadorirobin/library-sync.koplugin** entry and this stable release.

Existing installations can use **Library Sync > Check for updates**.
If your installation still uses `grimmory-sync.koplugin`, the built-in updater
selects **grimmory-sync.koplugin.zip**. Do not install both directories.
All settings and reading data are retained.

## Verification

Provider contract tests pass under Lua 5.1 and LuaJIT. Runtime ZIP contents,
canonical/legacy equivalence and checksums are validated. No physical e-reader
installation or live server sync was performed for this documentation release.

# v0.7.3 · 2026-10-19

## What's new

- Add complete Grimmory libraries as selectable sync sources alongside shelves and Magic Shelves.
- Library sources apply consistently to missing-book sync, metadata refresh, and Mirror selected sync source.
- Keep compatibility with older Grimmory versions that do not expose the libraries endpoint.
- Document library selection and add provider contract coverage for both new and legacy Grimmory servers.

Grimmory library selection requires a server version that exposes `/api/v1/opds/libraries`, available in Grimmory 3.5.0.

Both ZIP assets are included for new and legacy OTA installations.

# v0.7.2 · 2026-10-13

## What's new

- Add compatibility with BookOrbit 3.4.0's plain-text OPDS descriptions.
- Compare description content semantically, treating equivalent HTML and plain text as unchanged.
- Migrate existing HTML-based manifest signatures locally instead of downloading and replacing unchanged EPUB/CBZ files.
- Continue detecting genuine description text changes.
- Add regression coverage for HTML-to-text migration and real description changes.

After updating, cancel any previously prepared mass refresh and run **Refresh existing metadata** again. The first scan may take its usual time while old signatures are migrated, but equivalent descriptions should be skipped rather than downloaded.

Both ZIP assets are included for new and legacy OTA installations.

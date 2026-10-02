# v1.26.1-dev · 2026-09-30

- **Browse Goodreads — crash fix.** If the image cache directory was missing, pruning threw and the whole page failed ("Couldn't load the page"). Pruning is now a safe no-op and image/CSS enrichment can never fail a page. Added a regression test.
- **Browse Goodreads — better home + messages.** It opens **My Books** (`/review/list`) instead of the anti-bot-challenged root `/`, and shows clearer "sign-in required" / "blocked" messages.
- **Browse Goodreads is now experimental and dev-channel only** (hidden on stable), labelled "Browse Goodreads (experimental)…".
- **Reader-style rendering by default** (skips the site's modern CSS, which CRE can't lay out); dev toggle for Site vs Reader style.

# v1.26.0-dev · 2026-09-30

- **Selectable update channel.** Settings, and the main-menu version label, now honour an **Update channel** preference: **Stable** (published releases) or **Dev** (prereleases from the dev branch). The default matches the channel the running build was published on; switching channels changes where "check for updates" (and the daily auto-check) fetches from.
- Both channels are now published: `v1.26.0` (stable) and `v1.26.0-dev` (dev prerelease).

# v1.25.1-dev · 2026-09-30

- Clear the stale `last_sync_error` after a successful sync. It was only ever set on failure, so an old network error lingered in the diagnostics page even after later successful syncs. Now a successful sync clears it (and the diagnostics page treats an empty value as "none").

### PW3 hardware findings (in progress)
- Physical PW3 testing reproduces the static ARM helper's failure: every fetch
  scheme returns `about:query/fetcherror` and the process aborts with
  `double free or corruption`. This is a **real ARM build/run bug**, not a qemu
  artifact (the earlier note was corrected). Root-cause in progress.

# v1.25.0-dev · 2026-09-30


PW3 packaging + helper robustness; QEMU limitation documented.

- The engine now consumes a **complete** `frame.pgm` + `frame.json` even when the
  helper exits non-zero (post-output abort), recording `helper_exit` in the
  frame. It still fails cleanly when no usable output exists. Regression tests
  cover: valid output despite nonzero exit, nonzero exit without output, missing
  output on a clean exit, corrupt JSON with and without nonzero exit, and the
  platform IO/quoting helpers.
- `engines/netsurf/package-pw3.sh` produces a **self-contained** device bundle:
  static ARM helper + NetSurf `resources/` (incl. `ca-bundle`, and `mime.types`
  when available) + a launcher that resolves everything relative to itself.
  Verified from a clean directory (no build-tree dependency).
- `engines/netsurf/QEMU-LIMITATION.md`: dynamic `kindlepw2` glibc 2.12 binaries
  don't run under qemu-user; the static binary executes but NetSurf fetches fail
  uniformly (including `about:`/`data:`/`file:`) and it aborts post-output; the
  identical frontend works natively on x86_64. QEMU is therefore not a valid
  proxy for PW3 fetch/runtime validation — physical hardware is required.
- Tests 233 → 240.

# v1.24.0-dev · 2026-09-30


Linux KOReader → Browser Host → NetSurf → bitmap integration (end-to-end).

- `ui/netsurf_browser.lua`: a generic browser view that displays a BrowserEngine
  bitmap through KOReader (BB8 via memcpy), routes taps through the engine
  hitmap and swipes to engine scrolling, with back/forward/reload. It asks the
  `Browser Host` for an engine and uses only the `BrowserEngine` contract; CRE is
  untouched.
- `Host.create_engine(name, opts)`: the UI never constructs an engine directly.
- `browse/frame.lua`: pure frame helpers (gray_at, to_pgm, is_valid).
- `More → Browser engine (dev) → Open NetSurf browser (dev)` entry.
- Headless self-test hook (`GRK_NETSURF_SELFTEST=1`) exercising the full path
  inside real KOReader.
- Verified inside KOReader v2026.07.1 (headless): example.com, gnu.org (CSS),
  netsurf-browser.org (images), a Goodreads book page (cover shown), HTTPS,
  hitmap, tap→navigate, back/forward/reload, scrolling; invalid URL fails
  cleanly. Browsing created no books/`.sdr`/mappings — sync cannot be triggered.
- Measured (x86_64): example.com ~0.16 s / ~20 MB; Goodreads book page ~25 s /
  ~139 MB.
- Docs: `engines/netsurf/LINUX.md` (requirements, helper protocol, lifecycle,
  measurements).
- Tests 227 → 233 (Host engine factory, frame helpers, platform).

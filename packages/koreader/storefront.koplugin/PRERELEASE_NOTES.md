# 26.11.24-beta · 2026-11-24

### Memory Conductor v2 — Hardening & API Upgrades

* **Earlier Startup Protection:** Installs Conductor hooks at module load time so plugins alphabetically before Storefront are protected during `:init()`.
* **Long-Running Subprocess Support:** Auto-extends slot leases (up to `600s`) for active child processes, probes `waitpid` (`WNOHANG`) to reap leaked PIDs immediately, and skips locking `double_fork` spawns.
* **NTP-Immune Monotonic Timing:** Uses KOReader's monotonic clock (`ui/time`) so Wi-Fi NTP time jumps cannot break subprocess TTLs or `1.5s` cooldowns.
* **Faster Pre-`fork()` & Reclaim Handling:** Debounces `stabilizeBeforeFork` (`2.0s`) to avoid double GC sweeps, adds post-subprocess cooldowns, directly fans out `onMemoryReclaim(level)` so `return true` cannot block other plugins, and rate-limits repeat reclaims (`5s`/`10s`).
* **Unschedule Fix:** Preserves `UIManager:unschedule`'s boolean return value and cancels multi-scheduled callbacks cleanly.
* **Developer API:** Added `dedupe_key`, `lease_s`, tracked `foreground` slots (with idempotent `done()`), and `Conductor.getStats()`.

**Docs:** [Memory Conductor & Developer API (Wiki)](https://github.com/ultimatejimmy/storefront.koplugin/wiki/9.-Memory-Conductor)



**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.11.21-beta...26.11.24-beta

# 26.11.21-beta · 2026-11-21

### What's New: Storefront Memory Conductor

Storefront now includes a built-in **Memory Conductor** (`storefront_conductor`) that coordinates background tasks, `fork()` subprocesses, and cache eviction across **all installed KOReader plugins**—preventing Kindle's memory watchdog and Linux OOM killer from terminating KOReader when multiple plugins run simultaneously.

#### Key Features
* **Automatic Cross-Plugin Protection (Zero Configuration):**
  * **Background Timer Serialization:** Transparently wraps `UIManager:scheduleIn` and `unschedule` to serialize background plugin timers into a single-lane priority queue, preventing startup, wake, and Wi-Fi reconnect stampedes. Foreground UI actions, core KOReader timers, micro-timers (`<= 0.25s`), and active subprocess pollers continue with zero delay.
  * **Pre-`fork()` Copy-On-Write Stabilization:** Wraps `ffiutil.runInSubProcess`, `isSubProcessDone`, and `terminateSubProcess` to reclaim soft caches and flush LuaJIT GC debt before any plugin forks a child process, preventing parent-process CoW RAM duplication while background workers run.
  * **Kindle-Aware `/proc/meminfo` Thresholds:** Accurately accounts for `Shmem` on legacy Kindle kernels (Linux 3.0) and enforces safe RAM floors (`45 MB` soft / `28 MB` critical on `<= 512 MB` devices) before dispatching background work.
* **Developer API & Event Protocol (Zero Hard Dependency):**
  * **Level 1 (`MemoryReclaim` Event):** Plugins can implement `function MyPlugin:onMemoryReclaim(level)` to shed private in-memory caches on demand without importing Storefront.
  * **Level 2 (`storefront_conductor` API):** Plugins can request priority-managed execution slots (`foreground`, `interactive_bg`, `idle_bg`) via `pcall(require, "storefront_conductor")` with `Conductor.requestSlot()`, `Conductor.registerPlugin()`, `Conductor.reclaimMemory()`, and `Conductor.getMemoryStatus()`.

#### Documentation
* Full architecture details, standalone fallback templates, and API reference: **[Memory Conductor & Developer API (Wiki)](https://github.com/ultimatejimmy/storefront.koplugin/wiki/9.-Memory-Conductor)**

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.11.20...26.11.21-beta

# 26.11.19-beta · 2026-11-19

De-duplicate repos with the same name for likes

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.11.18-beta...26.11.19-beta

# 26.11.18-beta · 2026-11-18

Fix a bug with the likes not always updating

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.11.17-beta...26.11.18-beta

# 26.11.17-beta · 2026-11-17

- Update font catalog logic to make it more efficient
- Show the version number of plugins on the installed tab

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.11.15-beta...26.11.17-beta

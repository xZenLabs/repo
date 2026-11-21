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

# 26.11.15-beta · 2026-11-15

- refine font catalog logic

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.11.13-beta...26.11.15-beta

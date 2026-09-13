# RakuYomi Bridge

Android companion app + Kotlin Multiplatform modules for the [RakuYomi](https://github.com/tachibana-shin/rakuyomi) manga reader KOReader plugin.

Loads `librakuyomi_server.so` (Rust HTTP server from the rakuyomi monorepo) via JNI and runs it as an Android foreground service, exposing the server at `http://127.0.0.1:8787`. This enables the KOReader Lua plugin to communicate with the Rust backend (SQLite + WASM sources) on Android devices.

## Installation

Download the latest APK from [GitHub Releases](https://github.com/tachibana-shin/rakuyomi_bridge/releases). Two variants are available:

| Application | Support |
| --- | --- |
| Rakuyomi Bridge | Android `5+` (v8 and x86_64) |
| Rakuyomi Bridge Headless | Android `4.3+` (v8 and v7 and x86_64) |

- **`RakuYomiBridge`** -- Compose app (Android 5.0+)
- **`RakuYomiBridge Headless`** -- Headless app (Android 4.3+)

After installing, start the server via the app or deep link (`rakuyomi_bridge://start`). Grant storage and notification permissions when prompted. The server runs as a foreground service on `127.0.0.1:8787`.

### Xiaomi Devices (MIUI / HyperOS)

To ensure Rakuyomi Bridge maintains a stable background connection and is not aggressively terminated by the system, adjust the following settings in the **App Info** page:

- **Disable App Hibernation:** Turn off **"Pause app activity if unused"**.
- **Adjust Battery Settings:** Change the Battery Saver profile to **"No restrictions"**.

## Modules

| Module | Description | Android Support |
|---|---|---|
| `:shared` | KMP shared module (Android + JVM). Contains `JniBridge`, `RakuyomiServer`, `ServerConfig`, `BridgeClient`, `NetworkBridgeWorker`, `UpdateManager`. | -- |
| `:androidApp` | Full-featured Android app with Jetpack Compose (Material 3), Hilt DI, DataStore, navigation, built-in update flow, embedded browser, log viewer. | Android 5.0+ (API 21+) |
| `:androidHeadless` | Minimal Android app with a programmatic `LinearLayout` (no Compose, no Hilt). Different `applicationId` for side-by-side install with the Compose app. | Android 4.3+ (API 18+) |
| `:cli` | JVM CLI test harness for Linux development and CI. | -- |

## Architecture

```
KOReader (Lua) --TCP--> Rust server (librakuyomi_server.so) -- SQLite + WASM sources
                            ^
Android:                    |
  JniBridge (System.loadLibrary)
  RakuyomiServerAdapter (start/stop)
  BaseServerService (foreground service + notification)
```

The JNI bridge provides `nativeStart`, `nativeStop`, `nativeIsRunning`, `nativePollLogs`, `nativeSendNetworkResponse`, and `nativeSendNetworkError` -- implemented in `backend/server/src/jni.rs` (Rust). The Rust side can call back into Kotlin via `JniBridge.onNetworkRequest` to delegate HTTP requests made by WASM sources.

## Build

The Rust `.so` must be built first, then the Gradle build creates APKs:

```sh
# 1. Build Rust native library (from rakuyomi repo root)
scripts/build-rust-android.sh

# 2. Build Android APKs (from bridge/)
./gradlew assembleDebug
```

Requires Rust 1.95.0 with Android targets (`aarch64-linux-android`, `armv7-linux-androideabi`, `x86_64-linux-android`) and `cargo-ndk`.

## Deep Link Schemes

- Compose app: `rakuyomi_bridge://start` / `rakuyomi_bridge://stop`
- Headless app: `rakuyomi_bride://start` / `rakuyomi_bride://stop`

## CLI Usage (Linux)

```sh
./gradlew :cli:run --args="health 8787"
./gradlew :cli:run --args="run ./server /tmp/data"
./gradlew :cli:run --args="test ./server /tmp/data"
```

## Permissions (Android)

| API | Permission |
|---|---|
| 30+ | `MANAGE_EXTERNAL_STORAGE` |
| 33+ | `POST_NOTIFICATIONS` |
| 34+ | `FOREGROUND_SERVICE_DATA_SYNC` |

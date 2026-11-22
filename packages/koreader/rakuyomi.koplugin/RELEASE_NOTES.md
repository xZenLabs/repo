# v1.43.8 · 2026-11-22

## [1.43.8](https://github.com/yuuki-kagura/rakuyomi/compare/v1.43.7...v1.43.8) (2026-11-22)


### Bug Fixes

* **reader:** compare ReadHistory paths with realpath ([#5](https://github.com/yuuki-kagura/rakuyomi/issues/5)) ([b3303ad](https://github.com/yuuki-kagura/rakuyomi/commit/b3303ad994751be59b38ab785ff363352ee99ebf))
* tolerate broken source lists and source files ([#2](https://github.com/yuuki-kagura/rakuyomi/issues/2)) ([80ee2ad](https://github.com/yuuki-kagura/rakuyomi/commit/80ee2ad7423f15f04cde4231c4b9366e7971072e))

# v1.43.7 · 2026-11-16

## [1.43.7](https://github.com/yuuki-kagura/rakuyomi/compare/v1.43.6...v1.43.7) (2026-11-16)


### Bug Fixes

* revert 6c780369280db27d05fb7c10ac565430e694f05d ([eedf8e9](https://github.com/yuuki-kagura/rakuyomi/commit/eedf8e90a74fcbbeb28726e2ec47fe16d99b2aa6))

# v1.43.6 · 2026-11-15

## [1.43.6](https://github.com/yuuki-kagura/rakuyomi/compare/v1.43.5...v1.43.6) (2026-11-15)


### Bug Fixes

* make backend socket-error detection actually match ([6c78036](https://github.com/yuuki-kagura/rakuyomi/commit/6c780369280db27d05fb7c10ac565430e694f05d))

# v1.43.5 · 2026-11-14

## [1.43.5](https://github.com/yuuki-kagura/rakuyomi/compare/v1.43.4...v1.43.5) (2026-11-14)


### Bug Fixes

* recover from a silently dead backend and stop leaking temp files ([8be3a90](https://github.com/yuuki-kagura/rakuyomi/commit/8be3a90fd432ff300a2c608e4e5d41cdd490456a))

# v1.43.4 · 2026-11-14

## [1.43.4](https://github.com/yuuki-kagura/rakuyomi/compare/v1.43.3...v1.43.4) (2026-11-14)


### Bug Fixes

* **ci:** use macos-latest for the macOS build job ([85e3b78](https://github.com/yuuki-kagura/rakuyomi/commit/85e3b7815efe2750b157955e1f5689e5ac99cb6e))
* trigger release ([17c7c96](https://github.com/yuuki-kagura/rakuyomi/commit/17c7c9615b532e46f7847860259b847da22314b0))


### Performance Improvements

* **cookie-bot:** stop registering bot commands on every cold isolate ([30d8002](https://github.com/yuuki-kagura/rakuyomi/commit/30d80029c0566587edc415dd23a57561d948a720))

# v1.42.2 · 2026-09-30

## [1.42.2](https://github.com/tachibana-shin/rakuyomi/compare/v1.42.1...v1.42.2) (2026-09-30)


### Bug Fixes

* **source:** reload an Aidoku source when its settings change ([#371](https://github.com/tachibana-shin/rakuyomi/issues/371)) ([856eb06](https://github.com/tachibana-shin/rakuyomi/commit/856eb06fbab89703dbe767846921b920d7a9bb57))

# v1.42.1 · 2026-09-29

## [1.42.1](https://github.com/tachibana-shin/rakuyomi/compare/v1.42.0...v1.42.1) (2026-09-29)


### Bug Fixes

* don't use `_` for space param ([e78e255](https://github.com/tachibana-shin/rakuyomi/commit/e78e255f03cfafadd7ac1037870c26ca0f452457))

# v1.42.0 · 2026-09-23

# [1.42.0](https://github.com/tachibana-shin/rakuyomi/compare/v1.41.8...v1.42.0) (2026-09-23)


### Bug Fixes

* keep in-memory chapter last_read in sync on mark read/unread ([#348](https://github.com/tachibana-shin/rakuyomi/issues/348)) ([#357](https://github.com/tachibana-shin/rakuyomi/issues/357)) ([44ca5c9](https://github.com/tachibana-shin/rakuyomi/commit/44ca5c93167550badd08f0bda45900bd8f9c5a47))
* report error when no chapters are selected for download ([#356](https://github.com/tachibana-shin/rakuyomi/issues/356)) ([14040fe](https://github.com/tachibana-shin/rakuyomi/commit/14040fe6989a24eede59324a1212899ccaa48c95)), closes [#347](https://github.com/tachibana-shin/rakuyomi/issues/347) [#347](https://github.com/tachibana-shin/rakuyomi/issues/347) [#347](https://github.com/tachibana-shin/rakuyomi/issues/347)


### Features

* support downloading specific chapters and ranges ([#355](https://github.com/tachibana-shin/rakuyomi/issues/355)) ([3620d55](https://github.com/tachibana-shin/rakuyomi/commit/3620d559e5be2b54b4e593a9bafe3ff3c242fcf6)), closes [#344](https://github.com/tachibana-shin/rakuyomi/issues/344) [#344](https://github.com/tachibana-shin/rakuyomi/issues/344)

# v1.41.8 · 2026-09-08

## [1.41.8](https://github.com/tachibana-shin/rakuyomi/compare/v1.41.7...v1.41.8) (2026-09-08)


### Bug Fixes

* **aidoku:** sync process_page_image on lazy boot ([#342](https://github.com/tachibana-shin/rakuyomi/issues/342)) ([82087f7](https://github.com/tachibana-shin/rakuyomi/commit/82087f74f42d88ebbb12b3df388df61f7c46874c))

# v1.41.7 · 2026-09-08

## [1.41.7](https://github.com/tachibana-shin/rakuyomi/compare/v1.41.6...v1.41.7) (2026-09-08)


### Bug Fixes

* apply cookies.json to wasm image requests ([#338](https://github.com/tachibana-shin/rakuyomi/issues/338)) ([#340](https://github.com/tachibana-shin/rakuyomi/issues/340)) ([2dbcbbc](https://github.com/tachibana-shin/rakuyomi/commit/2dbcbbc78d2f1d0ce9543ac872c23f83cd985c5a))
* **ui:** reconnect to Wi-Fi before retrying source list fetch ([#334](https://github.com/tachibana-shin/rakuyomi/issues/334)) ([#341](https://github.com/tachibana-shin/rakuyomi/issues/341)) ([ccdeaac](https://github.com/tachibana-shin/rakuyomi/commit/ccdeaac140c7fbfb60ee89a17f99ac9e6a8a53bf))

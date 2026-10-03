# MiuRead

> **5.9.0 · 正式版**

MiuRead（觅阅 · 微信读书助手）是面向 KOReader 的非官方微信读书客户端。5.9.0 将 5.9 beta 阶段验证完成的多设备进度对账、精确位置保护、同步恢复、外文翻译与扩展中心改进正式收口到稳定通道。

本仓库同时维护正式版与内测版：

- `main`：正式版
- `beta`：内测版
- 正式 OTA：`stable-channel/update.json`
- 内测 OTA：`beta-channel/update-beta.json`

## Versions

- 当前正式基线：`5.9.0`，Schema `136`。
- 正式版：以 GitHub Releases 中最新的非 Pre-release 为准。
- 内测版：以 GitHub Releases 中最新的 Pre-release 为准。

完整版本记录见 [`CHANGELOG.md`](CHANGELOG.md)。

## 5.9.0 highlights

- 多设备阅读进度使用 verified anchor、真实阅读事件时间与精确 `chapter_uid + co` 进行无感对账；无法安全裁决时保持 conflict/fence，不让旧位置覆盖新云端位置。
- 主页快捷同步、同步状态与进度失败恢复统一使用同一 progress recovery；设备唤醒后等待网络真正 online-ready 再进行云端 reconcile。
- 精确位置 recovery 在旧 source cache 失效后可真正刷新目标章节源数据；reading-time writer 抢占使用 KOReader 子进程完成状态，减少误判超时。
- 外文书支持原文、双语、仅译文显示与官方译文生成；数字 bookId 同样可尝试官方翻译能力，失败时保留原文与原 EPUB。
- 保留 5.8 系列的下载、书架恢复、扩展中心、批注/评论及后台稳定性改进。

## Installation

1. 在 GitHub Releases 下载需要的版本。
2. 解压后将完整的 `miuread.koplugin` 目录放入 KOReader 的插件目录。
3. 完整重启 KOReader。
4. 支持双更新通道的版本可在“觅阅设置 → 更新与关于 → 更新通道”中选择正式通道或内测通道。

## Release Process

- Stable tag：`vX.Y.Z`
- Beta tag：`vX.Y.Z-beta.N`
- 正式版发布到 `stable-channel`
- 内测版发布到 `beta-channel`
- 发布前源码中的版本号、更新通道与 `CHANGELOG.md` 必须已经与目标版本一致。
- Release workflow 先完成身份校验与回归测试，再确保对应 Tag 并生成安装包和 OTA 清单。
- Beta Tag 必须对应 `beta` 最新提交；Stable Tag 必须对应 `main` 最新提交。
- 最终分支源码、Tag 源码、Release 安装包与 OTA 清单保持同一版本。

仓库根目录 `update.json` 仅保留为旧正式版 OTA 桥接入口；实时正式更新清单发布在 `stable-channel/update.json`。

## Origin and License

MiuRead originated as a modified version of `finlater/weread.koplugin` v0.1.1 and has since undergone substantial restructuring, modification, and extension.

MiuRead is an unofficial community project and is not affiliated with or endorsed by WeRead, Tencent, KOReader, or their maintainers.

This project is distributed under the GNU Affero General Public License version 3 only (`AGPL-3.0-only`). See `LICENSE`, `NOTICE`, and `THIRD_PARTY_NOTICES` for details.

# MiuRead

> **5.9.0 · Stable Release**

5.9.0 开始把“本机/云端冲突需要用户判断”改为无感云端镜像：打开书籍时自动按同步因果和更新时间选择最新阅读状态，在定位完成前短暂保护翻页；精确 `chapter_uid + co` 仍是最终验收依据。账号书架默认使用微信云端顺序，已读完状态与当前位置分离解析，自动云端跳转可以短时撤回。

本仓库同时维护正式版与内测版：

- `main`：正式版
- `beta`：内测版
- 正式 OTA：`stable-channel/update.json`
- 内测 OTA：`beta-channel/update-beta.json`

## Versions

- 正式版：以 GitHub Releases 中最新的非 Pre-release 为准。
- 内测版：以 GitHub Releases 中最新的 Pre-release 为准。

完整版本记录见 [`CHANGELOG.md`](CHANGELOG.md)。

当前正式版：`5.9.0`。本版本由 `5.9.0-beta.19` 收口而来，以 5.8.0-beta.26 为兼容基线，Schema 为 136；正式版保留 5.9 beta 阶段已经完成验证的多设备 latest-wins、精确进度与安全恢复模型。


## 5.9.0 highlights

- 多设备续读以可信 verified anchor、真实阅读事件与云端更新时间判断 `LOCAL_NEWER / REMOTE_NEWER / ALIGNED / CONFLICT`，并用 write fence 防止旧位置误写回云端。
- 精确同步以 `chapter_uid + co` 为最终验收；本地映射使用多级双向唯一正文锚点、fresh source recovery 和严格 fail-closed 策略。
- 云端唯一 text anchor 命中后保留正文落点，不再让 percent correction 覆盖已经成功的精确导航。
- 阅读时间保持 best-effort 与 fresh-GET-before-POST，和阅读进度写入相互隔离；失败恢复采用 verify-first，避免不确定写请求被重复提交。
- 微信读书外文书支持原文、双语、仅译文三态以及安全译文 EPUB 替换。
- 主页刷新/同步入口、扩展中心、下载、锁屏和本地书库能力继续继承并整合 5.8 后期改进。

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
- 创建 Tag 后，发布工作流会自动同步分支源码中的版本号、发布通道与 `CHANGELOG.md`，再把 Tag 指向同步后的提交。
- Beta Tag 必须创建在 `beta` 最新提交；Stable Tag 必须创建在 `main` 最新提交。
- 最终分支源码、Tag 源码、Release 安装包与 OTA 清单保持同一版本。

仓库根目录 `update.json` 仅保留为旧正式版 OTA 桥接入口，不作为当前正式版实时更新清单。

## Origin and License

MiuRead originated as a modified version of `finlater/weread.koplugin` v0.1.1 and has since undergone substantial restructuring, modification, and extension.

MiuRead is an unofficial community project and is not affiliated with or endorsed by WeRead, Tencent, KOReader, or their maintainers.

This project is distributed under the GNU Affero General Public License version 3 only (`AGPL-3.0-only`). See `LICENSE`, `NOTICE`, and `THIRD_PARTY_NOTICES` for details.

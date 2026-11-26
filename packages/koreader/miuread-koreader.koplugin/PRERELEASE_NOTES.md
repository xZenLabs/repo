# v6.7.0-beta.18 · 2026-11-26

- 内核改造，全面切换为原生

# v6.6.0-beta.1 · 2026-11-21

- fix: 修复 E-Ink 授权续期与优化交互层级 (#191, #192)

# v6.5.0-beta.28 · 2026-11-09

- 修复 beta.27 在 GitHub Actions 发布前回归测试中 `_local_comment_enabled` 未加入模拟插件环境导致的失败：测试调用真实方法，并分别验证未关联和已关联本地 EPUB 的翻页行为。
- 将本地 EPUB 关联、章节匹配、评论回复以及私人上传书籍空划线补充查询的离线回归正式加入 `release-beta` 发布前检查，避免新功能未经 CI 验证就发包。
- 保留 beta.27 的本地 EPUB 社区评论功能及 beta.26 的下载、阅读时间、精确进度、多设备同步；不改变实际业务协议，Schema 仍为 136。
- 微信读书私人上传书籍的接口返回、EPUB 正文标记点击和 Kindle/KOReader 真机行为仍需在线与设备验收。

# v6.5.0-beta.26 · 2026-11-07

- fix(readtime): aggregate E-Ink offline reports and preserve unsent time (#184)
- fix(readtime): reserve safe Web retries before dispatch
- fix(readtime): exclude inactive gaps from Web reading time

# v6.5.0-beta.25 · 2026-11-07

- 本次更新准备发布 MiuRead 6.5.0-beta.24，重点修复 EPUB 多级目录问题，并完善 GitHub Release 与 Issue 自动关联机制。

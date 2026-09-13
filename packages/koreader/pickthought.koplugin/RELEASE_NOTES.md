# v0.5.2

## 本次更新

新功能：
进度面板重排与自适应文案,菜单收敛与交互修复
匹配口径最终化与 no_hit 缓存,真实已匹配量贯通
文本宽度估算与成对数值行自适应拆分助手
划线文字样式追加斜体选项
划线文字样式可选(Issue #23)

问题修复：
默认划线样式补运行时覆盖,关闭内嵌样式不再变实线
提交扫描拦截 LuaJIT 字节码等非 UTF-8 文件
匹配阶段进度语义修正与回退取证日志
移植上游章节标题索引并修复全命中误报取消 (#24)（PR #24/#150）

# v0.5.1

## 本次更新

新功能：
发布摘要支持 refactor 前缀
关于弹窗内容更新

问题修复：
登录行点按弹账户动作面板,想法弹窗设置放回划线样式下
移除菜单分隔线占位项
敏感信息扫描放行自身测试夹具并覆盖未跟踪文件

结构调整：
上游式收纳——登录行合并账户,低频入设置抽屉
菜单三段式重组,想法弹窗设置提级,命名统一
日志收敛、弹窗基类收敛与菜单抽离

# v0.5.0

## 本次更新

新功能：
想法评论查看与评论数懒加载（Issue #104 / PR #22/#106）

问题修复：
发布摘要识别 PR 合并提交

---

## Contributors（本次更新的贡献者）

- @Mr54233

---

## 安装

1. 下载 `pickthought.koplugin.zip` 并解压
2. 把 `pickthought.koplugin` 目录放到 KOReader 插件目录：
`koreader/plugins/pickthought.koplugin`
3. 完全重启 KOReader，在「工具」菜单找到「撷思」

## 环境要求

KOReader ≥ v2026.03（需要内建的 `ffi/archiver` 与 `lua-ljsqlite3`）。

---

本插件衍生自 [miuread-koreader](https://github.com/miumiupy98-art/miuread-koreader) 与 [weread.koplugin](https://github.com/finlater/weread.koplugin)，基于 AGPL-3.0 许可证发布。

# v0.4.2

## 本次更新

问题修复：
修复跨页裁切并完善尺寸设置（Issue #21）

---

## Contributors（本次更新的贡献者）

- @Mr54233

---

## 安装

1. 下载 `pickthought.koplugin.zip` 并解压
2. 把 `pickthought.koplugin` 目录放到 KOReader 插件目录：
`koreader/plugins/pickthought.koplugin`
3. 完全重启 KOReader，在「工具」菜单找到「撷思」

## 环境要求

KOReader ≥ v2026.03（需要内建的 `ffi/archiver` 与 `lua-ljsqlite3`）。

---

本插件衍生自 [miuread-koreader](https://github.com/miumiupy98-art/miuread-koreader) 与 [weread.koplugin](https://github.com/finlater/weread.koplugin)，基于 AGPL-3.0 许可证发布。

# v0.4.1

## 本次更新

性能优化：
优化想法弹窗冷启动读取

问题修复：
完善想法数据库异常恢复

---

## Contributors（本次更新的贡献者）

- @Mr54233

---

## 安装

1. 下载 `pickthought.koplugin.zip` 并解压
2. 把 `pickthought.koplugin` 目录放到 KOReader 插件目录：
`koreader/plugins/pickthought.koplugin`
3. 完全重启 KOReader，在「工具」菜单找到「撷思」

## 环境要求

KOReader ≥ v2026.03（需要内建的 `ffi/archiver` 与 `lua-ljsqlite3`）。

---

本插件衍生自 [miuread-koreader](https://github.com/miumiupy98-art/miuread-koreader) 与 [weread.koplugin](https://github.com/finlater/weread.koplugin)，基于 AGPL-3.0 许可证发布。

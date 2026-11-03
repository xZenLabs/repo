# v1.7.0 · 2026-11-03

## 新功能与改进

- 新增阅读时长上报间隔设置，可选择 30 秒或 60 秒。
- 新增“继续匹配划线和想法”手势操作。
- 优化章节状态显示，区分待获取、待匹配和已匹配。
- 修复下一章预下载打断划线和想法获取的问题。
- 修复部分扫码登录中断、登录二维码显示不完整的问题。

## What's Changed
* feat: add continue-matching gesture by @deanbear in https://github.com/finlater/weread.koplugin/pull/196
* fix: keep annotation prefetch alive during chapter prefetch by @deanbear in https://github.com/finlater/weread.koplugin/pull/195
* fix: retry QR login when getLoginInfo connection closes by @arislee1979-afk in https://github.com/finlater/weread.koplugin/pull/181
* fix: delay QR login dialog display to prevent clipping on Kindle by @zhufangu in https://github.com/finlater/weread.koplugin/pull/201
* feat(read_report): expose reporting interval presets in the menu by @yang11235 in https://github.com/finlater/weread.koplugin/pull/210

## New Contributors
* @deanbear made their first contribution in https://github.com/finlater/weread.koplugin/pull/196
* @arislee1979-afk made their first contribution in https://github.com/finlater/weread.koplugin/pull/181
* @zhufangu made their first contribution in https://github.com/finlater/weread.koplugin/pull/201
* @yang11235 made their first contribution in https://github.com/finlater/weread.koplugin/pull/210

**Full Changelog**: https://github.com/finlater/weread.koplugin/compare/v1.6.0...v1.7.0

# v1.6.0 · 2026-10-05

## 新功能与改进

- 支持多设备登录。
- 新增版本更新弹窗，支持立即更新、稍后提醒和跳过版本。
- 新增手势操作：立即同步阅读进度、查看阅读时长上报状态。
- 优化想法弹窗排版，修复翻页留白和文字重复问题。
- 脚注显示交由 KOReader 原生设置控制，移除“隐藏脚注文本”选项；已有书籍需重新下载以应用调整。
- 微信读书入口默认前移至工具菜单首位。
- 修复插件语言跟随和封面清晰度问题。

## What's Changed
* 修复 s_ 类型封面未升级为高清封面的问题 by @finlater in https://github.com/finlater/weread.koplugin/pull/186
* fix: 跟随 KOReader 自动识别的界面语言 by @finlater in https://github.com/finlater/weread.koplugin/pull/187
* fix: let readers control book footnotes by @finlater in https://github.com/finlater/weread.koplugin/pull/188
* feat: place WeRead first in the tools menu by @finlater in https://github.com/finlater/weread.koplugin/pull/189
* docs: remove added footnote explanation by @finlater in https://github.com/finlater/weread.koplugin/pull/190
* refactor: remove footnote hiding option by @finlater in https://github.com/finlater/weread.koplugin/pull/191
* feat: prompt users when plugin updates are available by @finlater in https://github.com/finlater/weread.koplugin/pull/192
* fix: refine thought popup layout by @finlater in https://github.com/finlater/weread.koplugin/pull/193
* feat: add progress sync and report status gestures by @finlater in https://github.com/finlater/weread.koplugin/pull/194


**Full Changelog**: https://github.com/finlater/weread.koplugin/compare/v1.5.3...v1.6.0

# v1.5.3 · 2026-10-01

## 新功能与改进

- 优化封面书架布局与阅读状态标记，公众号支持封面模式。
- 优化章节对应界面，清晰区分已获取、待获取和未对应状态。
- 修复关闭书架后封面资源未释放的问题。

感谢 @IswordSun 的贡献。

## What's Changed
* feat: 美化书架封面网格并支持公众号封面模式 by @IswordSun in https://github.com/finlater/weread.koplugin/pull/176


**Full Changelog**: https://github.com/finlater/weread.koplugin/compare/v1.5.2...v1.5.3

# v1.5.2 · 2026-09-19

## 新功能与改进

- 修复部分书籍获取划线和想法时中途报错的问题。
- 修复获取中断后，已完成章节的划线未及时显示的问题。

**Full Changelog**: https://github.com/finlater/weread.koplugin/compare/v1.5.1...v1.5.2

# v1.5.1 · 2026-09-19

## 新功能与改进

- 新增章节对应管理，支持手动调整匹配、按章获取或重新获取划线和想法，并显示“已获取”状态。
- 优化获取想法时的暂停与断点续传，保留已完成进度。
- 开书不再自动匹配划线位置；仅在章节预下载和预下载划线想法同时开启时，才在后台获取数据。
- 新增独立的本地 Mock 测试模式，方便在 macOS 模拟器和 Kindle 上验证功能。

## What's Changed
* feat: 支持 macOS KOReader 集成测试与局域网 Mock 调试 by @finlater in https://github.com/finlater/weread.koplugin/pull/175


**Full Changelog**: https://github.com/finlater/weread.koplugin/compare/v1.5.0...v1.5.1

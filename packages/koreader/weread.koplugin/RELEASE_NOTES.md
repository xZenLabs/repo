# v1.5.1

## 新功能与改进

- 新增章节对应管理，支持手动调整匹配、按章获取或重新获取划线和想法，并显示“已获取”状态。
- 优化获取想法时的暂停与断点续传，保留已完成进度。
- 开书不再自动匹配划线位置；仅在章节预下载和预下载划线想法同时开启时，才在后台获取数据。
- 新增独立的本地 Mock 测试模式，方便在 macOS 模拟器和 Kindle 上验证功能。

## What's Changed
* feat: 支持 macOS KOReader 集成测试与局域网 Mock 调试 by @finlater in https://github.com/finlater/weread.koplugin/pull/175


**Full Changelog**: https://github.com/finlater/weread.koplugin/compare/v1.5.0...v1.5.1

# v1.5.0

## 新功能与改进

- 重做书架导航，支持书籍分组筛选，优化搜索和刷新体验。
- 整本下载支持断点续传，降低内存占用，并改进进度反馈与取消操作。
- 修复本地书章节匹配与划线刷新问题，减少开书和翻页时的卡顿。
- 修复部分扫码登录失败的问题。
- 自动检查更新的间隔缩短为 1 小时。

感谢 @IswordSun、@vein-cyber 的贡献。

## What's Changed
* fix: match chapters independently of catalog order by @finlater in https://github.com/finlater/weread.koplugin/pull/161
* fix: serialize empty QR login OTP value by @vein-cyber in https://github.com/finlater/weread.koplugin/pull/167
* feat: resume interrupted full-book downloads by @IswordSun in https://github.com/finlater/weread.koplugin/pull/160
* feat: redesign bookshelf navigation with cached book groups by @finlater

## New Contributors
* @vein-cyber made their first contribution in https://github.com/finlater/weread.koplugin/pull/167
* @IswordSun made their first contribution in https://github.com/finlater/weread.koplugin/pull/160

**Full Changelog**: https://github.com/finlater/weread.koplugin/compare/v1.4.2...v1.5.0

# v1.4.2

## 新功能与改进

- 优化划线和想法的拉取速度与进度显示，减少网络请求。
- 提升显示划线和想法时的翻页流畅度。
- 修复清理想法不彻底，以及重新打开书籍后重复匹配的问题。

**Full Changelog**: https://github.com/finlater/weread.koplugin/compare/v1.4.1...v1.4.2

# v1.4.1

## 新功能与改进

- 修复划线和想法的显示状态及章节匹配问题，兼容本地书与微信读书章节编号不一致的情况。
- 降低后台预下载和匹配的内存要求，并修复清理书籍缓存后旧划线想法自动恢复的问题。

**Full Changelog**: https://github.com/finlater/weread.koplugin/compare/v1.4.0...v1.4.1

# v1.4.0

## 新功能与改进

- 统一本地书与微信下载书的划线和想法管理，支持按章匹配、中断续传和同书数据复用。
- 下一章正文及划线想法改为后台预下载，减少阅读时的等待和卡顿。
- 优化公众号图片下载，降低内存占用。
- 修复部分书籍正文不显示、脚注识别异常的问题。

感谢 @baily-zhang、@szey 和 @q107580018 的贡献。

## What's Changed
* fix(footnotes): stop ancestor blocks from poisoning note definitions by @baily-zhang in https://github.com/finlater/weread.koplugin/pull/133
* fix(content): sanitize hostile font-size:0 in server book css by @baily-zhang in https://github.com/finlater/weread.koplugin/pull/137
* refactor(annotations): unify matching and resumable sync by @finlater in https://github.com/finlater/weread.koplugin/pull/150
* fix(mp): stream public-account article images to disk by @szey in https://github.com/finlater/weread.koplugin/pull/132

## New Contributors
* @szey made their first contribution in https://github.com/finlater/weread.koplugin/pull/132

**Full Changelog**: https://github.com/finlater/weread.koplugin/compare/v1.3.1...v1.4.0

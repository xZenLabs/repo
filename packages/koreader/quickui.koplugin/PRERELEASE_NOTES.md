# v1.1.1-beta.1

## 更新说明
> 修复底部栏一些问题
- 底部栏: 阅读界面由原来的直接替换原生footer改为与原生footer共存，上下排布（保持与Menu patch一致）
- 底部栏: 取消勾选“在阅读器中显示”时立即清除底栏触摸区域（避免误触）而非等到重排结束才彻底清除
- 底部栏:  仅当底栏高度发生变化时才重排，修复打开书籍时闪烁一下的问题
- 底部栏: 修复从阅读界面返回simpleui主屏幕后移除或添加底栏按钮无法立即更新的问题

# v1.1.0-beta.4

### 更新说明
>非 Reader 界面的底栏注入改为"寄生"在 Menu 自身的 footer 里，不再从外面包裹整个 widget 树。
- 底部栏：重构底部栏注入方式-由包裹 widget 改为寄生在Menu 自身的 footer 里，彻底解决底栏丢失及与simpleui重复包裹时机先后的问题
- 书库封面：添加对内置依赖插件coverbrowser的前置检查，避免因coverbrowser未启用导致插件其他功能也无法使用。
- 兼容性：可搭配本人仓库[simpleui v2.7.1-b](https://github.com/gytwo/simpleui.koplugin/releases/tag/v2.7.1-b)使用

# v1.1.0-beta.3

## 更新说明
>底栏从"包裹替换 ReaderView"改为"寄生在 ReaderFooter 上"，与 KOReader 原生状态栏机制保持一致
- 底部栏：修复进入阅读界面闪烁、进度错位问题
- 底部栏：修复旋转、全屏切换等情形下偶尔底部栏丢失的问题（set Dirty)

# v1.1.0-beta.2

## 更新说明
- 侧边栏: 增加侧边栏快捷菜单（竖滑翻页、横滑拖动，长按按钮-编辑，长按上翻页-设置，长按下翻页-动作池，无按钮数量限制)
- 快捷操作: 优化（阅读器、UI字体切换、页眉页脚）字体列表-字体预览、最近排序、选中最前
- 快捷操作: 添加阅读滑块（字号、间距、样式微调等）的内置动作/手势操作-长按滑块弹出滑块列表（勾选以添加至顶部面板）、长按右侧数值重置为默认、长按左边标签弹出阅读滑块或重置为默认
- 快捷操作: 添加更多流行插件的内置动作（到动作池中添加至顶部面板/底部栏/侧边栏）
- 快捷操作: 给依赖插件的内置动作做前置检查-不可用会在动作池列表显示为灰，全选添加会自动过滤排除，顶部面板/底部栏/侧边栏按钮自动过滤排除
- 快捷操作: 在顶部面板/底部栏/侧边栏彻底删除某动作时联动删除其他栏上的相同动作按钮（避免空引用）
- 顶部面板: 修复点击顶部弹出菜单时误触前光滑块、重构滑块菜单（长按滑块以添加更多阅读滑块至顶部面板）
- 顶部面板: 添加分页行（默认3行1页，行上按钮可快速切换按钮形状、显/隐标签、一页几行，可隐藏、可滑动翻页），移除最大66个的数量限制
- 书库封面: 给进度为0%和100%的书籍也添加进度徽章
- 书库封面: 支持识别simpleui虚拟文件夹（作者/系列/标签）路径中的书籍图片从而正确绘制虚拟文件夹封面（封面网格&图片列表均适用）
- 页眉页脚: 阅读界面显示底部栏时自动隐藏页脚
- 底部栏：搜素结果界面也显示底部栏
- 底部栏：添加阅读器界面显示/隐藏底部栏的手势操作
- 其他: 完善中文翻译

# v1.1.0-beta.1

## What's Changed

- Vertical Bar: add vertical bar as quick menu (swipe to page or move,long-press to edit/add buttons, open the settings menu)
- Quick Actions: improve the font list both in Font List、UI Font Switcher&HF font (font preview + recently-selected sorting)
- Quick Actions: add reader sliders as built-in action and dispatcher action(long-press to bring up a settings dialog, check the box to add it to the panel)
- Quick Actions: add more built-in actions for popular koplugins(find them in actio pools)
- Quick Actions: cascade-delete custom action from all bars to avoid orphaned ids
- Panel: fix accidental touch issue in slider and refactor the slider menu(long-press slider to add more)
- Panel: add pagination (default 3 rows per page-can be changed by tab +/-) with chevron pager and swipe to flip pages; remove the 66-button cap
- Cover: show status icons on the progress badge at 0% and 100%
- Cover: support SimpleUI virtual paths for folder covers (Mosaic & List)
- Header & Footer: hide footer while the QuickUI bottom bar is shown in the reader
- Bottom bar: inject into FileManager via FileManager.setupLayout (one-shot injection)
- Bottom bar: show on filesearch results screen
- Bottom bar: add dispatcher action-toggle bottom bar in reader
- i18n: improve Chinese translation

# assistant_zh.koplugin — KOReader AI 助手中文适配版

基于 [assistant.koplugin](https://github.com/omer-faruq/assistant.koplugin) 的中文适配分支，主要面向中文用户：

- **提示词全中文**：所有内置提示词（翻译、摘要、词典、X-Ray、Recap、书籍信息等）均已汉化，回复语言跟随 KOReader 界面语言（或「AI 回复语言」设置）。
- **联网搜索走 DeepSeek**：使用 DeepSeek 官方 Responses API 的**服务端原生联网搜索**（`web_search` 工具），不需要 SerpAPI / Tavily / SearXNG / Exa 等任何第三方搜索 API 密钥。
- **中文语境分析**：为词典 / Term X-Ray 的 LexRank 算法新增了中文语言模块（bigram 分词、中文停用词、全角句读「。！？；」分句），分析中文书效果更好。
- **插件已改名**：目录名与元数据均为 `assistant_zh`，可与原版并存，互不干扰（菜单设置键、设置文件均已隔离）。

## 安装

1. 下载发行版 zip：`assistant_zh.koplugin-v1.14.zip`
2. 解压后把 **`assistant_zh.koplugin`** 文件夹放入 KOReader 的 `plugins/` 目录（与 KOReader 程序文件同级；若同时装有原版 `assistant.koplugin`，两者互不影响）
3. 重启 KOReader

> 发行版 zip **不包含** `configuration.lua`（见下方「发行版说明」），首次使用前需自行创建。

## 配置

### 1. 创建配置文件

把插件目录内的 `configuration.sample.lua` 复制一份，改名为 `configuration.lua`，然后编辑它：

```bash
cp configuration.sample.lua configuration.lua
```

### 2. 填入 DeepSeek API Key

默认提供商是 `responses_deepseek`（DeepSeek Responses API，支持原生联网搜索），在 `configuration.lua` 中找到并填入你的 Key：

```lua
responses_deepseek = {
    default = true,
    visible = true,
    model = "deepseek-v4-flash",          -- 按你的账户可用模型调整
    base_url = "https://api.deepseek.com",
    api_key = "sk-你的DeepSeek密钥",      -- ← 在这里填
    additional_parameters = {
        temperature = 0.7,
        max_output_tokens = 16384,        -- 重要：DeepSeek 推理模型的「推理 token」也计入此预算。
                                          -- X-Ray / Recap 等重任务推理量可达 1.5 万+ token，
                                          -- 设为 4096 会在推理阶段就被截断、正文为空（报"未收到回复"）。
                                          -- 建议 >= 16384。
    }
},
```

### 3. 启用 DeepSeek 联网搜索

KOReader 菜单 → 工具 → AI Assistant → 设置 → **网络搜索** → 选择 **「模型内置」（builtin）**。

启用后，凡是需要联网的提示词（维基百科、解释、书籍信息、Recap 等，带 🌐 图标）都会由 **DeepSeek 服务端直接执行搜索**，无需任何第三方搜索 API 密钥。

### 4. 回复语言（可选）

插件设置 → **AI 回复语言**：留空则跟随 KOReader 界面语言；建议填 `简体中文`。

## 发行版说明

- `dist/assistant_zh.koplugin-v1.14.zip` 为正式发行包，**已排除本地配置文件 `configuration.lua`（其中可能包含真实 API Key）**，仅保留占位符 `configuration.sample.lua`。
- 收到 zip 的用户需按上文「配置」自行创建 `configuration.lua` 并填入自己的 Key。
- OTA 更新已指向本仓库（`Kerwin75631591/assistant_zh.koplugin`）的最新 Release：插件启动时会检查 release tag（如 `v1.14-zh`）并与本地版本比较，有新版本时通过 GitHub 源码归档下载安装，`configuration.lua` 会保留。
- 如需关闭更新检查，设置 `updater_disabled = true`。

## 开发 / 测试

本地开发目录保留完整的 `configuration.lua`（含真实 API Key）用于测试，**不要提交到 git**（`.gitignore` 已排除 `assistant_zh.koplugin/configuration.lua`）。

修改代码后可用以下方式快速校验 Lua 语法（需 Node.js + luaparse）：

```bash
cd assistant_zh.koplugin
node -e "const p=require('luaparse');const fs=require('fs');fs.readdirSync('.').filter(f=>f.endsWith('.lua')).forEach(f=>{try{p.parse(fs.readFileSync(f,'utf8'),{luaVersion:'5.1'});console.log('OK',f)}catch(e){console.log('FAIL',f,e.message)}})"
```

## 与上游版本的差异

| 项目 | 上游 assistant.koplugin | 本分支 assistant_zh.koplugin |
| --- | --- | --- |
| 提示词语言 | 英文 | 全中文 |
| 联网搜索 | 需第三方搜索 API（SerpAPI 等）或各厂商内置 | 默认 DeepSeek 服务端原生联网搜索 |
| 中文语境分析 | 无中文分词模块 | 新增中文 LexRank 模块 + 中文分句 |
| 插件标识 | `assistant` | `assistant_zh`（可并存） |
| 界面语言 | 多语言（含中文） | 中文翻译已同步补全 |

## 许可证

[GPL-3.0](assistant_zh.koplugin/LICENSE)（与上游一致）。

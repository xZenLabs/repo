# v1.14-zh · 2026-08-13

KOReader AI 助手中文适配版

**功能特性**
- 全部提示词汉化（翻译/摘要/词典/X-Ray/Recap/书籍信息等）
- 联网搜索走 DeepSeek 服务端原生联网搜索（Responses API，设置中选择「模型内置」即可，无需第三方搜索 API 密钥）
- 新增中文 LexRank 分词模块与中文分句支持，分析中文书效果更好
- 插件改名 assistant_zh，可与原版并存
- OTA 更新已指向本仓库最新 Release

**注意**
- 发行版 zip **不含 configuration.lua**，安装后请复制 configuration.sample.lua 为 configuration.lua，填入你的 DeepSeek API Key
- **重要**：`responses_deepseek.max_output_tokens` 建议 **≥16384**（DeepSeek 推理 token 计入该预算，4096 会导致 X-Ray 等重任务在推理阶段被截断、正文为空、报"未收到回复"）
- 详细安装与配置见包内 README.md

**v1.14-zh（2026-08-14）**
- 修复：X-Ray / Recap 等重任务报"未收到回复"（max_output_tokens 对 DeepSeek 推理模型过小，4096 → 16384）
- Responses 内置 web_search 增加 max_uses=5 限制搜索次数
- OTA 更新地址指向本仓库；仓库结构调整为插件即仓库根，源码归档可直接 OTA 安装
- 版本号与 release tag 统一为 v1.14-zh

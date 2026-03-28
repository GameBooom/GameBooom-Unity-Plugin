# Changelog

## 0.1.6

### Added
- Added structured working-memory summaries and safer context compression so long Unity sessions keep more relevant project state while reducing chat history bloat.
- 新增结构化工作记忆摘要和更安全的上下文压缩机制，让长时间 Unity 会话在减少聊天历史膨胀的同时保留更多关键项目状态。
- Added MCP tool export profiles (`minimal` / `default` / `full`) with clearer external tool descriptions for different client needs.
- 新增 MCP 工具导出档位（`minimal` / `default` / `full`），并为外部客户端提供更清晰的工具描述分层。

### Improved
- Improved GameBooom UI consistency with a cleaner modernized chat/settings/MCP presentation, real message virtualization, and better large-message handling.
- 优化 GameBooom 的整体 UI 一致性，带来更现代简洁的聊天、设置和 MCP 界面，以及真正的消息虚拟化与更好的长文本处理体验。
- Improved MCP stability and external-client behavior by tightening tool exposure defaults, reducing duplicate write loops, and hardening main-thread request handling.
- 优化 MCP 稳定性与外部客户端行为，收紧默认工具暴露范围，降低重复写操作循环，并加强主线程请求处理。

### Fixed
- Fixed scene tool failures on inactive objects by updating core object lookup paths used by activate/delete/rename/select/focus and related helpers.
- 修复场景工具在未激活对象上的失效问题，更新 activate/delete/rename/select/focus 及相关辅助能力所使用的核心对象查找路径。
- Fixed long assistant responses collapsing back to preview immediately after clicking `Render` in the chat window.
- 修复聊天窗口中长文本助手消息点击 `Render` 后只短暂展开又立刻恢复预览的问题。
- Fixed missing or partially invalid styles in newly installed projects by adding stylesheet loading fallbacks for both `Assets` and UPM package layouts.
- 修复插件安装到新项目后样式表缺失或部分样式失效的问题，为 `Assets` 和 UPM package 两种布局增加样式加载兜底。
- Fixed subscription-state flicker on plugin restart by reading cached subscription info first and only refreshing UI when backend subscription data actually changes.
- 修复插件重启时订阅状态闪烁的问题，先读取缓存订阅信息，并仅在后端订阅数据真实变化时刷新 UI。

## 0.1.5

### Added
- Added project-scoped MCP one-click configuration entries so multiple Unity projects can coexist in external MCP clients.
- 新增按项目隔离的 MCP 一键配置条目，让多个 Unity 项目可以在外部 MCP 客户端中并行共存。
- Added project-aware MCP identity labels in server info, resources, and prompts to reduce cross-project tool selection mistakes.
- 新增带项目标识的 MCP server、resource 和 prompt 信息，降低多项目并行时选错项目的概率。

### Improved
- Improved subscription parsing compatibility with the updated backend response, including current_subscription, platform tier fallback, and wrapped payload handling.
- 优化新版后端订阅接口兼容性，补齐 current_subscription、平台订阅兜底和包裹式响应结构解析。
- Improved account upgrade and top-up flows by unifying all subscription-related entry points to the pricing page.
- 优化订阅升级与充值入口，将所有相关跳转统一到定价页面。
- Improved tool selection stability by reducing exposed tool count from 102 to 100 and hiding low-value visual-only actions.
- 优化工具选择稳定性，将暴露工具数从 102 个压到 100 个，并隐藏低价值的纯视觉反馈工具。

### Fixed
- Fixed incorrect Free-tier display for Ultra users when the backend returns global or platform-scoped subscription data.
- 修复后端返回全局或平台级订阅数据时，Ultra 用户在插件中仍显示为 Free 的问题。
- Fixed MCP configuration collisions between projects by separating per-project config keys and default ports.
- 修复多个项目之间的 MCP 配置冲突问题，改为按项目隔离配置键和默认端口。
- Fixed PackyAPI fallback behavior by forcing packyapi.com custom endpoints to use the OpenAI Responses protocol instead of chat completions.
- 修复 PackyAPI 的协议回退问题，强制对 packyapi.com 自定义接口使用 OpenAI Responses 协议，而不是 chat completions。


## 0.1.4

### Added
- Added MCP resources, resource templates, and prompts so Codex and other MCP clients can discover more useful Unity context.
- 新增 MCP resources、resource templates 和 prompts，让 Codex 与其他 MCP 客户端可以发现更多有价值的 Unity 上下文。
- Added cached attachment snapshots for image and text files to keep chat and session recovery independent from the original file paths.
- 新增图片和文本附件的缓存副本机制，使聊天与会话恢复不再依赖原始文件路径。
- Added higher-level Unity workflow helpers, including smarter reference auto-wiring and built-in runtime validation templates for common prototype checks.
- 新增更高阶的 Unity 工作流辅助能力，包括更智能的引用自动绑定和常用原型检查的内置运行时验证模板。

### Improved
- Improved custom API compatibility for OpenAI Responses-based providers such as PackyAPI while preserving tool calling in compatible flows.
- 优化基于 OpenAI Responses 的自定义 API 兼容性，适配 PackyAPI 等提供方，并在兼容流程中保留工具调用能力。
- Improved AI workflow quality for Unity prototyping, including stronger orchestration around scene setup, validation, and repeated write-action handling.
- 优化 Unity 原型开发的 AI 工作流质量，增强场景搭建、结果验证和重复写操作处理的编排能力。
- Improved release packaging consistency with unified package versioning and versioned commercial DLL output naming.
- 优化发布打包一致性，统一 package 版本来源，并采用带版本号的商业 DLL 输出命名。

### Fixed
- Fixed repeated write-operation loops from some models by blocking duplicate write actions and surfacing follow-up inspection suggestions.
- 修复部分模型出现重复写操作循环的问题，通过拦截重复写入并提供后续检查建议来降低误操作风险。
- Fixed scene safety gaps by saving the current scene before creating new scenes and before entering Play Mode.
- 修复场景安全问题，在创建新场景前和进入 Play Mode 前会先保存当前场景。
- Fixed MCP main-thread access issues by moving Unity state sampling to cached main-thread snapshots and enabling keep-alive only while requests are active.
- 修复 MCP 的主线程访问问题，将 Unity 状态采样改为主线程缓存快照，并仅在有请求进行时启用 keep-alive。

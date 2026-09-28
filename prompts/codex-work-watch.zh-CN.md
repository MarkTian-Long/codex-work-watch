# Codex Work Watch Prompt

目标：监控 Codex / ChatGPT Work 的实际状态变化。

## 默认原则

除非达到阈值，否则静默。

监控层保持技术深度；通知层优先使用非开发者也能快速理解的产品/使用语言。完整规则见 `policies/user-facing-output.md`。

## P0

每轮检查：

- Tibo public updates
- OpenAI Status
- OpenAI Help
- Codex releases
- pricing and entitlement docs
- GitHub issues
- recent community evidence

## 判断

必须区分：

- teaser
- announcement
- rollout-start
- completion

第三方只能发现线索，不能确认官方状态。

## 禁止

- 不把单个用户报告当官方事件；
- 不把 CLI release 推导为 Desktop/Work；
- 不猜测 root cause；
- 不把 speculation 写成事实。

## 输出

只有发生：

- official change
- shipped feature
- scope change
- rollback/restore
- lifecycle upgrade

才输出通知。

### 面向用户的表达

通知默认按以下顺序组织：

1. 发生了什么；
2. 对实际使用有什么影响；
3. 是否需要升级、回退、等待或无需操作；
4. 证据强度，以及是否已经被 OpenAI 官方确认。

Reset / 额度 / 模型消息优先回答：是否真的重置、覆盖谁、何时生效/是否完成、对当前可用额度的直接影响。

版本修复消息优先回答：是否已修好、哪个版本可用、哪些平台受影响、是否需要升级或回退。

不要让 cursor、Snowflake ID、A3/B+B、SIGCHLD、libuv、RPC、daemon、thread_hydration 等内部监控或底层术语占据主叙事。默认只在末尾用一句话补充必要技术机制；用户追问时再展开完整证据链。

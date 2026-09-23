# Codex Work Watch Prompt

目标：监控 Codex / ChatGPT Work 的实际状态变化。

## 默认原则

除非达到阈值，否则静默。

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

# Codex Work Watch

High-signal monitoring workflow for Codex and ChatGPT Work availability, routing, credits, capacity and reset lifecycle.

## Purpose

Codex Work Watch is not a news aggregator. It monitors when the product state actually changes.

The workflow focuses on:

- usage limits and credit mechanisms;
- model availability and routing behavior;
- Codex / ChatGPT Work incidents;
- reset lifecycle (teaser → announcement → rollout → completion);
- stable releases and shipped features.

The default behavior is silent. Notifications are generated only when evidence reaches predefined thresholds.

## Design principles

1. Official sources > maintainers > issue evidence > community reports.
2. Third-party trackers are discovery tools, not final authority.
3. Same reporter or same mechanism follow-ups do not automatically create independent evidence.
4. CLI stable releases do not imply Desktop or Work availability.
5. A rollout stage must not be promoted without evidence.
6. Internal verification can be technical; user-facing alerts should explain product impact first.

## Notification style

The workflow intentionally separates **evidence depth** from **notification complexity**.

Internally it may inspect GitHub issues, logs, version metadata, controlled A/B evidence, routing traces and low-level runtime mechanisms. Externally it should first explain:

1. what changed;
2. what it means for actual usage;
3. whether the user should act, wait, update, roll back, or do nothing;
4. whether the conclusion is officially confirmed or supported by independent evidence.

For reset / quota / model changes, lead with whether the reset happened, who is covered, when it takes effect, whether rollout is complete, and what changes for usable allowance.

For regressions and fixes, lead with whether the issue is fixed, the affected platform/version, and the recommended user action. Low-level details such as process signals, RPC errors or internal confidence labels belong in a short technical note or a follow-up when requested.

See `policies/user-facing-output.md`.

## Repository structure

```text
prompts/       execution prompt
policies/      evidence, notification and presentation rules
state/         runtime state schema
automations/   scheduler reference
docs/          architecture and usage
```

## Runtime model

This repository stores the workflow definition, not live account state.

The running automation remains independent from GitHub. Future versions may optionally check repository versions before execution.

## Quick start

1. Read `AGENTS.md`.
2. Read `manifest.yaml`.
3. Use `prompts/codex-work-watch.zh-CN.md` as the monitoring instruction.
4. Apply `policies/user-facing-output.md` before presenting any alert.
5. Keep runtime cursor/state outside the repository.

License: MIT

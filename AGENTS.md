# AGENTS.md

## Entry procedure

1. Read `manifest.yaml`.
2. Read the selected prompt completely.
3. Respect evidence policies before producing notifications.
4. Apply `policies/user-facing-output.md` before presenting any notification.

## Rules

- Default output is silent.
- Never convert community speculation into official status.
- Preserve distinction between announcement, rollout-start and completion.
- Do not infer Desktop/Work availability from CLI releases.
- Do not infer root causes without official confirmation.
- Maintain monotonic cursors.
- Third-party trackers are for discovery only.
- Keep technical depth inside the evidence process; present user impact first.

## Notification philosophy

A notification requires one of:

- official mechanism change;
- official acknowledgement;
- scope expansion or contraction;
- stable/service shipped;
- rollback or restore;
- lifecycle stage upgrade.

When a notification is triggered, explain what changed and what the user should expect before exposing implementation detail.

## Source priority

1. OpenAI official pages/status/help.
2. Tibo or maintainer statements.
3. GitHub issues/releases.
4. Community evidence.

Community evidence can create investigation state but not official state.

# User-facing Output Policy

## Principle

Keep the monitoring layer technically rigorous, but keep notifications understandable to a non-developer.

The system may use GitHub issues, release metadata, logs, controlled A/B evidence, internal confidence classes, cursor state, routing traces, or low-level runtime mechanisms to make a decision. Those details should not dominate the user-facing message unless they materially change what the user should do.

## Default notification order

Every notification should answer these questions in this order:

1. What changed?
2. What does it mean for actual Codex / ChatGPT Work usage?
3. Does the user need to act, wait, upgrade, roll back, or do nothing?
4. How strong is the evidence, and has OpenAI officially confirmed it?

## Reset / quota / model notifications

Lead with:

- whether a reset actually happened;
- who is covered;
- when it starts and whether rollout is complete;
- what changes for the user's currently usable allowance;
- whether the information is official, inferred, or community-supported.

Do not lead with cursor IDs, tracker state, Snowflake IDs, internal threshold labels, or implementation details.

## Release / fix notifications

Lead with:

- whether the problem is fixed;
- which version contains the fix;
- which platforms are affected;
- whether the user should update, roll back, or wait.

Only then add implementation detail if it helps explain the decision.

## Incidents and regressions

Translate technical symptoms into usage impact first.

Preferred:

> Some Linux Desktop users can get stuck when opening or starting Codex tasks. Rolling back to the previous build has restored functionality in several independent reports. There is strong technical evidence for a common startup-process problem, but OpenAI has not confirmed the root cause yet.

Avoid starting with:

> SIGCHLD / libuv / zombie child / thread_hydration / B+B ...

## Community technical evidence

When OpenAI has not confirmed the mechanism, use language such as:

- "multiple independent reports support the same mechanism";
- "the evidence currently points to";
- "this has not yet been confirmed by OpenAI".

Do not present community reverse engineering as an official root cause.

## Technical appendix

Keep low-level details to one short final sentence by default.

Expand the full evidence chain only when:

- the mechanism materially changes the user's decision;
- there is disagreement about the conclusion;
- the user explicitly asks for technical details, issue links, logs, or evidence.

## Length

Default notifications should usually fit in 2–4 short paragraphs. Precision should come from evidence quality, not from exposing every internal monitoring detail.

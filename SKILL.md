---
name: codex-work-watch
description: Monitor Codex and ChatGPT Work availability, routing, credits, releases and reset lifecycle with evidence thresholds.
---

# Codex Work Watch

Use this repository as a monitoring workflow definition.

When invoked:

1. Read manifest.yaml.
2. Load monitoring prompt.
3. Apply evidence policies.
4. Notify only when thresholds are reached.
5. Translate technical evidence into user-impact language before presenting the alert.

Never produce routine status noise.

Keep low-level technical evidence available for verification, but do not make it the default user-facing narrative.

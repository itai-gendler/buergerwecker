---
appliesTo:
- type: entity
  id: email-subscription
  facts:
  - Cadence
- type: entity
  id: app-alert
  facts:
  - Cadence
references:
- kind: code
  role: implementation
  target: app/cycle.py#adaptive_rate_limit_minutes
- kind: code
  role: implementation
  target: app/cycle.py#run_cycle
- kind: code
  role: implementation
  target: app/repo.py#update_filter
---

# Digest spacing grows with abundance or a continuing stream

The configured interval is a floor. At the last successful digest, up to 2 matching slots keep multiplier 1; up to 5 use 2; up to 15 use 4; more use 8. Consecutive digests use multipliers 1, 2, 4, then 8 for streaks of at most 1, 2, 3 and more. The greater multiplier applies, bounded by the configured maximum. Silence lasting twice the earned interval resets the streak. Editing resets both signals, preserving last delivery time.

---
appliesTo:
- type: entity
  id: email-subscription
  effect: removes
permits:
- unattended: true
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_purge_hard
---

# Only retention processing erases ended email subscriptions

Final erasure follows the ended-data retention period.

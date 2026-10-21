---
appliesTo:
- type: entity
  id: email-delivery
  effect: removes
permits:
- unattended: true
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_prune_suppressions
---

# Retention removes obsolete delivery standing

Complaint retention uses its configured clock; other delivery records follow the last associated subscription.

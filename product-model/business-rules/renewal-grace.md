---
appliesTo:
- type: entity
  id: email-subscription
- type: entity
  id: app-alert
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_soft_delete_expired
- kind: code
  role: implementation
  target: app/housekeeping.py#_purge_hard
---

# Expired searches pause before they end

At expiry, digests stop. A retained expired search can be renewed during the configured grace period, normally 14 days. It is then ended and permanently erased after another 30 days.

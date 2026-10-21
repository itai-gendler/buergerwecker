---
availability:
- place: website::subscription
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_soft_delete_expired
domain: subscriptions
---

# End expired subscription

End expired searches after their renewal grace period so their old renewal links no longer revive them.

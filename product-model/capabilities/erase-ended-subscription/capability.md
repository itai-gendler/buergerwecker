---
availability:
- place: website::subscription
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_purge_hard
- kind: code
  role: implementation
  target: app/db.py
domain: subscriptions
---

# Erase ended subscription

Permanently remove ended subscriptions after 30 days, together with their associated delivery and seen-slot records.

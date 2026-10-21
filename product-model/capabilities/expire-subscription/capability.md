---
availability:
- place: website::subscription
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/repo.py#active_subscriptions
- kind: code
  role: implementation
  target: app/api.py#_sub_json
- kind: code
  role: implementation
  target: app/web.py#manage_route
domain: subscriptions
---

# Expire subscription

Pause appointment notifications when a saved search reaches its end date. The expired search is kept, and renewable, for the configured grace period.

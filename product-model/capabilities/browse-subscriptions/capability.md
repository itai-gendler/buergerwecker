---
availability:
- place: website::subscription
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/web.py#manage_route
- kind: code
  role: implementation
  target: app/api.py#list_subscriptions
- kind: code
  role: implementation
  target: client/www/screens/subs.js
domain: subscriptions
---

# Browse subscriptions

Read the selected email request through its management link, or the current phone’s active and expired alerts. The mobile list reloads on launch and resume.

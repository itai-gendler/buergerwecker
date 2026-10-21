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
  target: app/api.py#update_subscription
- kind: code
  role: implementation
  target: app/repo.py#update_filter
- kind: code
  role: implementation
  target: client/www/screens/form.js
domain: subscriptions
---

# Edit subscription

Replace the service, offices and time preferences within the same city. Editing resets abundance and consecutive-digest cadence; it does not clear delivery history or restart the ordinary term.

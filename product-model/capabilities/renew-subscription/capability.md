---
availability:
- place: website::subscription
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/web.py#renew_route
- kind: code
  role: implementation
  target: app/api.py#renew
- kind: code
  role: implementation
  target: app/repo.py#renew_subscription
- kind: code
  role: implementation
  target: client/www/screens/subs.js
domain: subscriptions
---

# Renew subscription

Keep looking starts another term from now, including for an expired request still retained within its grace period. Admission is checked again and the current check-in is reset.

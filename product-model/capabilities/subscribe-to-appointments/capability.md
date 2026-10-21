---
availability:
- place: website::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/web.py#subscribe
- kind: code
  role: implementation
  target: app/api.py#create_subscription
- kind: code
  role: implementation
  target: app/signup.py#build_filter
- kind: code
  role: implementation
  target: client/www/screens/form.js
domain: subscriptions
---

# Subscribe to appointments

Save one selected service and appointment filter. Web sign-ups await email confirmation; mobile alerts start after device setup. The mobile service is offered when enabled.

---
availability:
- place: mobile-app::public
references:
- kind: code
  role: implementation
  target: client/www/push.js
- kind: code
  role: implementation
  target: client/www/screens/onboarding.js
- kind: code
  role: implementation
  target: client/www/screens/verify.js
- kind: code
  role: implementation
  target: app/api.py#register
- kind: code
  role: implementation
  target: app/api.py#device_verify
---

# Set up push notifications

Register the phone and acknowledge a setup push before using alerts. Permission denial still leaves city browsing available. Registration, verification and Resend are parts of this one setup outcome. Offered when the mobile service is enabled.

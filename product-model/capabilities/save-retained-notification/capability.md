---
availability:
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: client/www/inbox.js#record
- kind: code
  role: implementation
  target: client/www/inbox.js#harvest
- kind: code
  role: implementation
  target: client/www/app.js#onNotification
domain: notifications
---

# Save retained notification

Keep slot and check-in pushes that the app observes, whether received in the foreground, tapped or still present in the system notification area on launch or resume. Setup pushes are handled by verification instead.

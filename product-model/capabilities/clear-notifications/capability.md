---
availability:
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: client/www/inbox.js#clear
- kind: code
  role: implementation
  target: client/www/screens/inbox.js
domain: notifications
---

# Clear notifications

Remove retained entries from the local list. Clearing does not end the related alerts.

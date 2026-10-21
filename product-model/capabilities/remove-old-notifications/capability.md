---
availability:
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: client/www/inbox.js#add
- kind: code
  role: implementation
  target: client/www/inbox.js#sanitize
domain: notifications
---

# Remove old notifications

Keep at most the newest 50 locally observed notifications and remove entries older than 30 days during list loading and recording.

---
availability:
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: client/www/screens/inbox.js
- kind: code
  role: implementation
  target: client/www/inbox.js
domain: notifications
---

# Browse notifications

Read the phone’s retained slot and check-in entries, newest first. Opening the list marks its current entries read and updates the unread count.

---
appliesTo:
- type: entity
  id: retained-notification
references:
- kind: code
  role: implementation
  target: client/www/inbox.js
- kind: code
  role: implementation
  target: client/www/screens/inbox.js
---

# Retained notifications are local and bounded

Only observed slot and check-in pushes enter the local list. It retains at most 50 entries for 30 days, newest first. Repeated receipt, tap and system-area copies are deduplicated; setup pushes do not appear. Opening the list marks its current entries read; clearing it does not stop an alert.

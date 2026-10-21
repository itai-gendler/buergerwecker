---
appliesTo:
- type: entity
  id: retained-notification
  effect: creates
permits:
- unattended: true
references:
- kind: code
  role: implementation
  target: client/www/inbox.js#record
---

# Only observed pushes populate notification history

The product records slot and check-in pushes it actually observes on this installation.

---
appliesTo:
- type: entity
  id: retained-notification
  effect: changes
permits:
- related:
  - verb: keeps
    entity: resident
- unattended: true
references:
- kind: code
  role: implementation
  target: client/www/inbox.js
---

# Residents mark read their own retained notifications

The notification list belongs to the phone on which it was observed. Automatic retention and app-data deletion may remove entries.

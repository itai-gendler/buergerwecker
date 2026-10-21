---
appliesTo:
- type: entity
  id: email-subscription
  effect: reads
permits:
- related:
  - verb: holds
    entity: resident
- unattended: true
references:
- kind: code
  role: implementation
  target: app/web.py#manage_route
- kind: code
  role: implementation
  target: app/tokens.py#verify
---

# Only the email-link holder reads a subscription

The holder presents a valid link for the requested action on this subscription. The service reads saved facts to carry out confirmation, delivery and lifecycle work.

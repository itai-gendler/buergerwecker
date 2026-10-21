---
appliesTo:
- type: entity
  id: email-subscription
  effect: creates
permits:
- actors:
  - resident
references:
- kind: code
  role: implementation
  target: app/web.py#subscribe
---

# Residents may request email subscriptions

A resident may save an offered selection. A complaint-suppressed address is directed to contact the operator; sign-up and address allowances apply before saving.

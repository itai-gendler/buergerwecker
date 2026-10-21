---
appliesTo:
- type: entity
  id: delivery-history
  effect: reads
permits:
- actors:
  - operator
- unattended: true
references:
- kind: code
  role: implementation
  target: app/web.py#admin_route
---

# Only the operator reads delivery history

Operational history is presented in administration and service-generated operator notices.

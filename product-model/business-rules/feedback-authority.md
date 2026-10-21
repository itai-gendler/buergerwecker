---
appliesTo:
- type: entity
  id: email-delivery
  effect: changes
permits:
- actors:
  - mail-provider
  when:
  - entity: service-settings
    fact: Feedback enabled
    is: true
- unattended: true
references:
- kind: code
  role: implementation
  target: app/web.py#webhook_route
- kind: code
  role: implementation
  target: app/webhooks.py#apply_events
---

# Only configured mail-provider feedback changes delivery standing

The inbound provider request must satisfy the configured provider authentication before an event can be applied.

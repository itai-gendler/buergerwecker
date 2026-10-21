---
appliesTo:
- type: entity
  id: email-subscription
  effect: changes
permits:
- related:
  - verb: holds
    entity: resident
- unattended: true
- actors:
  - mail-provider
  when:
  - entity: service-settings
    fact: Feedback enabled
    is: true
references:
- kind: code
  role: implementation
  target: app/web.py
- kind: code
  role: implementation
  target: app/webhooks.py#apply_events
- kind: code
  role: implementation
  target: app/housekeeping.py
---

# Email-link holders and delivery processes change email subscriptions

The resident uses the subscription’s link for the requested purpose: confirm, manage, renew or unsubscribe. Scheduled delivery and retention may change it; configured provider feedback can end the address’s subscriptions.

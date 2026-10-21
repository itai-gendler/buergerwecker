---
appliesTo:
- type: entity
  id: app-alert
  effect: reads
permits:
- related:
  - verb: owns
    entity: push-device
  - verb: uses
    entity: resident
  when:
  - entity: service-settings
    fact: App available
    is: true
  - entity: push-device
    fact: Verification
    is: true
- unattended: true
references:
- kind: code
  role: implementation
  target: app/api.py#_own
- kind: code
  role: implementation
  target: app/api.py#list_subscriptions
---

# Verified device holders read their own app alerts

A device holder reads only that device’s non-ended alerts while the app is enabled. Scheduled notification work may read the selections it serves.

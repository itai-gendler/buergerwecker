---
appliesTo:
- type: entity
  id: app-alert
  effect: creates
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
references:
- kind: code
  role: implementation
  target: app/api.py#create_subscription
- kind: code
  role: implementation
  target: app/api.py#_share_refusal
---

# Verified device holders create app alerts

The app must be enabled and the requesting device verified. Creating an alert is limited to ten non-ended alerts per device, three per city and three distinct services per device per city, with expired-but-renewable alerts included in those device counts, together with city capacity.

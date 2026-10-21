---
appliesTo:
- type: entity
  id: free-slot
  effect: reads
  contexts:
  - place: mobile-app::device
permits:
- related:
  - verb: provides access to
    entity: app-alert
  - verb: owns
    entity: push-device
  - verb: uses
    entity: resident
  when:
  - entity: app-alert
    fact: Active
    is: true
  - entity: push-device
    fact: Verification
    is: true
  - entity: service-settings
    fact: App available
    is: true
- unattended: true
references:
- kind: code
  role: implementation
  target: app/api.py#city_slots
---

# Active city-alert holders read the city’s available appointments

The app and widget read observations through the verified device’s active alert in that city. Sensitive-service observations require that device’s own active alert for the service. The product may read observations unattended for polling and delivery.

---
appliesTo:
- type: entity
  id: app-alert
  effect: changes
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
  target: app/api.py#update_subscription
- kind: code
  role: implementation
  target: app/api.py#renew
- kind: code
  role: implementation
  target: app/api.py#delete_subscription
- kind: code
  role: implementation
  target: app/housekeeping.py
---

# Verified device holders and lifecycle processes change app alerts

Editing, renewing and stopping require the owning verified device while the app is enabled. Renewal repeats the applicable city admission checks. Scheduled delivery, expiry and device retirement may change their corresponding facts or lifecycle state.

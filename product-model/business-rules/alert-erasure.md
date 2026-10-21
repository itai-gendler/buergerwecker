---
appliesTo:
- type: entity
  id: app-alert
  effect: removes
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
- unattended: true
references:
- kind: code
  role: implementation
  target: app/repo.py#delete_device
- kind: code
  role: implementation
  target: app/housekeeping.py#_purge_hard
---

# Device deletion and retention erase owned app alerts

Alerts are erased with their owning device, or after their own ended-data retention period.

---
appliesTo:
- type: entity
  id: push-device
  effect: removes
permits:
- related:
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
  target: app/api.py#device_delete
- kind: code
  role: implementation
  target: app/housekeeping.py#_prune_push_devices
---

# Device holders and retention processes erase registrations

The current holder can delete device data even while setup is pending. Retention may remove retired or abandoned registrations.

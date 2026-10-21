---
appliesTo:
- type: entity
  id: push-device
  effect: creates
permits:
- actors:
  - resident
  when:
  - entity: service-settings
    fact: App available
    is: true
- unattended: true
  when:
  - entity: service-settings
    fact: App available
    is: true
references:
- kind: code
  role: implementation
  target: app/api.py#register
- kind: code
  role: implementation
  target: app/api.py#_integrity_refusal
---

# Residents register a phone while the app is enabled

Notification setup registers a supported push destination; registration allowances and any required platform attestation must pass.

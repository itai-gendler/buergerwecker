---
appliesTo:
- type: entity
  id: push-device
  effect: changes
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
  target: app/api.py#device_update
- kind: code
  role: implementation
  target: app/api.py#device_verify
- kind: code
  role: implementation
  target: app/push.py#send_push_batch
---

# Device holders and delivery processes change phone registration

The holder changes device preferences and destination using the current device credential; setup acknowledgement establishes verification. Automatic token refresh and verified delivery failures can change registration state.

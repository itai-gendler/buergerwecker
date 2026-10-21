---
availability:
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_prune_push_devices
---

# Erase inactive device

Remove retired or abandoned registrations according to their retention clock and erase alerts owned by a removed registration.
